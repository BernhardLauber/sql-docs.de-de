---
title: MemberUniqueNameStyle-Element (ASSL) | Microsoft Docs
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
apiname: MemberUniqueNameStyle Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
helpviewer_keywords: MemberUniqueNameStyle element
ms.assetid: f0771c81-0127-4203-9501-ae4f864730fa
caps.latest.revision: "13"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: a166f1ffdf623cbc809bd090b1babf95983b2c31
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="memberuniquenamestyle-element-assl"></a>MemberUniqueNameStyle-Element (ASSL)
  Bestimmt, wie eindeutige Namen für Elemente in Hierarchien enthaltenen generiert werden, die [CubeDimension](../../../analysis-services/scripting/data-type/cubedimension-data-type-assl.md) Element.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<CubeDimension>  
   ...  
   <MemberUniqueNameStyle>...</MemberUniqueNameStyle>  
   ...  
</CubeDimension>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Beschreibung|  
|--------------------|-----------------|  
|Datentyp und -länge|Zeichenfolge (Enumeration)|  
|Standardwert|*Systemeigene*|  
|Cardinality|0-1: Optionales Element, das nur einmal auftreten kann.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnetes Element|[CubeDimension](../../../analysis-services/scripting/data-type/cubedimension-data-type-assl.md)|  
|Untergeordnete Elemente|Keine|  
  
## <a name="remarks"></a>Hinweise  
 Der Wert dieses Elements ist auf eine der in der folgenden Tabelle aufgelisteten Zeichenfolgen beschränkt.  
  
|Wert|Description|  
|-----------|-----------------|  
|*Systemeigene*|Die Instanz legt automatisch die eindeutigen Namen von Elementen fest.|  
|*NamePath*|Die Instanz generiert einen zusammengesetzten Namen, der aus jeder Ebene und der Beschriftung des Elements besteht.|  
  
## <a name="remarks"></a>Hinweise  
 Das Element, das das übergeordnete Element des entspricht **MemberUniqueNameStyle** im Objekt Analysis Management Objects (AMO) Modell ist <xref:Microsoft.AnalysisServices.CubeDimension>.  
  
## <a name="see-also"></a>Siehe auch  
 [Cube-Element &#40; ASSL &#41;](../../../analysis-services/scripting/objects/cube-element-assl.md)   
 [Dimension-Element &#40; ASSL &#41;](../../../analysis-services/scripting/objects/dimension-element-assl.md)   
 [CubeDimension-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/cubedimension-data-type-assl.md)  
  
  
