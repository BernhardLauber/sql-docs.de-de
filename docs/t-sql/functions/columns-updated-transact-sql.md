---
title: COLUMNS_UPDATED (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/24/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- COLUMNS_UPDATED_TSQL
- COLUMNS_UPDATED
dev_langs:
- TSQL
helpviewer_keywords:
- COLUMNS_UPDATED function
- testing columns
- column testing [SQL Server]
- updated columns
ms.assetid: 765fde44-1f95-4015-80a4-45388f18a42c
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Active
ms.openlocfilehash: a64b20ce0d429ccd257c178abdb7c04630e409ec
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="columnsupdated-transact-sql"></a>COLUMNS_UPDATED (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Gibt ein **varbinary** -Bitmuster zurück, das anzeigt, welche Spalten der Tabelle eingefügt oder aktualisiert wurden. COLUMNS_UPDATED wird überall innerhalb eines INSERT- oder UPDATE-Triggers von [!INCLUDE[tsql](../../includes/tsql-md.md)] verwendet, um zu testen, ob der Trigger bestimmte Aktionen ausführen soll.
  
![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntax  
  
```sql
COLUMNS_UPDATED ( )   
```  
  
## <a name="return-types"></a>Rückgabetypen
**varbinary**
  
## <a name="remarks"></a>Hinweise  
COLUMNS_UPDATED testet, ob UPDATE- oder INSERT-Aktionen für mehrere Spalten ausgeführt wurden. Verwenden Sie zum Testen für eine Spalte wird, Update- oder INSERT versucht [UPDATE()](../../t-sql/functions/update-trigger-functions-transact-sql.md).
  
COLUMNS_UPDATED gibt mindestens ein Byte in der Reihenfolge von links nach rechts zurück, wobei das unwichtigste Bit in jedem Byte ganz rechts steht. Das Bit ganz rechts des Bytes ganz links stellt die erste Spalte in der Tabelle dar; das nächste Bit links davon stellt die zweite Spalte dar usw. COLUMNS_UPDATED gibt mehrere Bytes zurück, falls die Tabelle, für die der Trigger erstellt wird, mehr als acht Spalten enthält, wobei das unwichtigste Byte ganz links steht. COLUMNS_UPDATED gibt TRUE für alle Spalten in INSERT-Aktionen zurück, weil in die Spalten entweder explizite Werte oder implizite (NULL-) Werte eingefügt werden.
  
Um zu testen, ob in bestimmten Spalten Updates oder Einfügungen vorgenommen wurden, verwenden Sie die Syntax mit einem bitweisen Operator und einer ganzzahligen Bitmaske der zu testenden Spalten. Die **t1** -Tabelle enthält beispielsweise die Spalten **C1**, **C2**, **C3**, **C4**und **C5**. So überprüfen, dass die Spalten **C2**, **C3**, und **C4** aktualisiert wurden (mit der Tabelle **t1** müssen einen UPDATE-Trigger), verwenden Sie die Syntax mit **& 14**. So testen Sie, ob nur Spalte **C2** wird aktualisiert wurde, geben **& 2**.
  
COLUMNS_UPDATED kann überall innerhalb eines INSERT- oder UPDATE-Triggers von [!INCLUDE[tsql](../../includes/tsql-md.md)] verwendet werden.
  
Die Spalte ORDINAL_POSITION der INFORMATION_SCHEMA.COLUMNS-Sicht ist nicht mit dem Bitmuster von Spalten kompatibel, die von COLUMNS_UPDATED zurückgegeben werden. Für ein mit COLUMNS_UPDATED kompatibles Bitmuster verweisen Sie, wie im folgenden Beispiel dargestellt, auf die `ColumnID` -Eigenschaft der `COLUMNPROPERTY` -Systemfunktion, wenn Sie die `INFORMATION_SCHEMA.COLUMNS` -Sicht abfragen.
  
```sql
SELECT TABLE_NAME, COLUMN_NAME,  
    COLUMNPROPERTY(OBJECT_ID(TABLE_SCHEMA + '.' + TABLE_NAME),  
    COLUMN_NAME, 'ColumnID') AS COLUMN_ID  
FROM AdventureWorks2012.INFORMATION_SCHEMA.COLUMNS  
WHERE TABLE_NAME = 'Person';  
```  
  
## <a name="column-sets"></a>Spaltensätze
Wenn ein Spaltensatz für eine Tabelle definiert wird, verhält sich die COLUMNS_UPDATED-Funktion wie folgt:
-   Wenn eine Spalte, die zu dem Spaltensatz gehört, explizit aktualisiert wird, werden das entsprechende Bit für diese Spalte und das Bit für den Spaltensatz auf 1 festgelegt.  
-   Wenn ein Spaltensatz explizit aktualisiert wird, wird das Bit für den Spaltensatz auf 1 festgelegt, und die Bits für alle Sparsespalten in dieser Tabelle werden auf 1 festgelegt.  
-   Für Einfügevorgänge werden alle Bits auf 1 festgelegt.  
  
     Da bei Änderungen des Spaltensatzes die Bits aller Spalten in diesem Spaltensatz auf 1 festgelegt werden, erscheinen auch die Spalten, an denen keine Änderung vorgenommen wurde, als geändert. Weitere Informationen zu Spaltensätzen finden Sie unter [Verwenden von Spaltensätzen](../../relational-databases/tables/use-column-sets.md).  
  
## <a name="examples"></a>Beispiele  
  
### <a name="a-using-columnsupdated-to-test-the-first-eight-columns-of-a-table"></a>A. Verwenden von COLUMNS_UPDATED zum Testen der ersten acht Spalten einer Tabelle  
Im folgenden Beispiel werden zwei Tabellen erstellt: `employeeData` und `auditEmployeeData`. Die `employeeData` -Tabelle enthält vertrauliche Gehaltsinformationen und kann von Mitgliedern der Personalabteilung geändert werden. Wenn die Sozialversicherungsnummer (SSN, Social Security Number), das Jahresgehalt oder die Kontonummer für einen Mitarbeiter geändert wird, wird ein Überwachungsdatensatz generiert und in die `auditEmployeeData` -Tabelle eingefügt.
  
Mit `COLUMNS_UPDATED()`kann schnell getestet werden, ob Änderungen an den Spalten vorgenommen wurden, die vertrauliche Informationen zu Mitarbeitern enthalten. `COLUMNS_UPDATED()` kann jedoch nur dann auf diese Weise verwendet werden, wenn Sie Änderungen an den ersten acht Spalten in der Tabelle erkennen möchten.
  
```sql
USE AdventureWorks2012;  
GO  
IF EXISTS(SELECT TABLE_NAME FROM INFORMATION_SCHEMA.TABLES  
   WHERE TABLE_NAME = 'employeeData')  
   DROP TABLE employeeData;  
IF EXISTS(SELECT TABLE_NAME FROM INFORMATION_SCHEMA.TABLES  
   WHERE TABLE_NAME = 'auditEmployeeData')  
   DROP TABLE auditEmployeeData;  
GO  
CREATE TABLE dbo.employeeData (  
   emp_id int NOT NULL PRIMARY KEY,  
   emp_bankAccountNumber char (10) NOT NULL,  
   emp_salary int NOT NULL,  
   emp_SSN char (11) NOT NULL,  
   emp_lname nchar (32) NOT NULL,  
   emp_fname nchar (32) NOT NULL,  
   emp_manager int NOT NULL  
   );  
GO  
CREATE TABLE dbo.auditEmployeeData (  
   audit_log_id uniqueidentifier DEFAULT NEWID() PRIMARY KEY,  
   audit_log_type char (3) NOT NULL,  
   audit_emp_id int NOT NULL,  
   audit_emp_bankAccountNumber char (10) NULL,  
   audit_emp_salary int NULL,  
   audit_emp_SSN char (11) NULL,  
   audit_user sysname DEFAULT SUSER_SNAME(),  
   audit_changed datetime DEFAULT GETDATE()  
   );  
GO  
CREATE TRIGGER dbo.updEmployeeData   
ON dbo.employeeData   
AFTER UPDATE AS  
/*Check whether columns 2, 3 or 4 have been updated. If any or all  
columns 2, 3 or 4 have been changed, create an audit record. The
bitmask is: power(2,(2-1))+power(2,(3-1))+power(2,(4-1)) = 14. To test   
whether all columns 2, 3, and 4 are updated, use = 14 instead of >0  
(below).*/
  
   IF (COLUMNS_UPDATED() & 14) > 0  
/*Use IF (COLUMNS_UPDATED() & 14) = 14 to see whether all columns 2, 3,   
and 4 are updated.*/  
      BEGIN  
-- Audit OLD record.  
      INSERT INTO dbo.auditEmployeeData  
         (audit_log_type,  
         audit_emp_id,  
         audit_emp_bankAccountNumber,  
         audit_emp_salary,  
         audit_emp_SSN)  
         SELECT 'OLD',   
            del.emp_id,  
            del.emp_bankAccountNumber,  
            del.emp_salary,  
            del.emp_SSN  
         FROM deleted del;  
  
-- Audit NEW record.  
      INSERT INTO dbo.auditEmployeeData  
         (audit_log_type,  
         audit_emp_id,  
         audit_emp_bankAccountNumber,  
         audit_emp_salary,  
         audit_emp_SSN)  
         SELECT 'NEW',  
            ins.emp_id,  
            ins.emp_bankAccountNumber,  
            ins.emp_salary,  
            ins.emp_SSN  
         FROM inserted ins;  
   END;  
GO  
  
/*Inserting a new employee does not cause the UPDATE trigger to fire.*/  
INSERT INTO employeeData  
   VALUES ( 101, 'USA-987-01', 23000, 'R-M53550M', N'Mendel', N'Roland', 32);  
GO  
  
/*Updating the employee record for employee number 101 to change the   
salary to 51000 causes the UPDATE trigger to fire and an audit trail to   
be produced.*/  
  
UPDATE dbo.employeeData  
   SET emp_salary = 51000  
   WHERE emp_id = 101;  
GO  
SELECT * FROM auditEmployeeData;  
GO  
  
/*Updating the employee record for employee number 101 to change both   
the bank account number and social security number (SSN) causes the   
UPDATE trigger to fire and an audit trail to be produced.*/  
  
UPDATE dbo.employeeData  
   SET emp_bankAccountNumber = '133146A0', emp_SSN = 'R-M53550M'  
   WHERE emp_id = 101;  
GO  
SELECT * FROM dbo.auditEmployeeData;  
  
GO  
```  
  
### <a name="b-using-columnsupdated-to-test-more-than-eight-columns"></a>B. Verwenden von COLUMNS_UPDATED zum Testen von mehr als acht Spalten  
Wenn Sie testen möchten, ob Updates vorhanden sind, die andere Spalten als die ersten acht Spalten in einer Tabelle betreffen, verwenden Sie die `SUBSTRING` -Funktion, um die richtigen durch `COLUMNS_UPDATED`zurückgegebenen Bits zu testen. Im folgenden Beispiel wird getestet, ob Updates vorhanden sind, die die Spalten `3`, `5`und `9` in der `AdventureWorks2012.Person.Person` -Tabelle betreffen.
  
```sql
USE AdventureWorks2012;  
GO  
IF OBJECT_ID (N'Person.uContact2', N'TR') IS NOT NULL  
    DROP TRIGGER Person.uContact2;  
GO  
CREATE TRIGGER Person.uContact2 ON Person.Person  
AFTER UPDATE AS  
    IF ( (SUBSTRING(COLUMNS_UPDATED(),1,1) & 20 = 20)   
        AND (SUBSTRING(COLUMNS_UPDATED(),2,1) & 1 = 1) )   
    PRINT 'Columns 3, 5 and 9 updated';  
GO  
  
UPDATE Person.Person   
   SET NameStyle = NameStyle,  
      FirstName=FirstName,  
      EmailPromotion=EmailPromotion;  
GO  
```  
  
## <a name="see-also"></a>Siehe auch
[Bitweise Operatoren &#40; Transact-SQL &#41;](../../t-sql/language-elements/bitwise-operators-transact-sql.md)  
[CREATE TRIGGER &#40;Transact-SQL&#41;](../../t-sql/statements/create-trigger-transact-sql.md)  
[UPDATE &#40; &#41; &#40; Transact-SQL &#41;](../../t-sql/functions/update-trigger-functions-transact-sql.md)
  
  
