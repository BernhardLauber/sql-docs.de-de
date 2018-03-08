---
title: "ÜBERSETZEN (Transact-SQL) | Microsoft Docs"
ms.custom: 
ms.date: 12/16/2016
ms.prod: sql-non-specified
ms.prod_service: sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TRANSLATE
- TRANSLATE_TSQL
helpviewer_keywords:
- TRANSLATE function
ms.assetid: 0426fa90-ef6d-4d19-8207-02ee59f74aec
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: e7ea679043b83d8cee26f431602450d023516647
ms.sourcegitcommit: 6b4aae3706247ce9b311682774b13ac067f60a79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/18/2018
---
# <a name="translate-transact-sql"></a>TRANSLATE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2017-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2017-xxxx-xxxx-xxx-md.md)]

Gibt die Zeichenfolge als erstes Argument bereitgestellt werden, nachdem einige im zweiten Argument angegebenen Zeichen in eine Zielsatz von Zeichen übersetzt werden.

## <a name="syntax"></a>Syntax   
```
TRANSLATE ( inputString, characters, translations) 
```

## <a name="arguments"></a>Argumente   

inputString   
Ist ein [Ausdruck](../../t-sql/language-elements/expressions-transact-sql.md) eines beliebigen Typs Zeichen ("Nvarchar", "Varchar", "Nchar", "Char").

Buchstaben   
Ist eine [Ausdruck](../../t-sql/language-elements/expressions-transact-sql.md) eines beliebigen Zeichens-Typs mit Zeichen, die ersetzt werden soll.

Übersetzungen   
Ist ein Zeichen [Ausdruck](../../t-sql/language-elements/expressions-transact-sql.md) , zweites Argument vom Typ und Länge entspricht.

## <a name="return-types"></a>Rückgabetypen   
Gibt einen Zeichenausdruck, der den gleichen Typ wie `inputString` , wobei die Zeichen aus dem zweiten Argument mit den entsprechenden Zeichen von Dritten Argument ersetzt werden.

## <a name="remarks"></a>Hinweise   

`TRANSLATE`Funktion gibt einen Fehler zurück, wenn Zeichen und Übersetzungen unterschiedliche Längen aufweisen. `TRANSLATE`Funktion sollte unverändert Eingabe zurückgeben, wenn null-Werte als Zeichen oder Ersatz Argumente bereitgestellt werden. Das Verhalten der `TRANSLATE` Funktion sollte identisch mit der [ersetzen](../../t-sql/functions/replace-transact-sql.md) Funktion.   

Das Verhalten der `TRANSLATE` -Funktion ist gleichbedeutend mit der Verwendung mehrerer `REPLACE` Funktionen.

`TRANSLATE`ist immer SC-Sortierung beachten.

## <a name="examples"></a>Beispiele   

### <a name="a-replace-square-and-curly-braces-with-regular-braces"></a>A. Ersetzen Sie Square und geschweifte Klammern durch reguläre geschweifte Klammern    
Die folgende Abfrage ersetzt Square und geschweifte Klammern in der Eingabezeichenfolge mit Klammern an:
```
SELECT TRANSLATE('2*[3+4]/{7-2}', '[]{}', '()()');
```
[!INCLUDE[ssResult_md](../../includes/ssresult-md.md)]
```
2*(3+4)/(7-2)
```

>  [!NOTE]
>  Die `TRANSLATE` -Funktion in diesem Beispiel ist, entspricht aber wesentlich vereinfachte als die Verwendung der folgenden Anweisung `REPLACE`:`SELECT REPLACE(REPLACE(REPLACE(REPLACE('2*[3+4]/{7-2}','[','('), ']', ')'), '{', '('), '}', ')');` 


###  <a name="b-convert-geojson-points-into-wkt"></a>B. GeoJSON-Punkte in WKT konvertieren    
GeoJSON ist ein Format für eine Vielzahl von geografischen Datenstrukturen-Codierung. Mit der `TRANSLATE` Funktion Entwickler können einfach GeoJSON-Punkte WKT-Format und umgekehrt zu konvertieren. Die folgende Abfrage ersetzt Square und geschweifte Klammern in der Eingabe durch reguläre geschweiften Klammern an:   
```sql
SELECT TRANSLATE('[137.4, 72.3]' , '[,]', '( )') AS Point,
    TRANSLATE('(137.4 72.3)' , '( )', '[,]') AS Coordinates;
```

[!INCLUDE[ssResult_md](../../includes/ssresult-md.md)]   


|Punkt  |Koordinaten |  
---------|--------- |
(137.4  72.3) |[137.4,72.3] |


## <a name="see-also"></a>Siehe auch
 [CONCAT &#40;Transact-SQL&#41;](../../t-sql/functions/concat-transact-sql.md)  
 [CONCAT_WS &#40;Transact-SQL&#41;](../../t-sql/functions/concat-ws-transact-sql.md)  
 [FORMATMESSAGE &#40;Transact-SQL&#41;](../../t-sql/functions/formatmessage-transact-sql.md)  
 [QUOTENAME &#40;Transact-SQL&#41;](../../t-sql/functions/quotename-transact-sql.md)  
 [REPLACE &#40;Transact-SQL&#41;](../../t-sql/functions/replace-transact-sql.md)  
 [REVERSE &#40;Transact-SQL&#41;](../../t-sql/functions/reverse-transact-sql.md)  
 [STRING_AGG &#40;Transact-SQL&#41;](../../t-sql/functions/string-agg-transact-sql.md)  
 [STRING_ESCAPE &#40;Transact-SQL&#41;](../../t-sql/functions/string-escape-transact-sql.md)  
 [STUFF &#40;Transact-SQL&#41;](../../t-sql/functions/stuff-transact-sql.md)  
 [Zeichenfolgenfunktionen (Transact-SQL)](../../t-sql/functions/string-functions-transact-sql.md)   

