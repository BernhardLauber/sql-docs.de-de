---
title: Geben Sie-Element (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- Type Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- microsoft.xml.analysis.type
- http://schemas.microsoft.com/analysisservices/2003/engine#Type
- urn:schemas-microsoft-com:xml-analysis#Type
helpviewer_keywords:
- Type element
ms.assetid: 5d898123-a635-402a-be86-8249d7304fa4
caps.latest.revision: 15
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 363b89eddf7794174689c0d6df7805328c88eb70
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2018
---
# <a name="type-element-xmla"></a>Type-Element (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]Bestimmt den Typ des von auszuführenden Verarbeitung der [Prozess](../../../analysis-services/xmla/xml-elements-commands/process-element-xmla.md) Element.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<Process>  
...  
   <Type>...</Type>  
...  
</Process>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Description|  
|--------------------|-----------------|  
|Datentyp und -länge|Zeichenfolge (Enumeration)|  
|Standardwert|InclusionThresholdSetting|  
|Cardinality|1-1: Erforderliches Element, das nur einmal auftritt.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|[Verarbeiten](../../../analysis-services/xmla/xml-elements-commands/process-element-xmla.md)|  
|Untergeordnete Elemente|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zur Verarbeitung verfügbaren Optionen auf Objekte in einer Instanz von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], finden Sie unter [Verarbeiten eines mehrdimensionalen Modells &#40; Analysis Services &#41; ](../../../analysis-services/multidimensional-models/processing-a-multidimensional-model-analysis-services.md).  
  
 Der Wert des **Type** -Elements ist auf eine der in der folgenden Tabelle aufgelisteten Zeichenfolgen beschränkt.  
  
|value|Description|  
|-----------|-----------------|  
|*"ProcessFull"*|Löscht alle Daten im betroffenen Objekt und verarbeitet dann das betroffene Objekt.|  
|*"Processadd"*|Fügt dem betroffenen Objekt neue Daten hinzu.|  
|*ProcessUpdate*|Aktualisiert die Daten im betroffenen Objekt.|  
|*ProcessIndexes*|Erstellt Indizes und Aggregationen im betroffenen Objekt oder erstellt diese neu.|  
|*ProcessScriptCache*|Wenn der Cube verarbeitet wird, erstellt der Server den MDX-Skriptcache neu. Wenn nicht, wird ein Fehler ausgelöst.<br /><br /> **Hinweis** Gilt nur für Cube.|  
|*ProcessData*|Verarbeitet Daten nur im betroffenen Objekt.|  
|*ProcessDefault*|Erkennt den Status des betroffenen Objekts und führt die geeignete Verarbeitungsoption am betroffenen Objekt durch, um eine vollständige Optimierung des Objekts zu erreichen und den Status der vollständigen Verarbeitung zurückzugeben.|  
|*ProcessClear*|Löscht die Daten im betroffenen Objekt und allen verknüpften Objekten.|  
|*ProcessStructure*|Verarbeitet nur die Struktur des betroffenen Objekts.|  
|*' ProcessClearStructureOnly '*|Löscht Daten nur aus dem betroffenen Objekt.|  
  
## <a name="see-also"></a>Siehe auch  
 [Datenbankeigenschaften &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
