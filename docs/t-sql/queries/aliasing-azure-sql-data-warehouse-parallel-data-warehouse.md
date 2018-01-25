---
title: Aliasing (Azure SQL Data Warehouse, Parallel Data Warehouse) | Microsoft Docs
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-non-specified
ms.prod_service: sql-data-warehouse, pdw
ms.service: 
ms.component: t-sql|queries
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b3a5c74-05cf-4385-8ee6-6176d003cb8a
caps.latest.revision: "11"
author: barbkess
ms.author: barbkess
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 65d5799c33afabe8ebbdb212c13661699b9fea9e
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="aliasing-azure-sql-data-warehouse-parallel-data-warehouse"></a>Aliasing (Azure SQL Data Warehouse, Parallel Data Warehouse)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md.md)]

  Aliasing ermöglicht es, den temporären Ersatz einer kurz und leicht zu merkenden Zeichenfolge anstelle eines Tabellen- oder Spaltennamens Verzeichnisnamens [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] oder [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] [!INCLUDE[DWsql](../../includes/dwsql-md.md)] Abfragen. Tabellenaliase werden häufig in JOIN-Abfragen verwendet werden, da die JOIN-Syntax vollqualifizierten Objektnamen erforderlich ist, wenn Sie auf Spalten verweisen.  
  
 Aliase müssen es sich um einzelne Wörter mit Benennungsregeln Objekt sein. Weitere Informationen finden Sie unter "Benennungsregeln für Objekt" in der [!INCLUDE[pdw-product-documentation](../../includes/pdw-product-documentation-md.md)]. Aliase darf keine Leerzeichen enthalten und können nicht in einfache oder doppelte Anführungszeichen eingeschlossen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
object_source [ AS ] alias  
```  
  
## <a name="arguments"></a>Argumente  
 *object_source*  
 Der Name der Quelltabelle oder Spalte.  
  
 AS  
 Ein optionaler Alias Präposition. Bei der Arbeit mit Variablen Aliasing Bereich ist das AS-Schlüsselwort nicht zulässig.  
  
 *alias*  
 Der Name der gewünschten temporären Verweis für die Tabelle oder Spalte. Alle gültigen Objektnamen ein kann verwendet werden. Weitere Informationen finden Sie unter "Benennungsregeln für Objekt" in der [!INCLUDE[pdw-product-documentation](../../includes/pdw-product-documentation-md.md)].  
  
## <a name="examples-includesssdwincludessssdw-mdmd-and-includesspdwincludessspdw-mdmd"></a>Beispiele: [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] und[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 Das folgende Beispiel zeigt eine Abfrage mit mehreren Joins. Tabellen- und Spaltennamen Aliasing werden in diesem Beispiel veranschaulicht.  
  
-   Spaltenaliasing: Beide Spalten und Ausdrücke, die im Zusammenhang mit Spalten in der Auswahlliste sind als Alias in diesem Beispiel. `SalesTerritoryRegion AS SalesTR`Zeigt einen einfache Spaltenalias an. `Sum(SalesAmountQuota) AS TotalSales`Zeigt  
  
-   Tabelle Aliasing: `dbo.DimSalesTerritory AS st` zeigt die Erstellung von der `st` alias für die `dbo.DimSalesTerritory` Tabelle.  
  
```  
-- Uses AdventureWorks  
  
SELECT LastName, SUM(SalesAmountQuota) AS TotalSales, SalesTerritoryRegion AS SalesTR,  
    RANK() OVER (PARTITION BY SalesTerritoryRegion ORDER BY SUM(SalesAmountQuota) DESC ) AS RankResult  
FROM dbo.DimEmployee AS e  
INNER JOIN dbo.FactSalesQuota AS sq ON e.EmployeeKey = sq.EmployeeKey  
INNER JOIN dbo.DimSalesTerritory AS st ON e.SalesTerritoryKey = st.SalesTerritoryKey  
WHERE SalesPersonFlag = 1 AND SalesTerritoryRegion != N'NA'  
GROUP BY LastName, SalesTerritoryRegion;  
  
```  
  
 Das AS-Schlüsselwort kann ausgeschlossen werden, wie unten dargestellt, aber Sie wird häufig aus Gründen der Lesbarkeit.  
  
```  
-- Uses AdventureWorks  
  
SELECT LastName, SUM(SalesAmountQuota) TotalSales, SalesTerritoryRegion SalesTR,  
RANK() OVER (PARTITION BY SalesTerritoryRegion ORDER BY SUM(SalesAmountQuota) DESC ) RankResult  
FROM dbo.DimEmployee e  
INNER JOIN dbo.FactSalesQuota sq ON e.EmployeeKey = sq.EmployeeKey  
INNER JOIN dbo.DimSalesTerritory st ON e.SalesTerritoryKey = st.SalesTerritoryKey  
WHERE SalesPersonFlag = 1 AND SalesTerritoryRegion != N'NA'  
GROUP BY LastName, SalesTerritoryRegion;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [SELECT &#40;Transact-SQL&#41;](../../t-sql/queries/select-transact-sql.md)   
 [INSERT &#40; Transact-SQL &#41;](../../t-sql/statements/insert-transact-sql.md)   
 [UPDATE &#40;Transact-SQL&#41;](../../t-sql/queries/update-transact-sql.md)  
  
  
