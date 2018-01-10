---
title: Formatieren einer geschachtelten JSON-Ausgabe im PATH-Modus (SQL Server) | Microsoft-Dokumentation
ms.custom: 
ms.date: 07/17/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.component: json
ms.reviewer: 
ms.suite: sql
ms.technology: dbe-json
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 032761b0-6358-42e4-b05c-dbfd663ac881
caps.latest.revision: "19"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: fc211f9a4f61cc45669d3a45a187dd1413255cd7
ms.sourcegitcommit: 4aeedbb88c60a4b035a49754eff48128714ad290
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2018
---
# <a name="format-nested-json-output-with-path-mode-sql-server"></a>Formatieren einer geschachtelten JSON-Ausgabe im PATH-Modus (SQL Server)
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]

Wenn Sie die vollständige Kontrolle über die Ausgabe der **FOR JSON**-Klausel behalten möchten, geben Sie die Option **PATH** an.  
  
Im**PATH** -Modus können Sie Wrapper-Objekte erstellen und komplexe Eigenschaften schachteln. Die Ergebnisse werden wie ein JSON-Objekt-Array formatiert.  
  
Alternativ können Sie die Option **AUTO** verwenden, um die Ausgabe automatisch entsprechend der Struktur der **SELECT**-Anweisung zu formatieren.
 -   Weitere Informationen zur Option **AUTO** finden Sie unter [Format JSON Output Automatically with AUTO Mode (Automatisches Formatieren der JSON-Ausgabe im AUTO-Modus)](../../relational-databases/json/format-json-output-automatically-with-auto-mode-sql-server.md).
 -   Einen Überblick über die beiden Optionen finden Sie unter [Format Query Results as JSON with FOR JSON (Formatieren von Abfrageergebnissen als JSON mit FOR JSON)](../../relational-databases/json/format-query-results-as-json-with-for-json-sql-server.md).
 
Hier sind einige Beispiele für die **FOR JSON** -Klausel mit der Option **PATH** . Geschachtelte Ergebnisse formatieren Sie, wie nachfolgend gezeigt, mit durch Punkte getrennten Spaltennamen oder mit verschachtelten Abfragen. Nullwerte sind standardmäßig nicht in der **FOR JSON**-Ausgabe enthalten.  

## <a name="example---dot-separated-column-names"></a>Beispiel – Durch Punkte getrennte Spaltennamen  
Die ersten fünf Zeilen der AdventureWorks-Tabelle `Person` werden durch die Abfrage als JSON formatiert.  

Die Klausel **FOR JSON PATH** verwendet den Spaltenalias oder einen Spaltennamen, um den Schlüsselnamen in der JSON-Ausgabe zu bestimmen. Wenn ein Alias Punkte enthält, erstellt die Option PATH geschachtelte Objekte.  

 **Dataseteigenschaften**  
  
```sql  
SELECT TOP 5   
       BusinessEntityID As Id,  
       FirstName, LastName,  
       Title As 'Info.Title',  
       MiddleName As 'Info.MiddleName'  
   FROM Person.Person  
   FOR JSON PATH   
```  
  
 **Ergebnis**  
  
```json  
[{
    "Id": 1,
    "FirstName": "Ken",
    "LastName": "Sanchez",
    "Info": {
        "MiddleName": "J"
    }
}, {
    "Id": 2,
    "FirstName": "Terri",
    "LastName": "Duffy",
    "Info": {
        "MiddleName": "Lee"
    }
}, {
    "Id": 3,
    "FirstName": "Roberto",
    "LastName": "Tamburello"
}, {
    "Id": 4,
    "FirstName": "Rob",
    "LastName": "Walters"
}, {
    "Id": 5,
    "FirstName": "Gail",
    "LastName": "Erickson",
    "Info": {
        "Title": "Ms.",
        "MiddleName": "A"
    }
}]
```  
   
## <a name="example---multiple-tables"></a>Beispiel – Mehrere Tabellen  
Wenn Sie in einer Abfrage auf mehr als eine Tabelle verweisen, schachtelt **FOR JSON PATH** jede Spalte mithilfe des Alias. Die folgende Abfrage erstellt ein JSON-Objekt pro (OrderHeader, OrderDetails) Paar, das in der Abfrage verknüpft ist. 
  
 **Dataseteigenschaften**  
  
```sql  
SELECT TOP 2 SalesOrderNumber AS 'Order.Number',  
        OrderDate AS 'Order.Date',  
        UnitPrice AS 'Product.Price',  
        OrderQty AS 'Product.Quantity'  
FROM Sales.SalesOrderHeader H  
   INNER JOIN Sales.SalesOrderDetail D  
     ON H.SalesOrderID = D.SalesOrderID  
FOR JSON PATH   
```  
  
 **Ergebnis**  
  
```json  
[{
    "Order": {
        "Number": "SO43659",
        "Date": "2011-05-31T00:00:00"
    },
    "Product": {
        "Price": 2024.9940,
        "Quantity": 1
    }
}, {
    "Order": {
        "Number": "SO43659"
    },
    "Product": {
        "Price": 2024.9940
    }
}]
```  

## <a name="learn-more-about-the-built-in-json-support-in-sql-server"></a>Erfahren Sie mehr über die integrierte JSON-Unterstützung in SQL Server  
Viele spezifische Lösungen, Anwendungsfälle und Empfehlungen finden Sie in SQL Server und in der Azure SQL-Daten im [Blogbeitrag über die integrierte JSON-Unterstützung](http://blogs.msdn.com/b/sqlserverstorageengine/archive/tags/json/) von Jovan Popovic, Program Manager bei Microsoft.

## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [FOR-Klausel &#40;Transact-SQL&#41;](../../t-sql/queries/select-for-clause-transact-sql.md)  
