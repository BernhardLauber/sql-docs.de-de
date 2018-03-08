---
title: STBoundary (Geometry-Datentyp) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|spatial-geography
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- STBoundary (geometry Data Type)
- STBoundary_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- STBoundary (geometry Data Type)
ms.assetid: f0551674-e6e8-4926-9038-df03f2c807d7
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 9c7db74c44bd314d23c7452722159b769def5777
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="stboundary-geometry-data-type"></a>STBoundary (geometry-Datentyp)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Gibt die Begrenzung einer **Geometrie** Instanz.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
.STBoundary ( )  
```  
  
## <a name="return-types"></a>Rückgabetypen  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Rückgabetyp: **Geometrie**  
  
 CLR-Rückgabetyp: **SqlGeometry**  
  
## <a name="remarks"></a>Hinweise  
 `STBoundary()`Gibt ein leeres **GeometryCollection** Wenn die Endpunkte für einen **LineString**, **CircularString**, oder **CompoundCurve** Instanz sind identisch.  
  
## <a name="examples"></a>Beispiele  
  
### <a name="a-using-stboundary-on-a-linestring-instance-with-different-endpoints"></a>A. Verwenden von STBoundary() in einer LINESTRING-Instanz mit verschiedenen Endpunkten  
 Das folgende Beispiel erstellt eine `LineString``geometry` Instanz. `STBoundary()`Gibt die Begrenzung der `LineString`.  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('LINESTRING(0 0, 2 2, 0 2, 2 0)', 0);  
SELECT @g.STBoundary().ToString();  
```  
  
### <a name="b-using-stboundary-on-a-linestring-instance-with-the-same-endpoints"></a>B. Verwenden von STBoundary() in einer LINESTRING-Instanz mit übereinstimmenden Endpunkten  
 Im folgenden Beispiel wird eine gültige `LineString`-Instanz mit den gleichen Endpunkten erstellt. `STBoundary()` gibt eine leere `GeometryCollection` zurück.  
  
```
 DECLARE @g geometry;  
 SET @g = geometry::STGeomFromText('LINESTRING(0 0, 2 2, 0 2, -2 2, 0 0)', 0);  
 SELECT @g.STBoundary().ToString();
 ```  
  
### <a name="c-using-stboundary-on-a-curvepolygon-instance"></a>C. Verwenden von STBoundary() in einer CurvePolygon-Instanz  
 Im folgenden Beispiel wird `STBoundary()` in einer `CurvePolygon`-Instanz verwendet. `STBoundary()` gibt eine `CircularString`-Instanz zurück.  
  
```
 DECLARE @g geometry;  
 SET @g = geometry::STGeomFromText('CURVEPOLYGON(CIRCULARSTRING(0 0, 2 2, 0 2, -2 2, 0 0))', 0);  
 SELECT @g.STBoundary().ToString();
 ```  
  
## <a name="see-also"></a>Siehe auch  
 [OGC-Methoden für geometry-Instanzen](../../t-sql/spatial-geometry/ogc-methods-on-geometry-instances.md)  
  
  
