---
title: RENAME (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 11/20/2017
ms.prod: 
ms.prod_service: sql-data-warehouse, pdw
ms.reviewer: 
ms.service: sql-data-warehouse
ms.component: t-sql|statements
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 0907cfd9-33a6-4fa6-91da-7d6679fee878
caps.latest.revision: 
author: barbkess
ms.author: barbkess
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 3c08b4d991717d877ca33cd2d136d0dbf0d30483
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="rename-transact-sql"></a>RENAME (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md.md)]

  Benennt eine benutzerdefinierte Tabelle in [!INCLUDE[ssSDW](../../includes/sssdw-md.md)]. Benennt eine vom Benutzer erstellten Tabelle oder Datenbank in [!INCLUDE[ssPDW](../../includes/sspdw-md.md)].  
  
> [!NOTE]  
>  Umbenennen eine Datenbank in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], verwenden Sie die gespeicherte Prozedur [Sp_renamedb &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/sp-renamedb-transact-sql.md). Um eine Datenbank in Azure SQL-Datenbank umzubenennen, verwenden Sie die Anweisung [ALTER DATABASE (Azure SQL-Datenbank)](/statements/alter-database-azure-sql-database.md). 
  
## <a name="syntax"></a>Syntax  
  
```  
-- Syntax for Azure SQL Data Warehouse  
  
-- Rename a table.  
RENAME OBJECT [ :: ]  [ [ database_name .  [schema_name ] ] . ] | [schema_name . ] ] table_name TO new_table_name  
[;]  
  
```  
  
```  
-- Syntax for Parallel Data Warehouse  
  
-- Rename a table  
RENAME OBJECT [::] [ [ database_name . [ schema_name ] . ] | [ schema_name . ] ] table_name TO new_table_name  
[;]  
  
-- Rename a database  
RENAME DATABASE [::] database_name TO new_database_name  
[;]  
```  
  
