---
title: UPPER (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/13/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- UPPER_TSQL
- UPPER
dev_langs: TSQL
helpviewer_keywords:
- UPPER function
- characters [SQL Server], lowercase
- converting lowercase to uppercase
- uppercase characters [SQL Server]
- characters [SQL Server], uppercase
- lowercase characters
ms.assetid: 5ced55f7-ac89-4cf2-9465-f63f4dc480db
caps.latest.revision: "26"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Active
ms.openlocfilehash: 7fc98d515cef0d4a1f11e44ada8ff45174b8c95e
ms.sourcegitcommit: 6b4aae3706247ce9b311682774b13ac067f60a79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/18/2018
---
# <a name="upper-transact-sql"></a>UPPER (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Gibt einen Zeichenausdruck zurück, wobei Kleinbuchstaben in Großbuchstaben umgewandelt werden.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
UPPER ( character_expression )  
```  
  
## <a name="arguments"></a>Argumente  
 *character_expression*  
 Ist ein [Ausdruck](../../t-sql/language-elements/expressions-transact-sql.md) von Zeichendaten. *Character_expression* kann eine Konstante, Variable oder Spalte mit Zeichen- oder Binärdaten sein.  
  
 *Character_expression* muss einen Datentyp, der implizit in **Varchar**. Verwenden Sie andernfalls [Umwandlung](../../t-sql/functions/cast-and-convert-transact-sql.md) zur expliziten Konvertierung *Character_expression*.  
  
## <a name="return-types"></a>Rückgabetypen  
 **Varchar** oder **Nvarchar**  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird die `UPPER` und `RTRIM` Funktionen zum Zurückgeben der Nachname von Personen in der `dbo.DimEmployee` Tabelle, sodass sie in Großbuchstaben, gekürzt und mit dem Vornamen verketteten ist.  
  
```  
-- Uses AdventureWorks  
  
SELECT UPPER(RTRIM(LastName)) + ', ' + FirstName AS Name  
FROM dbo.DimEmployee  
ORDER BY LastName;  
```  
  
 Dies ist ein Auszug aus dem Resultset.  
  
 ```
Name
------------------------------
ABBAS, Syed
ABERCROMBIE, Kim
ABOLROUS, Hazem
 ```  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen &#40;Transact-SQL&#41;](../../t-sql/data-types/data-types-transact-sql.md)   
 [Zeichenfolgenfunktionen &#40; Transact-SQL &#41;](../../t-sql/functions/string-functions-transact-sql.md)  
 [LOWER &#40;Transact-SQL&#41;](../../t-sql/functions/lower-transact-sql.md)  
  
  

