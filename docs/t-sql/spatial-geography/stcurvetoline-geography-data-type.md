---
title: STCurveToLine (Geography-Datentyp) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|spatial-geography
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- STCurveToLine_TSQL
- STCurveToLine
dev_langs: TSQL
helpviewer_keywords: STCurveToLine method (geography)
ms.assetid: 2f863a85-6168-465a-b32f-bb5e3de58dee
caps.latest.revision: "12"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: d8353ac3184c6c51668c0da9bce5ab9d33c19b5b
ms.sourcegitcommit: 6c54e67818ec7b0a2e3c1f6e8aca0fdf65e6625f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="stcurvetoline-geography-data-type"></a>STCurveToLine (geography-Datentyp)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Gibt eine polygonale Näherung einer Instanz von **geography** mit Kreisbogensegmenten zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
.STCurveToLine()  
```  
  
## <a name="return-types"></a>Rückgabetypen  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Rückgabetyp: **Geography**  
  
 CLR-Rückgabetyp: **SqlGeography**  
  
## <a name="remarks"></a>Hinweise  
 Gibt eine **LineString** -Instanz für eine **CircularString** - oder **CompoundCurve** -Instanz zurück.  
  
 Gibt eine **Polygon** -Instanz für eine **CurvePolygon** -Instanz zurück.  
  
 Gibt eine Kopie von **geography** -Instanzen zurück, die keine **CircularString**, **CompoundCurve**-Instanz und keine **CurvePolygon** -Instanz enthalten.  
  
 Im Gegensatz zur SQL MM-Spezifikation verwendet diese Methode nicht die Z-Koordinate Werte bei der Berechnung der polygonalen Näherung verwendet. Z-Koordinate Werte vorhanden, in der aufrufenden **Geography** Instanz werden ignoriert.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird eine `LineString` -Instanz zurückgegeben, die eine polygonale Näherung einer `CircularString` -Instanz ist:  
  
```
 DECLARE @g1 geography = 'CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653)';  
 DECLARE @g2 geography;  
 SET @g2 = @g1.STCurveToLine();  
 SELECT @g1.STNumPoints() AS G1, @g2.STNumPoints() AS G2;
 ```  
  
## <a name="see-also"></a>Siehe auch  
 [STLength &#40; Geography-Datentyp &#41;](../../t-sql/spatial-geography/stlength-geography-data-type.md)   
 [STNumPoints &#40; Geography-Datentyp &#41;](../../t-sql/spatial-geography/stnumpoints-geography-data-type.md)   
 [Übersicht über räumliche Datentypen](../../relational-databases/spatial/spatial-data-types-overview.md)  
  
  
