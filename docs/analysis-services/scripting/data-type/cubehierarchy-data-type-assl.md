---
title: CubeHierarchy-Datentyp (ASSL) | Microsoft Docs
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
apiname: CubeHierarchy Data Type
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords: CubeHierarchy
helpviewer_keywords: CubeHierarchy data type
ms.assetid: cd633409-0c14-4dd9-97cc-3d30e25df24f
caps.latest.revision: "44"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 299714f32b8c0536588be684f164ad76b9e5cc65
ms.sourcegitcommit: f1a6944f95dd015d3774a25c14a919421b09151b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2017
---
# <a name="cubehierarchy-data-type-assl"></a>CubeHierarchy-Datentyp (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Definiert einen Grunddatentyp, der Informationen darstellt, zu einer [Hierarchie](../../../analysis-services/scripting/objects/hierarchy-element-assl.md) Element in eine [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) Element.  
  
## <a name="syntax"></a>Syntax  
  
```  
<CubeHierarchy>   <HierarchyID>...</HierarchyID>   <Name>...</Name>   <OptimizedState>...</OptimizedState>   <Visible>...</Visible>   <Enabled>...</Enabled>   <Annotations>...</Annotations></CubeHierarchy>  
```  
  
## <a name="data-type-characteristics"></a>Datentypmerkmale  
  
|Merkmal|Beschreibung|  
|--------------------|-----------------|  
|Basisdatentypen|Keine|  
|Abgeleitete Datentypen|Keine|  
  
## <a name="data-type-relationships"></a>Datentypbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|Keine|  
|Untergeordnete Elemente|[Anmerkungen](../../../analysis-services/scripting/collections/annotations-element-assl.md), [aktiviert](../../../analysis-services/scripting/properties/enabled-element-assl.md), [HierarchyID](../../../analysis-services/scripting/properties/hierarchyid-element-assl.md), [Namen](../../../analysis-services/scripting/properties/name-element-assl.md), [OptimizedState](../../../analysis-services/scripting/properties/optimizedstate-element-assl.md), [sichtbar](../../../analysis-services/scripting/properties/visible-element-assl.md)|  
|Abgeleitete Elemente|[Hierarchie](../../../analysis-services/scripting/objects/hierarchy-element-assl.md) ([Hierarchien](../../../analysis-services/scripting/collections/hierarchies-element-assl.md) Auflistung von [CubeDimension](../../../analysis-services/scripting/data-type/cubedimension-data-type-assl.md))|  
  
## <a name="remarks"></a>Hinweise  
 Dieser Datentyp unterliegt in keinem Bereitstellungsmodus Einschränkungen und kann in jedem dieser Modi verwendet werden: 0 - Mehrdimensional und Data Mining, 1 - SharePoint und 2 - Tabellarisch.  
  
 In SQL Server 2016 Analysis Services und höher die *aktiviert* Eigenschaft kann nicht festgelegt werden, um **"false"** für *CubeHierarchy*.  
  
 Das entsprechende Element im Objektmodell von Analysis Management Objects (AMO) ist <xref:Microsoft.AnalysisServices.CubeHierarchy>.  
  
## <a name="see-also"></a>Siehe auch  
 [Discover-Methode &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-methods-discover.md)   
 [Analysis Services Scripting Language-XML-Datentypen &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
