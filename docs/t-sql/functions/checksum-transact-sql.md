---
title: CHECKSUM (Transact-SQL) | Microsoft-Dokumentation
ms.custom: 
ms.date: 07/24/2017
ms.prod: sql-non-specified
ms.prod_service: sql-data-warehouse, database-engine, sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- CHECKSUM_TSQL
- CHECKSUM
dev_langs:
- TSQL
helpviewer_keywords:
- hash indexes
- CHECKSUM function
- checksum values
ms.assetid: e26d3339-845c-49c2-9d89-243376874c13
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Active
ms.openlocfilehash: d41736f6ac216de0ecf755cbf7ca73ba34a697b8
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="checksum-transact-sql"></a>CHECKSUM (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-asdw-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-asdw-xxx-md.md)]

Gibt den Prüfsummenwert zurück, der für eine Zeile einer Tabelle oder eine Liste mit Ausdrücken berechnet wurde. CHECKSUM wurde zum Verwenden beim Erstellen von Hashindizes konzipiert.
  
![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntax  
  
```sql
CHECKSUM ( * | expression [ ,...n ] )  
```  
  
## <a name="arguments"></a>Argumente  
\*  
Gibt an, dass die Berechnung für alle Spalten der Tabelle erfolgt. CHECKSUM gibt einen Fehler zurück, wenn eine Spalte einen nicht vergleichbaren Datentyp hat. Nicht vergleichbare Datentypen sind **text**, **ntext**, **image**, XML und **cursor** sowie **sql_variant** mit einem der vorstehenden Typen als Basistyp.
  
*expression*  
Ein [Ausdruck](../../t-sql/language-elements/expressions-transact-sql.md) eines beliebigen Typs mit Ausnahme eines nicht vergleichbaren Datentyps.
  
## <a name="return-types"></a>Rückgabetypen
 **int**  
  
## <a name="remarks"></a>Remarks  
CHECKSUM berechnet aus der Liste der Argumente einen Hashwert, der Prüfsumme genannt wird. Der Hashwert wurde zum Verwenden beim Erstellen von Hashindizes konzipiert. Wenn die Argumente für CHECKSUM Spalten sind und ein Index für den berechneten CHECKSUM-Wert erstellt wird, ist das Ergebnis ein Hashindex. Dieser kann für Gleichheitssuchen in den Spalten verwendet werden.
  
CHECKSUM erfüllt die Eigenschaften einer Hashfunktion: Wenn CHECKSUM auf zwei beliebige Listen mit Ausdrücken angewendet wird, wird immer derselbe Wert zurückgegeben, falls die entsprechenden Elemente der beiden Listen vom gleichen Typ sind und bezüglich des Vergleichs mit dem Gleichheitsoperator (=) gleich sind. Bei dieser Definition wird für NULL-Werte eines angegebenen Typs angenommen, dass sie bei einem Vergleich "gleich" sind. Wenn sich einer der Werte in der Liste mit Ausdrücken ändert, ändert sich gewöhnlich auch die Prüfsumme der Liste. Es besteht jedoch eine geringe Möglichkeit, dass sich die Prüfsumme nicht ändert. Aus diesem Grund wird nicht empfohlen, CHECKSUM für die Überprüfung auf geänderte Werte zu verwenden, außer es spielt für die Anwendung keine große Rolle, wenn gelegentlich eine Änderung nicht erkannt wird. Verwenden Sie stattdessen lieber [HashBytes](../../t-sql/functions/hashbytes-transact-sql.md). Wenn ein MD5-Hashalgorithmus angegeben wird, ist die Wahrscheinlichkeit, dass HashBytes für zwei verschiedene Eingaben dasselbe Ergebnis zurückgibt, wesentlich geringer als bei CHECKSUM.
  
Die Reihenfolge von Ausdrücken wirkt sich auf den Ergebniswert für CHECKSUM aus. Die Spaltenreihenfolge, die bei CHECKSUM(*) verwendet wird, ist die Spaltenreihenfolge, die in der Tabellen- oder Sichtdefinition angegeben ist. Dies schließt die berechneten Spalten ein.
  
Der CHECKSUM-Wert ist von Sortierung abhängig. Der gleiche Wert gibt einen anderen CHECKSUM-Wert zurück, wenn er mit einer anderen Sortierung gespeichert ist.
  
## <a name="examples"></a>Beispiele  
In den folgenden Beispielen wird die Verwendung von `CHECKSUM` zum Erstellen von Hashindizes gezeigt. Ein Hashindex wird erstellt, indem eine Spalte mit berechneten Prüfsummen zur indizierten Tabelle hinzugefügt wird und dann ein Index aus der Prüfsummenspalte erstellt wird.
  
```sql
-- Create a checksum index.  
SET ARITHABORT ON;  
USE AdventureWorks2012;   
GO  
ALTER TABLE Production.Product  
ADD cs_Pname AS CHECKSUM(Name);  
GO  
CREATE INDEX Pname_index ON Production.Product (cs_Pname);  
GO  
```  
  
Der Prüfsummenindex kann als Hashindex verwendet werden, insbesondere zur Erhöhung der Indizierungsgeschwindigkeit, wenn die Spalte, für die der Index erstellt werden soll, lange Zeichenfolgen enthält. Der Prüfsummenindex kann für die Gleichheitssuche verwendet werden.
  
```sql
/*Use the index in a SELECT query. Add a second search   
condition to catch stray cases where checksums match,   
but the values are not the same.*/  
SELECT *   
FROM Production.Product  
WHERE CHECKSUM(N'Bearing Ball') = cs_Pname  
AND Name = N'Bearing Ball';  
GO  
```  
  
Durch Erstellen des Indexes für die berechnete Spalte wird die Prüfsummenspalte materialisiert, und die Änderungen des `ProductName`-Werts werden an die Prüfsummenspalte weitergegeben. Ein Index kann jedoch auch direkt für die indizierte Spalte erstellt werden. Wenn die Schlüsselwerte jedoch lang sind, ist ein normaler Index wahrscheinlich nicht so leistungsfähig wie ein Prüfsummenindex.
  
## <a name="see-also"></a>Siehe auch
[CHECKSUM_AGG &#40;Transact-SQL&#41;](../../t-sql/functions/checksum-agg-transact-sql.md)  
[HASHBYTES &#40;Transact-SQL&#41;](../../t-sql/functions/hashbytes-transact-sql.md)  
[BINARY_CHECKSUM  &#40;Transact-SQL&#41;](../../t-sql/functions/binary-checksum-transact-sql.md)
  
  
