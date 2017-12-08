---
title: Member-Element (CSDLBI) | Microsoft Docs
ms.custom: 
ms.date: 03/07/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: tabular-models
ms.reviewer: 
ms.suite: sql
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to: SQL Server 2016 Preview
ms.assetid: 1ba225f5-3867-4aae-a519-e3c277688d1e
caps.latest.revision: "6"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: a97b171f1205b2718b5786ae92fce826c2c6316c
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="member-element-csdlbi"></a>Member-Element (CSDLBI)
  Das Member-Element ist ein komplexer Typ, der als Basis für andere Elemente dient.  
  
 Die zugehörigen Attribute können in Spalten, Measures, Navigationseigenschaften, Hierarchien und Ebenen angezeigt werden.  
  
## <a name="elements-and-attributes"></a>Elemente und Attribute  
 In der folgenden Tabelle sind die Elemente und Attribute aufgeführt, die das Member-Element definieren.  
  
|Name|Ist erforderlich|Beschreibung|  
|----------|-----------------|-----------------|  
|Name||Der Name für das Element (Spalte, Measure, Navigationseigenschaft, Hierarchie oder Ebene), das von der Implementierung des TMember-Typs definiert wird.|  
|Beschriftung|ja|Der Anzeigename für das Element.|  
|ContextualNameRule|ja|Das Namensformat, das verwendet wird, um Elemente zu unterscheiden. Die Inhalte dieses Attributs werden vom einfachen Typ ContextualNameRule definiert.|  
|Hidden||Ein boolescher Wert, der angibt, ob das Element für den Client ausgeblendet wird.<br /><br /> Der Standardwert lautet false und gibt an, dass Spalten im Client sichtbar sind.|  
|ReferenceName||Der Bezeichner, mit dem in einer DAX-Abfrage auf das Element verwiesen wird. Wenn dieses Attribut weggelassen wird, wird der Feldname verwendet.|  
  
## <a name="contextualnamerule-element"></a>ContextualNameRule-Element  
 Mit diesem einfachen Typ wird das Namensformat definiert, das verwendet wird, um Elemente zu unterscheiden.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Keine|Verwenden Sie den Attributnamen.|  
|Kontext|Verwenden Sie den Namen der eingehenden Beziehung.|  
|Merge|Verketten Sie den Namen der eingehenden Beziehung und den Namen der Eigenschaft.|  
  
## <a name="see-also"></a>Siehe auch  
 [Informationen zum tabellarischen Objektmodell auf Kompatibilität Ebenen 1050 bis 1103](../../../analysis-services/tabular-model-programming-compatibility-levels-1050-1103/representation/understanding-tabular-object-model-at-levels-1050-through-1103.md)  
  
  
