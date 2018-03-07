---
title: Sql_variant (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 9/12/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|data-types
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sql_variant
- sql_variant_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sql_variant comparisons
- storing data [SQL Server], sql_variant
- sql_variant data type
- storage [SQL Server], sql_variant
ms.assetid: 01229779-8bc1-4c7d-890a-8246d4899250
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 01a11cca67bbf24afa7d74d5e776a969d62920dc
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="sqlvariant-transact-sql"></a>sql_variant (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Ein Datentyp, der Werte verschiedener von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützter Datentypen speichert.
  
![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntax  
  
```sql
sql_variant  
```  
  
## <a name="remarks"></a>Hinweise  
**Sql_variant** kann in Spalten, Parametern, Variablen und die Rückgabewerte von benutzerdefinierten Funktionen verwendet werden. **Sql_variant** ermöglicht diese Datenbankobjekte Werte anderer Datentypen unterstützen.
  
Eine Spalte vom Typ **Sql_variant** enthält möglicherweise Zeilen verschiedener Datentypen. Angenommen, eine Spalte, die als definiert **Sql_variant** können speichern **Int**, **binäre**, und **Char** Werte.
  
**Sql_variant** haben eine maximale Länge von 8016 Byte. Dies schließt sowohl die Basistypinformationen als auch den Basistypwert ein. Die maximale Länge des Basistypwerts ist 8.000 Byte.
  
Ein **Sql_variant** -Datentyp muss zuerst in die Basisdaten Typwert umgewandelt werden, bevor in Operationen wie Addition und Subtraktion.
  
**Sql_variant** kann einen Standardwert zugewiesen werden. Dieser Datentyp kann auch NULL als zugrunde liegenden Wert haben, den NULL-Werten ist jedoch kein Basistyp zugeordnet. Darüber hinaus **Sql_variant** sind keine anderen **Sql_variant** als Basistyp.
  
Ein Schlüssel eindeutiger, Primär- oder Fremdschlüssel kann Spalten vom Typ enthalten **Sql_variant**, aber die Gesamtlänge der Datenwerte, aus denen der Schlüssel einer bestimmten Zeile darf nicht länger als die maximale Länge eines Indexes sein. Diese beträgt 900 Bytes.
  
Eine Tabelle kann eine beliebige Anzahl von verfügen **Sql_variant** Spalten.
  
**Sql_variant** kann nicht in CONTAINSTABLE und FREETEXTTABLE verwendet werden.
  
ODBC unterstützt nicht vollständig **Sql_variant**. Deshalb werden Abfragen von **Sql_variant** Spalten werden als binäre Daten zurückgegeben, wenn Sie Microsoft OLE DB-Anbieter für ODBC (MSDASQL) verwenden. Z. B. eine **Sql_variant** Spalte mit den Zeichenfolgendaten 'PS2091' wird als 0 x 505332303931 zurückgegeben.
  
## <a name="comparing-sqlvariant-values"></a>Vergleichen von sql_variant-Werten  
Die **Sql_variant** Datentyp gehört, an den Anfang der Hierarchieliste der Datentypen für die Konvertierung. Für **Sql_variant** Vergleiche, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Reihenfolge der Datentyphierarchie in Datentypfamilien unterteilt gruppiert wird.
  
|Datentyphierarchie|Datentypfamilie|  
|---|---|
|**sql_variant**|sql_variant |  
|**datetime2**|Datum und Uhrzeit|  
|**datetimeoffset**|Datum und Uhrzeit|  
|**datetime**|Datum und Uhrzeit|  
|**smalldatetime**|Datum und Uhrzeit|  
|**Datum**|Datum und Uhrzeit|  
|**Uhrzeit**|Datum und Uhrzeit|  
|**float**|Ungefährer numerischer Wert|  
|**real**|Ungefährer numerischer Wert|  
|**decimal**|Genauer numerischer Wert|  
|**money**|Genauer numerischer Wert|  
|**smallmoney**|Genauer numerischer Wert|  
|**bigint**|Genauer numerischer Wert|  
|**int**|Genauer numerischer Wert|  
|**smallint**|Genauer numerischer Wert|  
|**tinyint**|Genauer numerischer Wert|  
|**bit**|Genauer numerischer Wert|  
|**nvarchar**|Unicode|  
|**nchar**|Unicode|  
|**varchar**|Unicode|  
|**char**|Unicode|  
|**varbinary**|Binär (Binary)|  
|**binary**|Binär (Binary)|  
|**uniqueidentifier**|Uniqueidentifier |  
  
Die folgenden Regeln gelten für **Sql_variant** Vergleiche:
-   Wenn **Sql_variant** -Werte unterschiedlicher Basisdatentypen verglichen und die Basisdatentypen verschiedenen Datentypfamilien, gilt der Wert, dessen datentypfamilie in der Hierarchieliste höher ist, das größere der beiden Werte.  
-   Wenn **Sql_variant** -Werte unterschiedlicher Basisdatentypen verglichen und die Basisdatentypen derselben datentypfamilie, der Wert, dessen Basisdatentyp in der Hierarchieliste unten ist, wird in den anderen Datentyp implizit konvertiert und dann wird der Vergleich durchgeführt.  
-   Wenn **Sql_variant** Werte von der **Char**, **Varchar**, **Nchar**, oder **Nvarchar** Datentypen sind verglichen, stützt sind der Vergleich zunächst auf folgenden Kriterien: LCID, LCID-Version, Vergleichsflags und Sortierreihenfolge-ID auf. Diese Kriterien werden als ganzzahlige Werte und in der genannten Reihenfolge verglichen. Sind alle diese Kriterien gleich, werden die tatsächlichen Zeichenfolgenwerte entsprechend der Sortierreihenfolge verglichen.  
  
## <a name="converting-sqlvariant-data"></a>Konvertieren von sql_variant-Daten  
Bei der Verarbeitung von der **Sql_variant** Datentyp [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützt die implizite Konvertierung von Objekten mit anderen Datentypen, die **Sql_variant** Typ. Allerdings [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützt keine implizite Konvertierungen von **Sql_variant** Daten auf ein Objekt mit einem anderen Datentyp.
  
## <a name="restrictions"></a>Einschränkungen  
Die folgende Tabelle enthält die Typen von Werten, die mit nicht gespeichert werden **Sql_variant**:
  
|||  
|-|-|  
|**varchar(max)**|**varbinary(max)**|  
|**nvarchar(max)**|**xml**|  
|**text**|**ntext**|  
|**image**|**RowVersion** (**Zeitstempel**)|  
|**sql_variant**|**geography**|  
|**hierarchyid**|**Geometrie**|  
|Benutzerdefinierte Typen|**datetimeoffset**|  

## <a name="examples"></a>Beispiele  

### <a name="a-using-a-sqlvariant-in-a-table"></a>A. Verwenden eine Sql_variant in einer Tabelle  
 Im folgenden Beispiel erstellt eine Tabelle mit einem Sql_variant-Datentyp. Und im Beispiel ruft dann `SQL_VARIANT_PROPERTY` Informationen zu den `colA` Wert `46279.1` , in dem `colB`  = `1689`, davon ausgehend, dass `tableA` hat `colA` vom Typ `sql_variant` und `colB`.  
  
```sql    
CREATE   TABLE tableA(colA sql_variant, colB int)  
INSERT INTO tableA values ( cast (46279.1 as decimal(8,2)), 1689)  
SELECT   SQL_VARIANT_PROPERTY(colA,'BaseType') AS 'Base Type',  
         SQL_VARIANT_PROPERTY(colA,'Precision') AS 'Precision',  
         SQL_VARIANT_PROPERTY(colA,'Scale') AS 'Scale'  
FROM      tableA  
WHERE      colB = 1689  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]Beachten Sie, dass jeder dieser drei Werte ist ein **Sql_variant**.  
  
```  
Base Type    Precision    Scale  
---------    ---------    -----  
decimal      8           2  
  
(1 row(s) affected)  
```  
  
### <a name="b-using-a-sqlvariant-as-a-variable"></a>B. Verwenden eine Sql_variant als variable   
 Im folgenden Beispiel erstellt eine Variable mit dem Sql_variant-Datentyp, und ruft dann `SQL_VARIANT_PROPERTY` Informationen zu einer Variablen mit dem Namen @v1.  
  
```sql    
DECLARE @v1 sql_variant;  
SET @v1 = 'ABC';  
SELECT @v1;  
SELECT SQL_VARIANT_PROPERTY(@v1, 'BaseType');  
SELECT SQL_VARIANT_PROPERTY(@v1, 'MaxLength');  
```    


## <a name="see-also"></a>Siehe auch
[CAST und CONVERT &#40;Transact-SQL&#41;](../../t-sql/functions/cast-and-convert-transact-sql.md)  
[SQL_VARIANT_PROPERTY &#40; Transact-SQL &#41;](../../t-sql/functions/sql-variant-property-transact-sql.md)
  
  
