---
title: ReferenceMeasureGroupDimension-Datentyp (ASSL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ReferenceMeasureGroupDimension Data Type
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- ReferenceMeasureGroupDimension
helpviewer_keywords:
- ReferenceMeasureGroupDimension data type
ms.assetid: 81f7b83e-71a3-4eab-b291-0500d05903dc
caps.latest.revision: 36
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: c9f43f7f7662ccde1a1fa4c4f8229c785bf9c484
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2018
---
# <a name="referencemeasuregroupdimension-data-type-assl"></a>ReferenceMeasureGroupDimension-Datentyp (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Definiert einen abgeleiteten Datentyp, der eine Dimension darstellt, die indirekt mit der Faktentabelle über eine Zwischendimension verknüpft ist. (Eine Sales-Measuregruppe kann beispielsweise auf eine Geography-Dimension verweisen, die über die Customer-Dimension verbunden ist.)  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<ReferenceMeasureGroupDimension>  
   <!-- The following elements extend MeasureGroupDimension -->  
      <IntermediateCubeDimensionID>...</IntermediateCubeDimensionID>  
   <IntermediateGranularityAttributeID>...</IntermediateGranularityAttributeID>  
   <Materialization>...</Materialization>  
</ReferenceMeasureGroupDimension>  
```  
  
## <a name="data-type-characteristics"></a>Datentypmerkmale  
  
|Merkmal|Description|  
|--------------------|-----------------|  
|Basisdatentypen|[MeasureGroupDimension](../../../analysis-services/scripting/data-type/measuregroupdimension-data-type-assl.md)|  
|Abgeleitete Datentypen|InclusionThresholdSetting|  
  
## <a name="data-type-relationships"></a>Datentypbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|InclusionThresholdSetting|  
|Untergeordnete Elemente|[IntermediateCubeDimensionID](../../../analysis-services/scripting/properties/intermediatecubedimensionid-element-assl.md), [IntermediateGranularityAttributeID](../../../analysis-services/scripting/properties/intermediategranularityattributeid-element-assl.md), [Materialisierung](../../../analysis-services/scripting/properties/materialization-element-assl.md)|  
|Abgeleitete Elemente|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Hinweise  
 Das entsprechende Element im Objektmodell von Analysis Management Objects (AMO) ist <xref:Microsoft.AnalysisServices.ReferenceMeasureGroupDimension>.  
  
## <a name="see-also"></a>Siehe auch  
 [Analysis Services Scripting Language-XML-Datentypen &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
