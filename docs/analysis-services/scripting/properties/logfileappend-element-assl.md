---
title: LogFileAppend-Element (ASSL) | Microsoft Docs
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
apiname: LogFileAppend Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords: LogFileAppend
helpviewer_keywords: LogFileAppend element
ms.assetid: f85e94a9-e5c5-478a-a5a0-fc99ed19b582
caps.latest.revision: "32"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: a6af2ce43451db0ed1c0eee88c6248d8487639aa
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="logfileappend-element-assl"></a>LogFileAppend-Element (ASSL)
  Bestimmt, ob die [Trace](../../../analysis-services/scripting/objects/trace-element-assl.md) -Element seine Protokollierungsausgabe an die vorhandene Protokolldatei anfügt oder Sie überschreibt.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<Trace>  
  
   <LogFileAppend>...</LogFileAppend>  
  
</Trace>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Beschreibung|  
|--------------------|-----------------|  
|Datentyp und -länge|Boolean|  
|Standardwert|False|  
|Kardinalität|0-1: Optionales Element, das nur einmal auftreten kann.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnetes Element|[Trace](../../../analysis-services/scripting/objects/trace-element-assl.md)|  
|Untergeordnete Elemente|Keine|  
  
## <a name="remarks"></a>Hinweise  
 Das Element, das das übergeordnete Element des entspricht **LogFileAppend** im Objekt Analysis Management Objects (AMO) Modell ist <xref:Microsoft.AnalysisServices.Trace>.  
  
## <a name="see-also"></a>Siehe auch  
 [Traces-Element &#40; ASSL &#41;](../../../analysis-services/scripting/collections/traces-element-assl.md)   
 [Datenbankeigenschaften &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
