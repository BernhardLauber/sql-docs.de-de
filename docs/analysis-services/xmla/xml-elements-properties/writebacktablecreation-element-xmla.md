---
title: WritebackTableCreation-Element (XMLA) | Microsoft Docs
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
apiname: WritebackTableCreation Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords:
- urn:schemas-microsoft-com:xml-analysis#WritebackTableCreation
- microsoft.xml.analysis.writebacktablecreation
- http://schemas.microsoft.com/analysisservices/2003/engine#WritebackTableCreation
helpviewer_keywords: WritebackTableCreation element
ms.assetid: e9579d63-e28c-4d4e-9f4a-21c5da24c276
caps.latest.revision: "12"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 6ac62b6327cda533fe6487e1499488a5a1f6ba33
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="writebacktablecreation-element-xmla"></a>WritebackTableCreation-Element (XMLA)
  Bestimmt, ob eine Rückschreibetabelle, während erstellt wird die [Prozess](../../../analysis-services/xmla/xml-elements-commands/process-element-xmla.md) Vorgang.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<Process>  
...  
   <WritebackTableCreation>...</WritebackTableCreation>  
...  
</Process>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Beschreibung|  
|--------------------|-----------------|  
|Datentyp und -länge|Zeichenfolge (Enumeration)|  
|Standardwert|Keine|  
|Kardinalität|0-1: Optionales Element, das nur einmal auftreten kann.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|[Verarbeiten](../../../analysis-services/xmla/xml-elements-commands/process-element-xmla.md)|  
|Untergeordnete Elemente|Keine|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zu Verarbeitungsoptionen verfügbar, um Objekte auf einer Analysis Services-Instanz, finden Sie unter [Verarbeiten eines mehrdimensionalen Modells &#40; Analysis Services &#41; ](../../../analysis-services/multidimensional-models/processing-a-multidimensional-model-analysis-services.md).  
  
 Der Wert des **WritebackTableCreation** -Elements ist auf eine der in der folgenden Tabelle aufgelisteten Zeichenfolgen beschränkt.  
  
|Wert|Description|  
|-----------|-----------------|  
|*Erstellen*|Eine neue Rückschreibetabelle wird erstellt, sofern noch keine vorhanden ist. Wenn bereits eine Rückschreibetabelle vorhanden ist, tritt ein Fehler auf.|  
|*CreateAlways*|Eine neue Rückschreibetabelle wird erstellt, die jede vorhandene Rückschreibetabelle überschreibt.|  
|*"Useexisting"*|Die vorhandene Rückschreibetabelle wird verwendet, wenn bereits eine vorhanden ist. Wenn noch keine vorhanden ist, tritt ein Fehler auf.|  
  
## <a name="see-also"></a>Siehe auch  
 [Datenbankeigenschaften &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
