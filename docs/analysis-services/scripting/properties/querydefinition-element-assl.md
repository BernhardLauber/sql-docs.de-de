---
title: QueryDefinition-Element (ASSL) | Microsoft Docs
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
apiname: QueryDefinition Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords: QueryDefinition
helpviewer_keywords: QueryDefinition element
ms.assetid: 25bf0e93-d5c5-41df-b310-a253a4ace80e
caps.latest.revision: "34"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: dae9a5e0988ec65649ede10c1367601ec99d6c41
ms.sourcegitcommit: f1a6944f95dd015d3774a25c14a919421b09151b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2017
---
# <a name="querydefinition-element-assl"></a>QueryDefinition-Element (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Enthält einen nicht transparenten Ausdruck für eine Abfrage, die zugeordneten eine [DataSource](../../../analysis-services/scripting/objects/datasource-element-assl.md) Element in einer [QueryBinding](../../../analysis-services/scripting/data-type/querybinding-data-type-assl.md) Element.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<QueryBinding>  
   ...  
   <QueryDefinition>...</QueryDefinition>  
   ...  
</QueryBinding>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Beschreibung|  
|--------------------|-----------------|  
|Datentyp und -länge|String|  
|Standardwert|Keine|  
|Kardinalität|1-1: Erforderliches Element, das nur einmal auftritt.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnetes Element|[QueryBinding](../../../analysis-services/scripting/data-type/querybinding-data-type-assl.md)|  
|Untergeordnete Elemente|Keine|  
  
## <a name="remarks"></a>Hinweise  
 Das Element, das das übergeordnete Element des entspricht **QueryDefinition** im Objekt Analysis Management Objects (AMO) Modell ist <xref:Microsoft.AnalysisServices.QueryBinding>.  
  
## <a name="see-also"></a>Siehe auch  
 [Datenbankeigenschaften &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
