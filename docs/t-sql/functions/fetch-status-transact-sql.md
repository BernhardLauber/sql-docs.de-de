---
title: '@@FETCH_STATUS (Transact-SQL) | Microsoft Docs'
ms.custom: 
ms.date: 09/18/2017
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
- '@@FETCH_STATUS'
- '@@FETCH_STATUS_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- FETCH statement
- status information [SQL Server], FETCH
- '@@FETCH_STATUS function'
ms.assetid: 93659193-e4ff-4dfb-9043-0c4114921b91
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Active
ms.openlocfilehash: 9bc4027eb6be9d79599cb06f7935bd2d052bb2a2
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="x40x40fetchstatus-transact-sql"></a>&#x40;&#x40;Sp_describe_cursor (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Gibt den Status der letzten Cursor-FETCH-Anweisung zurück, die für einen beliebigen der aktuell von der Verbindung geöffneten Cursor ausgegeben wurde.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
@@FETCH_STATUS  
```  
  
## <a name="return-type"></a>Rückgabetyp  
 **integer**  
  
## <a name="return-value"></a>Rückgabewert  
  
|Rückgabewert|Description|  
|------------------|-----------------|  
|0|Die FETCH-Anweisung war erfolgreich.|  
|-1|Die FETCH-Anweisung ist fehlgeschlagen, oder die Zeile war außerhalb des Resultsets.|  
|-2|Die abgerufene Zeile fehlt.|
|-9|Der Cursor wird einen Fetch-Vorgang nicht ausgeführt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Da @@FETCH_STATUS ist global für alle Cursor bei einer Verbindung verwenden@FETCH_STATUS sorgfältig. Nachdem eine FETCH-Anweisung ausgeführt wird, der Test auf Vorhandensein @@FETCH_STATUS auftreten muss, bevor weitere FETCH-Anweisung für einen anderen Cursor ausgeführt wird. Der Wert des @@FETCH_STATUS ist undefiniert, bis ein Abrufvorgang auf der Verbindung aufgetreten sind.  
  
 Ein Benutzer führt z. B. eine FETCH-Anweisung von einem Cursor aus durch und ruft dann eine gespeicherte Prozedur auf, die die Ergebnisse von einem anderen Cursor aus öffnet und verarbeitet. Bei Steuerelement Rückgabe von der aufgerufenen gespeicherten Prozedur@FETCH_STATUS letzten in der gespeicherten Prozedur, nicht die FETCH-Anweisung, die ausgeführt werden, vor dem Aufruf der gespeicherten Prozedur ausgeführten ABRUFS widerspiegelt.  
  
 Um den letzten Fetch-Status eines bestimmten Cursors abzurufen, Fragen Sie die **Fetch_status** Spalte die **dm_exec_cursors** dynamische Verwaltungsfunktion.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird `@@FETCH_STATUS` zur Steuerung der Cursoraktivitäten in einer `WHILE`-Schleife verwendet.  
  
```  
DECLARE Employee_Cursor CURSOR FOR  
SELECT BusinessEntityID, JobTitle  
FROM AdventureWorks2012.HumanResources.Employee;  
OPEN Employee_Cursor;  
FETCH NEXT FROM Employee_Cursor;  
WHILE @@FETCH_STATUS = 0  
   BEGIN  
      FETCH NEXT FROM Employee_Cursor;  
   END;  
CLOSE Employee_Cursor;  
DEALLOCATE Employee_Cursor;  
GO  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Cursorfunktionen &#40;Transact-SQL&#41;](../../t-sql/functions/cursor-functions-transact-sql.md)   
 [Abrufen von Daten &#40; Transact-SQL &#41;](../../t-sql/language-elements/fetch-transact-sql.md)  
  
  
