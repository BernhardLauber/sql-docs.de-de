---
title: ColumnID-Element (EventColumn) (ASSL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
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
apiname: ColumnID Element (EventColumn)
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords: ColumnID
helpviewer_keywords: ColumnID element
ms.assetid: c4f4fbad-9d70-4de2-8cf7-caee80a4a1e4
caps.latest.revision: "37"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 068aee390a3208b55323b31720bb42eeaa39f7d8
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="columnid-element-eventcolumn-assl"></a>ColumnID-Element (EventColumn) (ASSL)
  Enthält den Bezeichner (ID) der Spalte mit den Informationen für ein Ereignis erfasst werden sollen, als Teil einer [Ablaufverfolgung](../../../analysis-services/scripting/objects/trace-element-assl.md) Element.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<EventColumn>  
   <ColumnID>...</ColumnID>  
</EventColumn>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Beschreibung|  
|--------------------|-----------------|  
|Datentyp und -länge|String|  
|Standardwert|Keine|  
|Kardinalität|1-1: Erforderliches Element, das nur einmal auftreten kann.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnetes Element|[EventColumn](../../../analysis-services/scripting/data-type/eventcolumn-data-type-assl.md)|  
|Untergeordnete Elemente|Keine.|  
  
## <a name="remarks"></a>Hinweise  
 Das Element, das das übergeordnete Element des entspricht **ColumnID** im Objekt Analysis Management Objects (AMO) Modell ist <xref:Microsoft.AnalysisServices.TraceColumn>.  
  
## <a name="see-also"></a>Siehe auch  
 [Columns-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/columns-element-assl.md)   
 [Event-Element &#40; ASSL &#41;](../../../analysis-services/scripting/objects/event-element-assl.md)   
 [Events-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/events-element-assl.md)   
 [Datenbankeigenschaften &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
