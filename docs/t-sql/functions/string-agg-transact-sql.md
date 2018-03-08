---
title: STRING_AGG (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 04/19/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- STRING_AGG
- STRING_AGG_TSQL
helpviewer_keywords:
- STRING_AGG function
ms.assetid: 8860ef3f-142f-4cca-aa64-87a123e91206
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Active
ms.openlocfilehash: f2bcc8b02b0228dc403fffc4ef1c6b82557872a4
ms.sourcegitcommit: 6b4aae3706247ce9b311682774b13ac067f60a79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/18/2018
---
# <a name="stringagg-transact-sql"></a>STRING_AGG (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2017-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2017-asdb-xxxx-xxx-md.md)]

Verkettet die Werte von Zeichenfolgenausdrücke durch und platziert die Trennzeichenwerte dazwischen. Das Trennzeichen wird am Ende der Zeichenfolge nicht hinzugefügt werden.
 
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
STRING_AGG ( expression, separator ) [ <order_clause> ]

<order_clause> ::=   
    WITHIN GROUP ( ORDER BY <order_by_expression_list> [ ASC | DESC ] )   
```

## <a name="arguments"></a>Argumente 

*separator*  
Ist ein [Ausdruck](../../t-sql/language-elements/expressions-transact-sql.md) von `NVARCHAR` oder `VARCHAR` Typ, der verwendet wird, als Trennzeichen für verkettet Zeichenfolgen. Sie können literal oder eine Variable sein. 

*expression*  
Ist ein [Ausdruck](../../t-sql/language-elements/expressions-transact-sql.md) eines beliebigen Typs. Ausdrücke werden in konvertiert `NVARCHAR` oder `VARCHAR` Typen während der Verkettung. Nicht-Zeichenfolgen-Datentypen werden in konvertiert `NVARCHAR` Typ.


<order_clause>   
Geben Sie optional Reihenfolge von verketteten Ergebnissen mit `WITHIN GROUP` Klausel:
```
WITHIN GROUP ( ORDER BY <order_by_expression_list> [ ASC | DESC ] )
```   
<order_by_expression_list>   
 
  Eine Liste der nicht konstant [Ausdrücke](../../t-sql/language-elements/expressions-transact-sql.md) , die zum Sortieren der Ergebnisse verwendet werden kann. Nur ein `order_by_expression` pro Abfrage zulässig ist. Die Standardsortierreihenfolge ist Aufsteigend.   
  

## <a name="return-types"></a>Rückgabetypen 

Der Rückgabetyp ist, richtet sich nach der ersten Argument (Ausdruck). Wenn Eingabeargument Zeichenfolgentyp handelt (`NVARCHAR`, `VARCHAR`), Ergebnistyp wird als Eingabetyp identisch sein. Die folgende Tabelle enthält die automatische Konvertierung:  

|Eingabeausdruck-Typ |Ergebnis | 
|-------|-------|
|NVARCHAR(MAX) |NVARCHAR(MAX) |
|VARCHAR(MAX) |VARCHAR(MAX) |
|NVARCHAR (1... 4000) |NVARCHAR(4000) |
|VARCHAR (1... 8000) |VOM DATENTYP VARCHAR(8000) |
|"Int", "bigint", "smallint", "tinyint", numeric, float, real, Bit, Decimal, Smallmoney, Money, Datetime, datetime2, |NVARCHAR(4000) |


## <a name="remarks"></a>Hinweise  
 
`STRING_AGG`ist eine Aggregatfunktion, die alle Ausdrücke aus Zeilen und verkettet diese in einer einzigen Zeichenfolge, an. Expression-Werte werden implizit in Zeichenfolgentypen konvertiert und dann verkettet. Die implizite Konvertierung in Zeichenfolgen erfolgt basierend auf den vorhandenen Regeln für Datentypkonvertierungen. Weitere Informationen zu datentypkonvertierungen finden Sie unter [CAST und CONVERT (Transact-SQL)](../../t-sql/functions/cast-and-convert-transact-sql.md). 

Wenn der Eingabeausdruck Typ `VARCHAR`, das Trennzeichen nicht mit Typ `NVARCHAR`. 

NULL-Werte werden ignoriert, und das entsprechende Trennzeichen nicht hinzugefügt. Um ein Platzhalter für null-Werte zurückzugeben, verwenden die `ISNULL` wie in Beispiel b-Funktion

`STRING_AGG`in jedem Kompatibilitätsgrad ist verfügbar.


## <a name="examples"></a>Beispiele 

### <a name="a-generate-list-of-names-separated-in-new-lines"></a>A. Generieren Sie Liste der Namen in neue Zeilen getrennte 
Im folgenden Beispiel wird eine Liste der Namen in eine Zelle eines einzelnen Resultsets durch Zeilenumbrüche voneinander getrennt.
```sql
SELECT STRING_AGG (FirstName, CHAR(13)) AS csv 
FROM Person.Person; 
```
[!INCLUDE[ssResult_md](../../includes/ssresult-md.md)]

|csv | 
|--- |
|Syed <br />Catherine <br />Kim <br />Kim <br />Kim <br />Hazem <br />... | 

`NULL`Werte in gefunden `name` Zellen werden nicht im Ergebnis zurückgegeben.   
> [!NOTE]  
>  Wenn im Management Studio-Abfrage-Editor verwenden die **Ergebnisse in Raster** Option kann nicht der Wagenrücklauf implementieren. Wechseln Sie zur **Ergebnisse in Text** um das Resultset anzuzeigen richtig festgelegt.   


### <a name="b-generate-list-of-names-separated-with-comma-without-null-values"></a>B. Liste der Namen getrennt durch Kommas ohne NULL-Werte zu generieren   
Im folgenden Beispiel ersetzt null-Werte mit "N/v" und gibt die Namen getrennt durch Kommas in einer Zelle ein Einzelergebnis zurück.  
```sql
SELECT STRING_AGG ( ISNULL(FirstName,'N/A'), ',') AS csv 
FROM Person.Person; 
```

[!INCLUDE[ssResult_md](../../includes/ssresult-md.md)]
 

|Csv | 
|--- |
|John, n/v, Mike, Peter, n/v, n/v, Alice und Bob |  


### <a name="c-generate-comma-separated-values"></a>C. Durch Trennzeichen getrennten Werten zu generieren 

```sql   
SELECT 
STRING_AGG(CONCAT(FirstName, ' ', LastName, ' (', ModifiedDate, ')'), CHAR(13)) 
  AS names 
FROM Person.Person; 
```
[!INCLUDE[ssResult_md](../../includes/ssresult-md.md)]

|Namen | 
|--- |
|Ken Sánchez (8 Februar 2003 12:00 Uhr) <br />Terri Duffy (24. Februar 2002 12:00 Uhr) <br />Roberto Tamburello (5. Dezember 2001 12:00 Uhr) <br />Rob Walter (29. Dezember 2001 12:00 Uhr) <br />... |

> [!NOTE]  
>  Wenn im Management Studio-Abfrage-Editor verwenden die **Ergebnisse in Raster** Option kann nicht der Wagenrücklauf implementieren. Wechseln Sie zur **Ergebnisse in Text** um das Resultset anzuzeigen richtig festgelegt.   
 

### <a name="d-return-news-articles-with-related-tags"></a>D. Zurückgeben von Artikeln mit den zugehörigen tags 

Artikel und die Tags werden in verschiedenen Tabellen aufgeteilt. Entwickler möchte eine Zeile pro jeder Artikel mit allen zugeordneten Tags zurückgegeben. Verwenden folgende Abfrage: 
```sql
SELECT a.articleId, title, STRING_AGG (tag, ',') as tags 
FROM dbo.Article AS a       
LEFT JOIN dbo.ArticleTag AS t 
    ON a.ArticleId = t.ArticleId 
GROUP BY a.articleId, title;
```

[!INCLUDE[ssResult_md](../../includes/ssresult-md.md)]

|articleId |title |Transponder |
|--- |--- |--- |
|172 |Abrufe geben schließen Wahlergebnisse |Politik, Umfragen, City Rat | 
|176 |Neue autobahnmeilenleistung erwartet, dass eine Überlastung zu reduzieren. |NULL |
|177 |Dogs weiterhin als Katzen gängigeren |Abrufe Tieren| 

### <a name="e-generate-list-of-emails-per-towns"></a>E. Liste von e-Mail-Adressen pro brushville generieren

Die folgende Abfrage sucht nach der e-Mail-Adressen von Mitarbeitern und gruppiert sie nach brushville: 
```sql
SELECT town, STRING_AGG (email, ';') AS emails 
FROM dbo.Employee 
GROUP BY town; 
```

[!INCLUDE[ssResult_md](../../includes/ssresult-md.md)]

|Stadt |e-Mail-Nachrichten |
|--- |--- |
|Seattle |syed0@adventure-works.com;catherine0@adventure-works.com;kim2@adventure-works.com |
|LA |sam1@adventure-works.com;hazem0@adventure-works.com |

E-Mail-Nachrichten zurückgegeben, in die e-Mail-Nachrichten, die Spalte zum Senden von e-Mails an die Gruppe von Personen arbeiten in einigen bestimmten brushville direkt verwendet werden kann. 

### <a name="f-generate-a-sorted-list-of-emails-per-towns"></a>F. Eine sortierte Liste von e-Mail-Adressen pro brushville generieren   
   
Ähnlich wie bei den vorherigen Beispiel die folgende Abfrage sucht nach der e-Mail-Adressen von Mitarbeitern, gruppiert sie nach der Stadt und die e-Mail-Nachrichten in alphabetischer Reihenfolge sortiert:   
```sql
SELECT town, 
    STRING_AGG (email, ';') WITHIN GROUP (ORDER BY email ASC) AS emails 
FROM dbo.Employee 
GROUP BY town; 
```
   
[!INCLUDE[ssResult_md](../../includes/ssresult-md.md)]

|Stadt |e-Mail-Nachrichten |
|--- |--- |
|Seattle |catherine0@adventure-works.com;kim2@adventure-works.com;syed0@adventure-works.com |
|LA |hazem0@adventure-works.com;sam1@adventure-works.com |


## <a name="see-also"></a>Siehe auch  
 [CONCAT &#40;Transact-SQL&#41;](../../t-sql/functions/concat-transact-sql.md)  
 [CONCAT_WS &#40;Transact-SQL&#41;](../../t-sql/functions/concat-ws-transact-sql.md)  
 [FORMATMESSAGE &#40;Transact-SQL&#41;](../../t-sql/functions/formatmessage-transact-sql.md)  
 [QUOTENAME &#40;Transact-SQL&#41;](../../t-sql/functions/quotename-transact-sql.md)  
 [REPLACE &#40;Transact-SQL&#41;](../../t-sql/functions/replace-transact-sql.md)  
 [REVERSE &#40;Transact-SQL&#41;](../../t-sql/functions/reverse-transact-sql.md)  
 [STRING_ESCAPE &#40;Transact-SQL&#41;](../../t-sql/functions/string-escape-transact-sql.md)  
 [STUFF &#40;Transact-SQL&#41;](../../t-sql/functions/stuff-transact-sql.md)  
 [TRANSLATE &#40;Transact-SQL&#41;](../../t-sql/functions/translate-transact-sql.md)  
 [Aggregatfunktionen &#40; Transact-SQL &#41;](../../t-sql/functions/aggregate-functions-transact-sql.md)  
 [Zeichenfolgenfunktionen &#40; Transact-SQL &#41;](../../t-sql/functions/string-functions-transact-sql.md)  

