---
title: DATETIMEFROMPARTS (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/29/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DATETIMEFROMPARTS_TSQL
- DATETIMEFROMPARTS
dev_langs:
- TSQL
helpviewer_keywords:
- DATETIMEFROMPARTS function
ms.assetid: 6008148b-bf75-4c98-9392-68a89fa0711c
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: ef125163e41d9ab1b2b465a31694428d22407501
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="datetimefromparts-transact-sql"></a>DATETIMEFROMPARTS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-all-md](../../includes/tsql-appliesto-ss2012-all-md.md)]

Gibt eine **"DateTime"** Wert für das angegebene Datum und die Uhrzeit.
  
![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntax  
  
```sql
DATETIMEFROMPARTS ( year, month, day, hour, minute, seconds, milliseconds )  
```  
  
## <a name="arguments"></a>Argumente  
*Jahr*  
Ganzzahliger Ausdruck, der ein Jahr angibt.
  
*Monat*  
Ganzzahliger Ausdruck, der einen Monat angibt.
  
*Tag*  
Ganzzahliger Ausdruck, der einen Tag angibt.
  
*Stunde*  
Ganzzahliger Ausdruck, der die Stunden angibt.
  
*Minute*  
Ganzzahliger Ausdruck, der die Minuten angibt.
  
*Sekunden*  
Ganzzahliger Ausdruck, der die Sekunden angibt.
  
*Millisekunden*  
Ganzzahliger Ausdruck, der die Millisekunden angibt.
  
## <a name="return-types"></a>Rückgabetypen
**datetime**
  
## <a name="remarks"></a>Hinweise  
**DATETIMEFROMPARTS** gibt einen vollständig initialisierten **"DateTime"** Wert. Wenn die Argumente nicht gültig sind, wird ein Fehler ausgelöst. Wenn erforderliche Argumente null sind, wird Null zurückgegeben.
  
Diese Funktion kann remote auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]-Servern oder höher ausgeführt werden. Sie werden nicht in der Remoteausführung auf Servern, auf denen eine Version unter [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].
  
## <a name="examples"></a>Beispiele  
  
```sql
SELECT DATETIMEFROMPARTS ( 2010, 12, 31, 23, 59, 59, 0 ) AS Result;  
```  
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]
  
```sql
Result  
---------------------------  
2010-12-31 23:59:59.000  
  
(1 row(s) affected)  
```  
  
## <a name="see-also"></a>Siehe auch
["DateTime" &#40; Transact-SQL &#41;](../../t-sql/data-types/datetime-transact-sql.md)
  
  

