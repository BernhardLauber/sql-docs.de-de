---
title: '@@TOTAL_ERRORS (Transact-SQL) | Microsoft Docs'
ms.custom: 
ms.date: 09/18/2017
ms.prod: sql-non-specified
ms.prod_service: sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '@@TOTAL_ERRORS'
- '@@TOTAL_ERRORS_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- '@@TOTAL_ERRORS function'
- total errors [SQL Server]
- errors [SQL Server], read/write
- number of disk read/write errors
- disks [SQL Server], errors
- write errors [SQL Server]
- read/write errors
ms.assetid: 09e62428-ee0e-4ef5-b969-da9d255f1199
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 53065810884eaae4513f5f8a2725f136daaaa5e4
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="x40x40totalerrors-transact-sql"></a>&#x40;&#x40;TOTAL_ERRORS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Gibt die Anzahl der in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] seit dem letzten Start von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aufgetretenen Schreibfehler auf dem Datenträger zurück.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
@@TOTAL_ERRORS  
```  
  
## <a name="return-types"></a>Rückgabetypen  
 **integer**  
  
## <a name="remarks"></a>Hinweise  
 Nicht alle in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aufgetretenen Schreibfehler werden von dieser Funktion berücksichtigt. Gelegentlich werden nicht als schwerwiegend geltende Schreibfehler vom Server selbst bearbeitet und nicht als Fehler eingestuft. Zum Anzeigen eines Berichts mit mehreren [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Statistiken, einschließlich der Gesamtanzahl von Fehlern ausführen **Sp_monitor**.  
  
## <a name="examples"></a>Beispiele  
 Dieses Beispiel zeigt die Anzahl der in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aufgetretenen Fehler bis zum aktuellen Datum und der aktuellen Uhrzeit an.  
  
```  
SELECT @@TOTAL_ERRORS AS 'Errors', GETDATE() AS 'As of';  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
Errors      As of                   
----------- ----------------------  
0           3/28/2003 12:32:11 PM   
```  
  
## <a name="see-also"></a>Siehe auch  
 [sp_monitor &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-monitor-transact-sql.md)   
 [Statistische Systemfunktionen &#40;Transact-SQL&#41;](../../t-sql/functions/system-statistical-functions-transact-sql.md)  
  
  
