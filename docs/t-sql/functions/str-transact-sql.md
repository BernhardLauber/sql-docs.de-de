---
title: STR (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/16/2017
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
- STR
- STR_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- converting numbers to characters
- characters [SQL Server], converting
- character data [SQL Server]
- STR function
ms.assetid: de03531b-d9e7-4c3c-9604-14e582ac20c6
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Active
ms.openlocfilehash: 04386cd8dafb69d08c72b460f3794963c8b6da36
ms.sourcegitcommit: 6b4aae3706247ce9b311682774b13ac067f60a79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/18/2018
---
# <a name="str-transact-sql"></a>STR (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Konvertiert numerische Daten in Zeichenfolgen.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
STR ( float_expression [ , length [ , decimal ] ] )  
```  
  
## <a name="arguments"></a>Argumente  
 *float_expression*  
 Ist ein Ausdruck der ungefähren numerischen (**"float"**)-Datentyp mit einem Dezimaltrennzeichen.  
  
 *length*  
 Die Gesamtlänge. Dazu gehören Dezimaltrennzeichen, Zeichen, Ziffern und Leerzeichen. Der Standardwert lautet 10.  
  
 *decimal*  
 Die Anzahl der Stellen nach dem Dezimaltrennzeichen. *Decimal* muss kleiner oder gleich 16 sein. Wenn *decimal* mehr als 16 ist, und klicken Sie dann das Ergebnis bei sechzehn Stellen rechts vom Dezimaltrennzeichen abgeschnitten wird.  
  
## <a name="return-types"></a>Rückgabetypen  
 **varchar**  
  
## <a name="remarks"></a>Hinweise  
 Wenn angegeben, die Werte für *Länge* und *decimal* an str Übergebenen Parameter müssen positiv sein. Die Zahl wird standardmäßig, oder wenn der Dezimalstellenparameter 0 beträgt, auf eine ganze Zahl gerundet. Die angegebene Länge sollte größer oder gleich dem Teil der Zahl vor dem Dezimalpunkt plus dem Vorzeichen (falls vorhanden) sein. Ein kurzer *Float_expression* wird rechtsbündig in der angegebenen Länge und ein langer *Float_expression* auf die angegebene Anzahl von Dezimalstellen abgeschnitten. Beispielsweise STR (12**,**10) ergibt das Ergebnis 12. Dieser Wert wird im Resultset rechtsbündig ausgerichtet. Allerdings STR (1223**,**2) schneidet das Resultset zu **. Zeichenfolgenfunktionen können geschachtelt werden.  
  
> [!NOTE]  
>  Zum Konvertieren in Unicode-Daten verwenden Sie STR innerhalb einer Convert- oder [Umwandlung](../../t-sql/functions/cast-and-convert-transact-sql.md) Konvertierungsfunktion.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird ein Ausdruck, der aus fünf Ziffern und einem Dezimaltrennzeichen besteht, in eine Zeichenfolge mit sechs Stellen konvertiert. Die Stellen hinter dem Dezimalpunkt werden auf eine Dezimalstelle gerundet.  
  
```  
SELECT STR(123.45, 6, 1);  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
------  
 123.5  
  
(1 row(s) affected)  
```  
  
 Falls der Ausdruck die angegebene Länge überschreitet, wird die Zeichenfolge `**` in der festgelegten Länge zurückgegeben.  
  
```  
SELECT STR(123.45, 2, 2);  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
--  
**  
  
(1 row(s) affected)  
```  
  
 Auch wenn numerische Daten innerhalb von `STR` geschachtelt sind, werden als Ergebnis Zeichendaten mit dem angegebenen Format zurückgegeben.  
  
```  
SELECT STR (FLOOR (123.45), 8, 3;)  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
--------  
 123.000  
  
(1 row(s) affected)  
```  
  
## <a name="see-also"></a>Siehe auch  
 [CAST und CONVERT &#40;Transact-SQL&#41;](../../t-sql/functions/cast-and-convert-transact-sql.md)  
 [FORMAT &#40;Transact-SQL&#41;](../../t-sql/functions/format-transact-sql.md)  
 [Zeichenfolgenfunktionen &#40; Transact-SQL &#41;](../../t-sql/functions/string-functions-transact-sql.md)  
  
  

