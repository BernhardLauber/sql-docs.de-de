---
title: "&gt;= (Größer als oder gleich) (Transact-SQL) | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: t-sql|language-elements
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Greater
- '>='
- '>= (Greater Than or Equal To)'
- Equal To
- '>=_TSQL'
- Greater Than
- Equal
dev_langs: TSQL
helpviewer_keywords:
- greater than or equal to operator (>=)
- '>= (greater than or equal to operator)'
ms.assetid: 641ee28d-7536-46dd-a48a-6c63c2d59278
caps.latest.revision: "38"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Active
ms.openlocfilehash: 68fb863abee3f77c9641b13ff341615b96376899
ms.sourcegitcommit: 6c54e67818ec7b0a2e3c1f6e8aca0fdf65e6625f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="gt-greater-than-or-equal-to-transact-sql"></a>&gt;= (Größer als oder gleich) (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Vergleicht zwei Ausdrücke nach dem Kriterium größer als oder gleich (ein Vergleichsoperator).  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
expression >= expression  
```  
  
## <a name="arguments"></a>Argumente  
 *expression*  
 Ist ein beliebiger gültiger [Ausdruck](../../t-sql/language-elements/expressions-transact-sql.md). Beide Ausdrücke müssen implizit konvertierbare Datentypen besitzen. Die Konvertierung folgt den Regeln der [Rangfolge der Datentypen](../../t-sql/data-types/data-type-precedence-transact-sql.md).  
  
## <a name="result-types"></a>Ergebnistypen  
 Boolean  
  
## <a name="remarks"></a>Hinweise  
 Beim Vergleich von Ausdrücken, die ungleich NULL sind, ist das Ergebnis TRUE, wenn der linke Operand einen größeren Wert besitzt als der rechte Operand oder einen Wert, der gleich groß ist; andernfalls ist das Ergebnis FALSE.  
  
 Im Gegensatz zum Vergleichsoperator = (gleich) ist das Ergebnis des Vergleichs zweier NULL-Werte mit dem Operator >= nicht von der ANSI_NULLS-Einstellung abhängig.  
  
## <a name="examples"></a>Beispiele  
  
### <a name="a-using--in-a-simple-query"></a>A. Verwenden von >= in einer einfachen Abfrage  
 Im folgenden Beispiel werden alle Zeilen in der `HumanResources.Department` -Tabelle zurückgegeben, die in `DepartmentID` über einen Wert größer oder gleich 13 verfügen.  
  
```  
-- Uses AdventureWorks  
  
SELECT DepartmentID, Name  
FROM HumanResources.Department  
WHERE DepartmentID >= 13  
ORDER BY DepartmentID;  
  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
DepartmentID Name  
------------ --------------------------------------------------  
13           Quality Assurance  
14           Facilities and Maintenance  
15           Shipping and Receiving  
16           Executive  
  
(4 row(s) affected)  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen &#40;Transact-SQL&#41;](../../t-sql/data-types/data-types-transact-sql.md)   
 [Expressions &#40;Transact-SQL&#41;](../../t-sql/language-elements/expressions-transact-sql.md)   
 [= &#40;Equals&#41; &#40;Transact-SQL&#41;](../../t-sql/language-elements/equals-transact-sql.md)   
 [&#62; &#40; Größer als &#41; &#40; Transact-SQL &#41;](../../t-sql/language-elements/greater-than-transact-sql.md)   
 [Operators &#40;Transact-SQL&#41;](../../t-sql/language-elements/operators-transact-sql.md)  
  
  
