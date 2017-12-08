---
title: CubeAttribute-Datentyp (ASSL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: scripting
ms.reviewer: 
ms.suite: sql
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname: CubeAttribute Data Type
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords: CubeAttribute
helpviewer_keywords: CubeAttribute data type
ms.assetid: 114ffb44-460b-4971-b31b-dd844e960b81
caps.latest.revision: "45"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 004ae803e654a8267b89bf5b5ab813052f7b3eda
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="cubeattribute-data-type-assl"></a>CubeAttribute-Datentyp (ASSL)
  Definiert einen Grunddatentyp, der ein Attribut zugeordnet darstellt eine [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) Element.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<CubeAttribute>  
   <AttributeID>...</AttributeID>  
   <AggregationUsage>...</AggregationUsage>  
   <AttributeHierarchyOptimizedState>...</AttributeHierarchyOptimizedState>  
   <AttributeHierarchyEnabled>...</AttributeHierarchyEnabled>  
   <AttributeHierarchyVisible>...</AttributeHierarchyVisible>  
   <Annotations>...</Annotations>  
</CubeAttribute>  
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
|Untergeordnete Elemente|[AggregationUsage](../../../analysis-services/scripting/properties/aggregationusage-element-assl.md), [Anmerkungen](../../../analysis-services/scripting/collections/annotations-element-assl.md), [AttributeHierarchyEnabled](../../../analysis-services/scripting/properties/attributehierarchyenabled-element-assl.md), [AttributeHierarchyOptimizedState](../../../analysis-services/scripting/properties/attributehierarchyoptimizedstate-element-assl.md), [AttributeHierarchyVisible](../../../analysis-services/scripting/properties/attributehierarchyvisible-element-assl.md), [AttributeID](../../../analysis-services/scripting/properties/attributeid-element-assl.md)|  
|Abgeleitete Elemente|[Attribut](../../../analysis-services/scripting/objects/attribute-element-assl.md) ([Attribute](../../../analysis-services/scripting/collections/attributes-element-assl.md) Auflistung von [CubeDimension](../../../analysis-services/scripting/data-type/cubedimension-data-type-assl.md))|  
  
## <a name="remarks"></a>Hinweise  
 Die *AttributeHierarchyOptimizedState* Element wird nicht unterstützt, beim Ausführen des Diensts DeploymentMode-konfigurationseigenschaftswerten 1 oder 2 (SharePoint- oder tabellarischer Modus zum Ausführen [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] und tabellarische Modelle Datenbanken).  
  
 Ein Attribut kann nicht als Ebene einer Hierarchie hinzugefügt werden bei der Eigenschaft *AtttributeHierarchyEnabled*, auf "false" festgelegt ist und die Instanz im DeploymentMode 1 oder 2 (SharePoint- oder tabellarischer Servermodus) betrieben wird.  
  
 Attribute in der [CubeDimension](../../../analysis-services/scripting/data-type/cubedimension-data-type-assl.md) Element, das nicht explizit in enthalten sind die [Attribute](../../../analysis-services/scripting/collections/attributes-element-assl.md) Auflistung werden in der Auflistung mit den Standardwerten, die ihnen zugewiesen. Nachdem die Attribute der Auflistung hinzugefügt werden, können die Attribute zurückgegeben werden, indem die [Discover](../../../analysis-services/xmla/xml-elements-methods-discover.md) Methode.  
  
 Die [AggregationUsage](../../../analysis-services/scripting/properties/aggregationusage-element-assl.md) Element Steuerelemente wie [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] automatisch Aggregationen für das Attribut entwirft. Die **AggregationUsage** -Element schränkt keine Aggregationen, die für den Cube manuell erstellt werden.  
  
 Das entsprechende Element im Objektmodell von Analysis Management Objects (AMO) ist <xref:Microsoft.AnalysisServices.CubeAttribute>.  
  
## <a name="see-also"></a>Siehe auch  
 [Analysis Services Scripting Language-XML-Datentypen &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
