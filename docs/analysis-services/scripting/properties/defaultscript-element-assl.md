---
title: DefaultScript-Element (ASSL) | Microsoft Docs
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
apiname: DefaultScript Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords: DefaultScript
helpviewer_keywords: DefaultScript element
ms.assetid: 60716e63-2d64-4774-9ac9-253efe612fa5
caps.latest.revision: "34"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 72a8171e9dedf77983c685d3081a0525a1d4015c
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="defaultscript-element-assl"></a>DefaultScript-Element (ASSL)
  Identifiziert das Standard- [MdxScript](../../../analysis-services/scripting/objects/mdxscript-element-assl.md) Element in der [MdxScripts](../../../analysis-services/scripting/collections/mdxscripts-element-assl.md) Auflistung.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<MdxScript>  
   ...  
   <DefaultScript>...</DefaultScript>  
   ...  
</MdxScript>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Beschreibung|  
|--------------------|-----------------|  
|Datentyp und -länge|Boolean|  
|Standardwert|**Wahr**|  
|Cardinality|0-1: Optionales Element, das nur einmal auftreten kann.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|[MdxScript-Objekt](../../../analysis-services/scripting/objects/mdxscript-element-assl.md)|  
|Untergeordnete Elemente|Keine|  
  
## <a name="remarks"></a>Hinweise  
 Das Einrichten des Werts für **DefaultScript** auf **True** für ein Skript setzt den Wert für **DefaultScript** auf **False** für alle anderen **MdxScript** -Elemente in der **MdxScripts** -Auflistung.  
  
 Das Element, das das übergeordnete Element des entspricht **DefaultScript** im Objekt Analysis Management Objects (AMO) Modell ist <xref:Microsoft.AnalysisServices.MdxScript>.  
  
## <a name="see-also"></a>Siehe auch  
 [Datenbankeigenschaften &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
