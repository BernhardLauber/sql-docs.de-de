---
title: ErrorConfiguration-Element (XMLA) | Microsoft Docs
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
apiname: ErrorConfiguration Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords:
- http://schemas.microsoft.com/analysisservices/2003/engine#ErrorConfiguration
- urn:schemas-microsoft-com:xml-analysis#ErrorConfiguration
- microsoft.xml.analysis.errorconfiguration
helpviewer_keywords: ErrorConfiguration element
ms.assetid: 5e350f5f-3a14-49b4-80c0-208c61f336d5
caps.latest.revision: "13"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 562e80a617f2a09da5f6eb3b1b85670ef906140c
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="errorconfiguration-element-xmla"></a>ErrorConfiguration-Element (XMLA)
  Gibt die Einstellungen für die Behandlung von Fehlern ab, während eine [Batch](../../../analysis-services/xmla/xml-elements-commands/batch-element-xmla.md) oder [Prozess](../../../analysis-services/xmla/xml-elements-commands/process-element-xmla.md) Vorgang.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<Batch> <!-- or Process -->  
   ...  
   <ErrorConfiguration>  
      <KeyErrorLimit>...</KeyErrorLimit>  
      <KeyErrorLogFile>...</KeyErrorLogFile>  
      <KeyErrorAction>...</KeyErrorAction>  
      <KeyErrorLimitAction>...</KeyErrorLimitAction>  
      <KeyNotFound>...</KeyNotFound>  
      <KeyDuplicate>...</KeyDuplicate>  
      <NullKeyConvertedToUnknown>...</NullKeyConvertedToUnknown>  
      <NullKeyNotAllowed>...<NullKeyNotAllowed>  
   </ErrorConfiguration>  
   ...  
</Batch>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Beschreibung|  
|--------------------|-----------------|  
|Datentyp und -länge|Keine|  
|Standardwert|Keine|  
|Kardinalität|0-1: Optionales Element, das nur einmal auftreten kann.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|[Batch](../../../analysis-services/xmla/xml-elements-commands/batch-element-xmla.md), [Process](../../../analysis-services/xmla/xml-elements-commands/process-element-xmla.md)|  
|Untergeordnete Elemente|[KeyDuplicate](../../../analysis-services/scripting/properties/keyduplicate-element-assl.md), [KeyErrorAction](../../../analysis-services/scripting/properties/keyerroraction-element-assl.md), [KeyErrorLimit](../../../analysis-services/scripting/properties/keyerrorlimit-element-assl.md), [KeyErrorLimitAction](../../../analysis-services/scripting/properties/keyerrorlimitaction-element-assl.md), [KeyErrorLogFile](../../../analysis-services/scripting/properties/keyerrorlogfile-element-assl.md), [ KeyNotFound](../../../analysis-services/scripting/properties/keynotfound-element-assl.md), [NullKeyConvertedToUnknown](../../../analysis-services/scripting/properties/nullkeyconvertedtounknown-element-assl.md), [NullKeyNotAllowed](../../../analysis-services/scripting/properties/nullkeynotallowed-element-assl.md)|  
  
## <a name="remarks"></a>Hinweise  
 Die Struktur dieses Elements ist identisch mit der Struktur des **ErrorConfiguration** -Elements in ASSL (Analysis Services Scripting Language). Weitere Informationen zu den **ErrorConfiguration** Element finden Sie unter [ErrorConfiguration-Element &#40; ASSL &#41; ](../../../analysis-services/scripting/objects/errorconfiguration-element-assl.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datenbankeigenschaften &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
