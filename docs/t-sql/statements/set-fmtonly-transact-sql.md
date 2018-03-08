---
title: SET FMTONLY (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: t-sql|statements
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- FMTONLY_TSQL
- FMTONLY
- SET FMTONLY
- SET_FMTONLY_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- metadata [SQL Server], only metadata returned
- SET FMTONLY statement
- FMTONLY option
ms.assetid: 02a1d9ac-2e58-433c-9a07-2c5a4a2214e1
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 38625e3079956032513bb0e26c5d37b9a7071fea
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="set-fmtonly-transact-sql"></a>SET FMTONLY (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Gibt nur Metadaten an den Client zurück. Kann verwendet werden, um das Format der Antwort zu testen, ohne die Abfrage tatsächlich auszuführen.  
  
> [!NOTE]  
>  Verwenden Sie diese Funktion nicht. Diese Funktion wurde ersetzt durch [Sp_describe_first_result_set &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/sp-describe-first-result-set-transact-sql.md), [Sp_describe_undeclared_parameters &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/sp-describe-undeclared-parameters-transact-sql.md), [Sys. dm_exec_describe_first_result_set &#40; Transact-SQL &#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-exec-describe-first-result-set-transact-sql.md), und [Sys. dm_exec_describe_first_result_set_for_object &#40; Transact-SQL &#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-exec-describe-first-result-set-for-object-transact-sql.md).  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
SET FMTONLY { ON | OFF }   
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn SET FMTONLY aktiviert ist, werden keine Zeilen verarbeitet oder aufgrund der Anforderung an den Client gesendet.  
  
 Die Einstellung von SET FMTONLY wird zur Ausführungszeit und nicht zur Analysezeit festgelegt.  
  
## <a name="permissions"></a>Berechtigungen  
 Erfordert die Mitgliedschaft in der public-Rolle.  
  
## <a name="examples"></a>Beispiele  
  
### <a name="a-view-the-column-header-information-for-a-query-without-actually-running-the-query"></a>A: Anzeigen der Spaltenheader für eine Abfrage, ohne die Abfrage tatsächlich auszuführen.  
 Im folgenden Beispiel wird die `SET FMTONLY`-Einstellung zu `ON` geändert und eine `SELECT`-Anweisung ausgeführt. Die Einstellung bewirkt, dass die Anweisung nur die Spalteninformationen, aber keine Datenzeilen zurückgibt.  
  
```  
USE AdventureWorks2012;  
GO  
SET FMTONLY ON;  
GO  
SELECT *   
FROM HumanResources.Employee;  
GO  
SET FMTONLY OFF;  
GO  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Beispiele: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] und[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="b-view-the-column-header-information-for-a-query-without-actually-running-the-query"></a>B. Anzeigen der Spaltenheader für eine Abfrage ohne die Abfrage tatsächlich auszuführen.  
 Im folgende Beispiel wird gezeigt, wie nur die Spalte (Metadaten) Headerinformationen für eine Abfrage zurückgegeben wird. Der Batch beginnt mit FMTONLY auf OFF festgelegt und FMTONLY On ändert, bevor Sie die SELECT-Anweisung. Dies bewirkt, dass die SELECT-Anweisung nur die Spaltenheader zurückgegeben; Es werden keine Zeilen mit Daten zurückgegeben.  
  
```  
-- Uses AdventureWorks  
  
BEGIN  
    SET FMTONLY OFF;  
    SET DATEFORMAT mdy;  
    SET FMTONLY ON;  
    SELECT * FROM dbo.DimCustomer;  
    SET FMTONLY OFF;  
END  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [SET-Anweisungen &#40;Transact-SQL&#41;](../../t-sql/statements/set-statements-transact-sql.md)  
  
  

