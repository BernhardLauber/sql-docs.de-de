---
title: "Beispiele für Massenzugriff auf Daten in Azure Blob Storage | Microsoft-Dokumentation"
ms.custom: 
ms.date: 01/04/2017
ms.prod: sql-server-2017
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- bulk importing [SQL Server], from Azure blob storage
- Azure blob storage, bulk import to SQL Server
- BULK INSERT, Azure blob storage
- OPENROWSET, Azure blob storage
ms.assetid: f7d85db3-7a93-400e-87af-f56247319ecd
caps.latest.revision: 2
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: f1e6d604647070e6789fd9a49a7825a3ae3c7e1b
ms.lasthandoff: 04/11/2017

---
# <a name="examples-of-bulk-access-to-data-in-azure-blob-storage"></a>Beispiele für Massenzugriff auf Daten in Azure Blob Storage
[!INCLUDE[tsql-appliesto-ssvNxt-xxxx-xxxx-xxx](../../includes/tsql-appliesto-ssvnxt-xxxx-xxxx-xxx.md)]

Die Anweisungen `BULK INSERT` und `OPENROWSET` können direkt auf eine Datei in Azure Blob Storage zugreifen. In den folgenden Beispielen werden Daten aus einer CSV-Datei (Comma Separated Value: durch Trennzeichen getrennte Werte) (mit dem Namen `inv-2017-01-19.csv`) verwendet, die in einem Container (mit dem Namen `Week3`) gespeichert ist, der in einem Speicherkonto (mit dem Namen `newinvoices`) gespeichert ist. Der Pfad zur Datei kann verwendet werden, ist aber nicht in diesen Beispielen enthalten. 

Für den Massenzugriff auf Azure Blob Storage über SQL Server wird mindestens [!INCLUDE[ssSQLv14_md](../../includes/sssqlv14-md.md)] CTP 1.1 benötigt.

## <a name="create-the-credential"></a>Anmeldeinformationen erstellen   
   
Alle nachfolgenden Beispiele erfordern für die komplette Datenbank gültige Anmeldeinformationen mit einem Verweis auf eine Shared Access Signature.   

>  [!IMPORTANT]
>  Die externe Datenquelle muss mit für die komplette Datenbank gültige Anmeldeinformationen erstellt werden, die die `SHARED ACCESS SIGNATURE`-Identität verwenden. Informationen zum Erstellen einer Shared Access Signature für das Speicherkonto finden Sie unter der Eigenschaft **Shared Access Signature** auf der Eigenschaftenseite des Speicherkontos im Azure-Portal. Weitere Informationen zu SAS finden Sie unter [Verwenden von Shared Access Signatures (SAS)](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1). Weitere Informationen finden Sie unter [ (Erstellen von datenbankweit gültigen Anmeldeinformationen)](../../t-sql/statements/create-database-scoped-credential-transact-sql.md).  
 
Erstellen Sie datenbankweit gültige Anmeldeinformationen mithilfe von `IDENTITY`, die auf `SHARED ACCESS SIGNATURE` festgelegt sein muss. Verwenden Sie den geheimen Schlüssel aus dem Azure-Portal. Beispiel:  

```tsql
CREATE DATABASE SCOPED CREDENTIAL UploadInvoices  
WITH IDENTITY = 'SHARED ACCESS SIGNATURE',
SECRET = 'QLYMgmSXMklt%2FI1U6DcVrQixnlU5Sgbtk1qDRakUBGs%3D';
```


## <a name="accessing-data-in-a-csv-file-referencing-an-azure-blob-storage-location"></a>Zugriff auf Daten in einer CSV-Datei, die auf einen Speicherort von Azure Blob Storage verweisen   
Im folgenden Beispiel wird eine externe Datenquelle verwendet, die auf ein Azure-Speicherkonto mit dem Namen `newinvoices` verweist.   
```tsql
CREATE EXTERNAL DATA SOURCE MyAzureInvoices
    WITH  (
        TYPE = BLOB_STORAGE,
        LOCATION = 'https://newinvoices.blob.core.windows.net', 
        CREDENTIAL = UploadInvoices  
    );
```   

Die `OPENROWSET`-Anweisung fügt den Containernamen (`week3`) zur Dateibeschreibung hinzu. Die Datei heißt `inv-2017-01-19.csv`.
```tsql     
SELECT * FROM OPENROWSET(
   BULK  'week3/inv-2017-01-19.csv',
   DATA_SOURCE = 'MyAzureInvoices',
   SINGLE_CLOB) AS DataFile;
```

Verwenden Sie den Container und die Dateibeschreibung mithilfe von `BULK INSERT`:

```tsql
BULK INSERT Colors2
FROM 'week3/inv-2017-01-19.csv'
WITH (DATA_SOURCE = 'MyAzureInvoices',
      FORMAT = 'CSV'); 
```

## <a name="accessing-data-in-a-csv-file-referencing-a-container-in-an-azure-blob-storage-location"></a>Zugriff auf Daten in einer CSV-Datei, die auf einen Container an einem Speicherort von Azure BLOB-Speicher verweisen   

Im folgenden Beispiel wird eine externe Datenquelle verwendet, die auf einen Container (mit dem Namen `week3`) in einem Azure-Speicherkonto verweist.   
```tsql
CREATE EXTERNAL DATA SOURCE MyAzureInvoicesContainer
    WITH  (
        TYPE = BLOB_STORAGE,
        LOCATION = 'https://newinvoices.blob.core.windows.net/week3', 
        CREDENTIAL = UploadInvoices  
    );
```  
  
Die `OPENROWSET`-Anweisung enthält den Containernamen nicht in der Dateibeschreibung:
```tsql
SELECT * FROM OPENROWSET(
   BULK  'inv-2017-01-19.csv',
   DATA_SOURCE = 'MyAzureInvoicesContainer',
   SINGLE_CLOB) AS DataFile;
```   

Verwenden Sie den Containernamen mithilfe von `BULKINSERT` nicht in der Dateibeschreibung: 

```tsql
BULK INSERT Colors2
FROM 'inv-2017-01-19.csv'
WITH (DATA_SOURCE = 'MyAzureInvoicesContainer',
      FORMAT = 'CSV'); 
```

## <a name="see-also"></a>Siehe auch   

[CREATE DATABASE SCOPED CREDENTIAL (Erstellen von datenbankweit gültigen Anmeldeinformationen)](../../t-sql/statements/create-database-scoped-credential-transact-sql.md)   
[ERSTELLEN EINER EXTERNEN DATENQUELLE](../../t-sql/statements/create-external-data-source-transact-sql.md)   
[BULK INSERT](../../t-sql/statements/bulk-insert-transact-sql.md)   
[OPENROWSET](../../t-sql/functions/openrowset-transact-sql.md)   

