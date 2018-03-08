---
title: SQL_VARIANT_PROPERTY (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 09/12/2017
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
- SQL_VARIANT_PROPERTY_TSQL
- SQL_VARIANT_PROPERTY
dev_langs:
- TSQL
helpviewer_keywords:
- SQL_VARIANT_PROPERTY function
- sql_variant data type
ms.assetid: 50e5c1d9-4e95-4ed0-9c92-435c872a399e
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 5947528f4e8959de1b8b4ee3679d4e3e058476d5
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="sqlvariantproperty-transact-sql"></a>SQL_VARIANT_PROPERTY (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Gibt den Basisdatentyp und andere Informationen zu einem **Sql_variant** Wert.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
SQL_VARIANT_PROPERTY ( expression , property )  
```  
  
## <a name="arguments"></a>Argumente  
 *expression*  
 Ist ein Ausdruck vom Typ **Sql_variant**.  
  
 *Eigenschaft*  
 Enthält den Namen des der **Sql_variant** -Eigenschaft für die Informationen bereitgestellt werden. *Eigenschaft* ist **Varchar (**128**)**, und kann einen der folgenden Werte sein:  
  
|Wert|Description|Zurückgegebener Basistyp von sql_variant|  
|-----------|-----------------|----------------------------------------|  
|**BaseType**|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentyp, beispielsweise:<br /><br /> **bigint**<br /><br /> **binary**<br /><br /> **char**<br /><br /> **Datum**<br /><br /> **datetime**<br /><br /> **datetime2**<br /><br /> **datetimeoffset**<br /><br /> **decimal**<br /><br /> **float**<br /><br /> **int**<br /><br /> **money**<br /><br /> **nchar**<br /><br /> **numeric**<br /><br /> **nvarchar**<br /><br /> **real**<br /><br /> **smalldatetime**<br /><br /> **smallint**<br /><br /> **smallmoney**<br /><br /> **Uhrzeit**<br /><br /> **tinyint**<br /><br /> **uniqueidentifier**<br /><br /> **varbinary**<br /><br /> **varchar**|**sysname**<br /><br /> NULL = Eingabe ist nicht gültig.|  
|**Genauigkeit**|Anzahl der Stellen des numerischen Basisdatentyps:<br /><br /> **"DateTime"** = 23<br /><br /> **Smalldatetime** = 16<br /><br /> **"float"** = 53<br /><br /> **echte** = 24<br /><br /> **Decimal** (p, s) und **numerischen** (p, s) = p<br /><br /> **Money** = 19<br /><br /> **Smallmoney** = 10<br /><br /> **"bigint"** = 19<br /><br /> **Int** = 10<br /><br /> **"smallint"** = 5<br /><br /> **"tinyint"** = 3<br /><br /> **Bit** = 1<br /><br /> Alle sonstigen Typen = 0|**int**<br /><br /> NULL = Eingabe ist nicht gültig.|  
|**Dezimalstellen**|Anzahl der Stellen hinter dem Dezimalkomma des numerischen Basisdatentyps:<br /><br /> **Decimal** (p, s) und **numerischen** (p, s) = s<br /><br /> **Money** und **Smallmoney** = 4<br /><br /> **"DateTime"** = 3<br /><br /> Alle anderen Typen = 0|**int**<br /><br /> NULL = Eingabe ist nicht gültig.|  
|**"TotalBytes" So**|Anzahl der Byte, die zum Speichern der Metadaten und der Daten des Werts erforderlich sind. Diese Informationen zur nützlich zum Überprüfen der maximalen Größe einer Datenseite in einem **Sql_variant** Spalte. Wenn der Wert größer als 900 ist, schlägt fehl, Erstellung eines Indexes.|**int**<br /><br /> NULL = Eingabe ist nicht gültig.|  
|**Sortierung**|Stellt die Sortierung des entsprechenden **Sql_variant** Wert.|**sysname**<br /><br /> NULL = Eingabe ist nicht gültig.|  
|**MaxLength**|Maximale Länge des Datentyps in Byte. Beispielsweise **MaxLength** von **Nvarchar (**50**)** ist 100, **MaxLength** von **Int** ist 4.|**int**<br /><br /> NULL = Eingabe ist nicht gültig.|  
  
## <a name="return-types"></a>Rückgabetypen  
 **sql_variant**  
  
## <a name="examples"></a>Beispiele  
### <a name="a-using-a-sqlvariant-in-a-table"></a>A. Verwenden eine Sql_variant in einer Tabelle  
 Das folgende Beispiel ruft `SQL_VARIANT_PROPERTY` Informationen zu den `colA` Wert `46279.1` , in denen `colB`  = `1689`, davon ausgehend, dass `tableA` hat `colA` vom Typ `sql_variant` und `colB`.  
  
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
 Das folgende Beispiel ruft `SQL_VARIANT_PROPERTY` Informationen zu einer Variablen mit dem Namen @v1.  
  
```sql    
DECLARE @v1 sql_variant;  
SET @v1 = 'ABC';  
SELECT @v1;  
SELECT SQL_VARIANT_PROPERTY(@v1, 'BaseType');  
SELECT SQL_VARIANT_PROPERTY(@v1, 'MaxLength');  
```  
  
## <a name="see-also"></a>Siehe auch  
 [sql_variant &#40;Transact-SQL&#41;](../../t-sql/data-types/sql-variant-transact-sql.md)  
  
  

