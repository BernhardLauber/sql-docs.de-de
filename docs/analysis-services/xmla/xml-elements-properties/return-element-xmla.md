---
title: return-Element (XMLA) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: xmla
ms.reviewer: 
ms.suite: sql
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname: return Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords:
- microsoft.xml.analysis.return
- http://schemas.microsoft.com/analysisservices/2003/engine#return
- urn:schemas-microsoft-com:xml-analysis#return
helpviewer_keywords: return element
ms.assetid: 3cfe8b74-fec3-4987-a74a-5f731444e024
caps.latest.revision: "14"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 6fb9f422df762c370f800cdc6f6dcef799d3fa77
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="return-element-xmla"></a>return-Element (XMLA)
  Enthält Informationen, indem Sie eine [DiscoverResponse](../../../analysis-services/xmla/xml-elements-objects-discoverresponse.md) -Element als Antwort auf eine [Discover](../../../analysis-services/xmla/xml-elements-methods-discover.md) Methodenaufruf oder ein [ExecuteResponse](../../../analysis-services/xmla/xml-elements-objects-executeresponse.md) -Element als Antwort auf eine [Execute](../../../analysis-services/xmla/xml-elements-methods-execute.md) -Methodenaufruf.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<DiscoverResponse> <!-- or ExecuteResponse -->  
   <return>  
      <root>...</root>  
      <!-- or -->  
      <results>...</results> <!-- ExecuteResponse only -->  
   </return>  
</DiscoverResponse>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Beschreibung|  
|--------------------|-----------------|  
|Datentyp und -länge|Keine|  
|Standardwert|Keine|  
|Kardinalität|1-1: Erforderliches Element, das nur einmal auftritt.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|[DiscoverResponse](../../../analysis-services/xmla/xml-elements-objects-discoverresponse.md), [ExecuteResponse](../../../analysis-services/xmla/xml-elements-objects-executeresponse.md)|  
|Untergeordnete Elemente|Finden Sie in der folgenden Tabelle aus.|  
  
|Ancestor|Untergeordnete Elemente|  
|--------------|--------------------|  
|[DiscoverResponse](../../../analysis-services/xmla/xml-elements-objects-discoverresponse.md)|[Stamm](../../../analysis-services/xmla/xml-elements-properties/root-element-xmla.md)|  
|[ExecuteResponse](../../../analysis-services/xmla/xml-elements-objects-executeresponse.md)|[Stamm](../../../analysis-services/xmla/xml-elements-properties/root-element-xmla.md) oder [Ergebnisse](../../../analysis-services/xmla/xml-elements-properties/results-element-xmla.md)|  
  
## <a name="remarks"></a>Hinweise  
 Das **return** -Element enthält die Daten, die von der **Discover** - und der **Execute** -Methode zurückgegeben wurden. In der Regel enthält das **return** -Element ein einzelnes **root** -Element, das entweder die von einem erfolgreichen **Discover** - oder **Execute** -Methodenaufruf zurückgegebenen Daten oder eine von einem nicht erfolgreichen Methodenaufruf zurückgegebene XMLA-Ausnahme (XML for Analysis) enthält. Wenn die **Execute** -Methode einen **Batch** -Befehl enthält, der mehrere Vorgänge ausführt, enthält das **return** -Element ein **results** -Element, das wiederum ein **root** -Element für jeden erfolgreich oder nicht erfolgreich vom **Batch** -Befehl ausgeführten Befehl enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [Datenbankeigenschaften &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