## <a name="arguments"></a>Argumente  
 BENENNEN SIE OBJEKT [:]   
          [ [*database_name* . [ *schema_name* ] . ] | [ *Schema_name* . []]*Table_name* TO *New_table_name*  
 **GILT FÜR:**[!INCLUDE[ssSDW](../../includes/sssdw-md.md)],  [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
 Ändern Sie den Namen einer benutzerdefinierten Tabelle. Geben Sie die Tabelle mit einer ein-, zwei- oder dreiteiligen Namen umbenannt werden soll.    Geben Sie die neue Tabelle *New_table_name* als einteiliger Name.  
  
 RENAME DATABASE [::]   
          [ *Database_name* TO *Name der neuen Datenbank*  
 **GILT FÜR:**  [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
 Ändern Sie den Namen einer benutzerdefinierten Datenbank von *Database_name* auf *Name der neuen Datenbank*.  Eine Datenbank kann nicht umbenannt werden, um eines dieser [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]reserviert Datenbanknamen verwendet:  
  
-   master  
  
-   model  
  
-   msdb  
  
-   tempdb  
  
-   pdwtempdb1  
  
-   pdwtempdb2  
  
-   DWConfiguration  
  
-   DWDiagnostics  
  
-   DWQueue  
  
## <a name="permissions"></a>Berechtigungen  
 Zum Ausführen dieses Befehls benötigen Sie diese Berechtigung:  
  
-   **ALTER** Berechtigung für die Tabelle  
   
  
## <a name="limitations-and-restrictions"></a>Einschränkungen  
  
### <a name="cannot-rename-an-external-table-indexes-or-views"></a>Eine externe Tabelle, Indizes oder Sichten kann nicht umbenannt werden.
Sie können eine externe Tabelle, Indizes oder Sichten nicht umbenennen. Anstelle der Umbenennung können Sie die externe Tabelle, den Index oder die Sicht löschen und dann mit dem neuen Namen neu erstellen.

### <a name="cannot-rename-a-table-in-use"></a>Eine Tabelle verwendet, kann nicht umbenannt werden.  
 Eine Tabelle oder Datenbank kann nicht umbenannt werden, während es verwendet wird. Umbenennen einer Tabelle erfordert eine exklusive Sperre für die Tabelle. Wenn die Tabelle verwendet wird, müssen Sie möglicherweise zum Beenden von Sitzungen, die in der Tabelle verwenden. Zum Beenden einer Sitzungs können Sie die KILL-Befehl. Verwenden Sie KILL vorsichtig, da beim Beenden einer Sitzungs nicht gespeicherte Arbeit ein Rollback ausgeführt wird. Sitzungen in SQL Data Warehouse werden von "SID" vorangestellt. Sie müssen dies und die Nummer der Sitzung hinzufügen, wenn den KILL-Befehl aufrufen. Dieses Beispiel zeigt eine Liste der aktiven Sitzungen im Leerlauf und beendet dann die Sitzung "SID1234".  
  
### <a name="views-are-not-updated"></a>Sichten werden nicht aktualisiert.  
 Wenn Sie eine Datenbank umbenennen, werden alle Ansichten, mit denen der frühere Datenbankname ungültig. Dies gilt für Sichten, die sowohl innerhalb als auch außerhalb der Datenbank. Z. B. wenn die Sales-Datenbank umbenannt wird, eine Ansicht, enthält `SELECT * FROM Sales.dbo.table1` werden dadurch ungültig. Sie können zum Beheben dieses Problems verwenden dreiteilige Namen in den Ansichten oder aktualisieren die Ansichten aus, um den neuen Datenbanknamen zu verweisen.  
  
 Beim Umbenennen einer Tabellenstatus werden Sichten nicht aktualisiert, um den neuen Tabellennamen verweisen. Jede Ansicht, die innerhalb oder außerhalb der Datenbank, die den Tabellennamen der vorherigen verweist auf werden möglicherweise ungültig. Zum Beheben dieses Problems können Sie jede Ansicht, um den neuen Tabellennamen verweisen aktualisieren.  
  
## <a name="locking"></a>Sperren  
 Umbenennen einer Tabelle verwendet, eine gemeinsame Sperre für das Datenbankobjekt, eine gemeinsame Sperre für das Schemaobjekt und eine exklusive Sperre für die Tabelle.  
  
## <a name="examples"></a>Beispiele  
  
### <a name="a-rename-a-database"></a>A. Umbenennen einer Datenbank  
 **GILT für:** [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] nur  
  
 In diesem Beispiel benennt die Datenbank eine benutzerdefinierte Zeichenfolge adworks ein, um AdWorks2.  
  
```  
-- Rename the user defined database AdWorks  
RENAME DATABASE AdWorks to AdWorks2;  
  
```  
  
 Beim Umbenennen einer Tabellenstatus werden alle Objekte und Eigenschaften der Tabelle zugeordneten aktualisiert, um den neuen Tabellennamen verweisen. Die Tabelle z. B. Definitionen, Indizes, Einschränkungen und Berechtigungen aktualisiert werden. Sichten werden nicht aktualisiert.  
  
### <a name="b-rename-a-table"></a>B. Umbenennen einer Tabelle  
 **GILT FÜR:**[!INCLUDE[ssSDW](../../includes/sssdw-md.md)],  [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
 In diesem Beispiel benennt die Customer-Tabelle in Customer1.  
  
```  
-- Rename the customer table  
RENAME OBJECT Customer TO Customer1;  
  
RENAME OBJECT mydb.dbo.Customer TO Customer1;  
```  
  
 Beim Umbenennen einer Tabellenstatus werden alle Objekte und Eigenschaften der Tabelle zugeordneten aktualisiert, um den neuen Tabellennamen verweisen. Die Tabelle z. B. Definitionen, Indizes, Einschränkungen und Berechtigungen aktualisiert werden. Sichten werden nicht aktualisiert.  
   
  
### <a name="c-move-a-table-to-a-different-schema"></a>C. Eine Tabelle in ein anderes Schema verschieben  
 **GILT FÜR:**[!INCLUDE[ssSDW](../../includes/sssdw-md.md)],  [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
 Wenn Ihre Absicht ist, das Objekt in ein anderes Schema verschieben, verwenden Sie [ALTER SCHEMA &#40; Transact-SQL &#41; ](../../t-sql/statements/alter-schema-transact-sql.md). Verschiebt diesen z. B. das Tabellenelement aus dem Produkt Schema zum Dbo-Schema.  
  
```  
ALTER SCHEMA dbo TRANSFER OBJECT::product.item;  
```  
  
### <a name="d-terminate-sessions-before-renaming-a-table"></a>D. Beenden von Sitzungen vor dem Umbenennen einer Tabelle  
 **GILT FÜR:**[!INCLUDE[ssSDW](../../includes/sssdw-md.md)],  [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
 Es ist wichtig zu beachten, dass Sie eine Tabelle umbenennen können, während es verwendet wird. Umbenennen einer Tabelle erfordert eine exklusive Sperre für die Tabelle. Wenn die Tabelle verwendet wird, müssen Sie möglicherweise zum Beenden der Sitzung, die anhand der folgenden Tabelle. Zum Beenden einer Sitzungs können Sie die KILL-Befehl. Verwenden Sie KILL vorsichtig, da beim Beenden einer Sitzungs nicht gespeicherte Arbeit ein Rollback ausgeführt wird. Sitzungen in SQL Data Warehouse werden von "SID" vorangestellt. Sie müssen dies und die Nummer der Sitzung hinzufügen, wenn den KILL-Befehl aufrufen. Dieses Beispiel zeigt eine Liste der aktiven Sitzungen im Leerlauf und beendet dann die Sitzung "SID1234".  
  
```  
-- View a list of the current sessions  
SELECT session_id, login_name, status   
FROM sys.dm_pdw_exec_sessions   
WHERE status='Active' OR status='Idle';  
  
-- Terminate a session using the session_id.  
KILL 'SID1234';  
```  
  
  
