---
title: ^ (Bitweises exklusives OR) (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 01/10/2017
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
- ^_TSQL
- Bitwise Exclusive OR
- Exclusive
- ^
- bitwise
- OR
dev_langs: TSQL
helpviewer_keywords:
- ^ (bitwise exclusive OR operator)
- OR operator
- exclusive OR mathematical operations
- bitwise exclusive OR (^)
ms.assetid: f38f0ad4-46d0-40ea-9851-0f928fda5293
caps.latest.revision: "44"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: b5833bd94dd28f6c09b2f1c05d4a59a8a137ddad
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="-bitwise-exclusive-or-transact-sql"></a>^ (Bitweises exklusives OR) (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Führt einen bitweisen exklusiven OR-Vorgang zwischen zwei ganzzahligen Werten aus.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
expression ^ expression  
```  
  
## <a name="arguments"></a>Argumente  
 *expression*  
 Ist ein beliebiger gültiger [Ausdruck](../../t-sql/language-elements/expressions-transact-sql.md) von einem der Datentypen der Datentypkategorie ' Integer ' oder die **Bit**, oder die **binäre** oder **Varbinary** Datentypen. *Ausdruck* wird als eine Binärzahl für die bitweise Operation behandelt.  
  
> [!NOTE]  
>  Nur ein *Ausdruck* sein **binäre** oder **Varbinary** -Datentyp in einer bitweisen Operation.  
  
## <a name="result-types"></a>Ergebnistypen  
 **Int** , wenn die Eingabewerte sind **Int**.  
  
 **"smallint"** , wenn die Eingabewerte sind **"smallint"**.  
  
 **"tinyint"** , wenn die Eingabewerte sind **"tinyint"**.  
  
## <a name="remarks"></a>Hinweise  
 Die  **^**  bitweiser Operator führt ein bitweises logisches exklusives OR zwischen den beiden Ausdrücken, indem die jeweils entsprechenden Bits für beide Ausdrücke. Ein Ergebnisbit wird genau dann auf den Wert 1 festgelegt, wenn genau ein Bit, also nicht beide Bits (für das aktuell aufzulösende Bit), der Eingabeausdrücke den Wert 1 aufweist. Falls die Bits beide den Wert 0 oder beide den Wert 1 besitzen, wird das entsprechende Bit im Ergebnis auf 0 festgelegt.  
  
 Wenn der linke und der rechte Ausdruck unterschiedliche ganzzahlige Datentypen aufweisen (z. B. Links *Ausdruck* ist **"smallint"** und das Recht *Ausdruck* ist  **Int**), wird das Argument des kleineren Datentyps in den größeren Datentyp konvertiert. In diesem Fall die **"smallint" *** Ausdruck* konvertiert ein **Int**.  
  
## <a name="examples"></a>Beispiele  
 Im folgende Beispiel wird eine Tabelle mit den **Int** Daten geben, um die ursprünglichen Werte zu speichern, und fügt zwei Werte in einer Zeile.  
  
```  
CREATE TABLE bitwise  
(   
a_int_value int NOT NULL,  
b_int_value int NOT NULL  
);  
GO  
INSERT bitwise VALUES (170, 75);  
GO  
```  
  
 Die folgende Abfrage führt das bitweise exklusive OR für die Spalten `a_int_value` und `b_int_value` aus.  
  
```  
SELECT a_int_value ^ b_int_value  
FROM bitwise;  
GO  
```  
  
 Im Folgenden wird das Resultset aufgeführt:  
  
```  
-----------   
225           
  
(1 row(s) affected)  
```  
  
 Die binäre Darstellung von 170 (`a_int_value` oder `A`) ist `0000 0000 1010 1010`. Die binäre Darstellung von 75 (`b_int_value` oder `B`) ist `0000 0000 0100 1011`. Die Anwendung des bitweisen exklusiven OR-Vorgangs auf diese beiden Werte erzeugt das binäre Ergebnis `0000 0000 1110 0001`, was dem dezimalen Wert 225 entspricht.  
  
```  
(A ^ B)     
         0000 0000 1010 1010  
         0000 0000 0100 1011  
         -------------------  
         0000 0000 1110 0001  
```  
  

  
## <a name="see-also"></a>Siehe auch  
 [Expressions &#40;Transact-SQL&#41;](../../t-sql/language-elements/expressions-transact-sql.md)   
 [Operators &#40;Transact-SQL&#41;](../../t-sql/language-elements/operators-transact-sql.md)   
 [Bitweise Operatoren &#40; Transact-SQL &#41;](../../t-sql/language-elements/bitwise-operators-transact-sql.md)   
 [^ = &#40; Bitweises exklusives OR-Zuweisung &#41; &#40; Transact-SQL &#41;](../../t-sql/language-elements/bitwise-exclusive-or-equals-transact-sql.md)   
 [Zusammengesetzte Operatoren &#40; Transact-SQL &#41;](../../t-sql/language-elements/compound-operators-transact-sql.md)  
  
  


