---
title: Lesen-Element (ASSL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname: Read Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
helpviewer_keywords: Read element
ms.assetid: 2e2c1173-72ca-4e8a-a6cd-fd348ef96d78
caps.latest.revision: "12"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 832f89d5586bd86351604aa9b58cd1c94068a09e
ms.sourcegitcommit: f1a6944f95dd015d3774a25c14a919421b09151b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2017
---
# <a name="read-element-assl"></a>Read-Element (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Bestimmt, ob Daten oder Metadaten für gelesen werden, kann eine bestimmte [CubeDimensionPermission](../../../analysis-services/scripting/data-type/cubedimensionpermission-data-type-assl.md) oder [Berechtigung](../../../analysis-services/scripting/data-type/permission-data-type-assl.md) Element.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<CubeDimensionPermission> <!-- or Permission -->  
   ...  
   <Read>...</Read>  
   ...  
</CubeDimensionPermission>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Beschreibung|  
|--------------------|-----------------|  
|Datentyp und -länge|Zeichenfolge (Enumeration)|  
|Standardwert|*Keine*|  
|Cardinality|0-1: Optionales Element, das nur einmal auftreten kann.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|[CubeDimensionPermission](../../../analysis-services/scripting/objects/cubepermission-element-assl.md), [Berechtigung](../../../analysis-services/scripting/data-type/permission-data-type-assl.md)|  
|Untergeordnete Elemente|Keine|  
  
## <a name="remarks"></a>Hinweise  
 Der Wert dieses Elements ist auf eine der in der folgenden Tabelle aufgelisteten Zeichenfolgen beschränkt.  
  
|Wert|Description|  
|-----------|-----------------|  
|*Keine*|Das übergeordnete Objekt lässt keinen Zugriff auf Daten oder Metadaten zu.|  
|*Zulässig*|Das übergeordnete Objekt lässt Lesezugriff auf Daten und Metadaten zu.|  
  
## <a name="remarks"></a>Hinweise  
 Die Elemente, die den übergeordneten Elementen von entsprechen **lesen** im Objektmodell von Analysis Management Objects (AMO) sind <xref:Microsoft.AnalysisServices.CubeDimensionPermission> und <xref:Microsoft.AnalysisServices.Permission>.  
  
## <a name="see-also"></a>Siehe auch  
 [Cube-Element &#40; ASSL &#41;](../../../analysis-services/scripting/objects/cube-element-assl.md)   
 [Dimension-Element &#40; ASSL &#41;](../../../analysis-services/scripting/objects/dimension-element-assl.md)   
 [CubePermission-Element &#40; ASSL &#41;](../../../analysis-services/scripting/objects/cubepermission-element-assl.md)   
 [Permission-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/permission-data-type-assl.md)   
 [Datenbankeigenschaften &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
