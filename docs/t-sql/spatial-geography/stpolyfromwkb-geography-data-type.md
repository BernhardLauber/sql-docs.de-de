---
title: STPolyFromWKB (Geography-Datentyp) | Microsoft Docs
ms.custom: 
ms.date: 07/30/2017
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
- STPolyFromWKB_TSQL
- STPolyFromWKB (geography Data Type)
dev_langs:
- TSQL
helpviewer_keywords:
- STPolyFromWKB method
ms.assetid: d236e0ea-dabe-4341-a6eb-ecc210d1f056
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 901ef4c168a8d7f7d2edcb87a742bc1ab2c359d4
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="stpolyfromwkb-geography-data-type"></a>STPolyFromWKB (geography-Datentyp)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Gibt eine **GeographyPolygon** Instanz aus einer Open Geospatial Consortium (OGC) Well-Known Binary (WKB)-Darstellung.
  
## <a name="syntax"></a>Syntax  
  
```  
  
STPolyFromWKB ( 'WKB_polygon' , SRID )  
```  
  
## <a name="arguments"></a>Argumente  
 *WKB_polygon*  
 Ist die WKB-Darstellung der **GeographyPolygon** Instanz, die Sie zurückgeben möchten. *WKB_polygon* ist ein **varbinary(max)** Ausdruck.  
  
 *SRID*  
 Ist ein **Int** Ausdruck darstellt, die räumliche verweisen ID (SRID), der die **GeographyPolygon** Instanz, die Sie zurückgeben möchten.  
  
## <a name="return-types"></a>Rückgabetypen  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Rückgabetyp: **Geography**  
  
 CLR-Rückgabetyp: **SqlGeography**  
  
 OGC-Typ: **Polygon**  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode löst eine **FormatException** aus, wenn die Eingabe nicht korrekt formatiert ist.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird `STPolyFromWKB()` zum Erstellen einer `geography` Instanz.  
  
```  
DECLARE @g geography;   
SET @g = geography::STPolyFromWKB(0x01030000000100000005000000F4FDD478E9965EC0DD24068195D3474083C0CAA145965EC0508D976E12D3474083C0CAA145965EC04E62105839D44740F4FDD478E9965EC04E62105839D44740F4FDD478E9965EC0DD24068195D34740, 4326);  
SELECT @g.ToString();  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Statische geography-Methoden des OGC](../../t-sql/spatial-geography/ogc-static-geography-methods.md)  
  
  
