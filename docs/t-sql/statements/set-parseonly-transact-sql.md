---
title: SET PARSEONLY (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 11/27/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|statements
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- PARSEONLY_TSQL
- SET_PARSEONLY_TSQL
- PARSEONLY
- SET PARSEONLY
dev_langs:
- TSQL
helpviewer_keywords:
- parsing [SQL Server], SET PARSEONLY statement
- checking syntax
- PARSEONLY option
- syntax [SQL Server], verifying
- verifying syntax
- SET PARSEONLY statement
ms.assetid: 514ab042-c53e-4d96-be71-fb08fcc6ef3c
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: eb009b23f9d4a751f6850218f4845c6c70c3bbd3
ms.sourcegitcommit: 531d0245f4b2730fad623a7aa61df1422c255edc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2017
---
# <a name="set-parseonly-transact-sql"></a>SET PARSEONLY (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-asdw-pdw-md](../../includes/tsql-appliesto-ss2008-asdb-asdw-pdw-md.md)]

  Überprüft die Syntax jeder [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung und gibt Fehlermeldungen zurück, ohne die Anweisung zu kompilieren oder auszuführen.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
SET PARSEONLY { ON | OFF }  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn SET PARSEONLY auf ON festgelegt ist, wird die Anweisung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nur analysiert. Wenn SET PARSEONLY auf OFF festgelegt ist, wird die Anweisung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kompiliert und ausgeführt.  
  
 Die Einstellung von SET PARSEONLY erfolgt zur Analysezeit und nicht zur Laufzeit.  
  
 Verwenden Sie PARSEONLY nicht in einer gespeicherten Prozedur oder in einem Trigger. SET PARSEONLY gibt Offsets zurück, wenn SET OFFSETS auf ON festgelegt ist und keine Fehler auftreten.  
  
## <a name="permissions"></a>Berechtigungen  
 Erfordert die Mitgliedschaft in der **public** -Rolle.  
  
## <a name="see-also"></a>Siehe auch  
 [SET-Anweisungen (Transact-SQL)](../../t-sql/statements/set-statements-transact-sql.md)   
 [SET OFFSETS &#40; Transact-SQL &#41;](../../t-sql/statements/set-offsets-transact-sql.md)  
  
  
