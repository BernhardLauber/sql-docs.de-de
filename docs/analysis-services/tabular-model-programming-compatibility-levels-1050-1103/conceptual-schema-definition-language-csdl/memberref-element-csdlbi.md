---
title: MemberRef-Element (CSDLBI) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
ms.assetid: 399aaa34-896c-48e7-aacb-18564f31b568
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 8c1bb47c2273d79e320e53b49c524112b067a2d3
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2018
---
# <a name="memberref-element-csdlbi"></a>MemberRef-Element (CSDLBI)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
Das MemberRef-Element identifiziert den Namen einer Eigenschaft, die das Ziel eines Verweises ist.  
  
## <a name="elements-and-attributes"></a>Elemente und Attribute  
 In der folgenden Tabelle sind die Elemente und Attribute aufgeführt, die das MemberRef-Element definieren.  
  
|Name|Ist erforderlich|Beschreibung|  
|----------|-----------------|-----------------|  
|Name|ja|De Name der Eigenschaft, die in einem MemberRef-Element enthalten ist.|  
  
## <a name="memberrefs-element"></a>MemberRefs-Element  
 MemberRefs ist ein komplexer Typ, der eine Auflistung von Elementen definiert, die jeweils in einem MemberRef-Element enthalten sind.  
  
 In der folgenden Tabelle sind die Elemente und Attribute des MemberRefs-Typs aufgeführt.  
  
|Name|Ist erforderlich|Beschreibung|  
|----------|-----------------|-----------------|  
|MemberRef|ja|Eine Zeichenfolge, die den Parameterverweis enthält.|  
  
## <a name="example"></a>Beispiel  
 **Tabellarische**  
  
 Im folgenden Beispiel wird in CSDLBI, Version 1.1, ein Teil des AdventureWorks-Beispieldatenmodells dargestellt, das die Products-Tabelle definiert. Hier wird das MemberRef-Element für alle Spalten verwendet, die im Standardfeldsatz für das Modell enthalten sind.  
  
```  
  
<bi:EntityType>  
   <bi:DefaultDetails>  
     <bi:MemberRef Name="Color" />  
     <bi:MemberRef Name="DealerPrice" />  
     <bi:MemberRef Name="Status" />  
   </bi:DefaultDetails>  
  
```  
  
## <a name="example"></a>Beispiel  
 **Mehrdimensionale**  
  
 Im folgenden Beispiel wird in CSDLBI, Version 1.1, ein Teil des Contoso-Vorgangscube dargestellt, der die Bike-Tabelle definiert. In diesem Beispiel wird ein MemberRef-Element verwendet, um den Namen der Spalte angeben, die in Berichten als Standardfeldsatz verwendet wird. Mithilfe eines weiteren MemberRef-Elements wird auf die Spalte verwiesen, die die Sortierreihenfolge bereitstellt.  
  
```  
  
<bi:DefaultDetails>  
   <bi:MemberRef Name="Color" />  
</bi:DefaultDetails>  
  
<bi:SortMembers>  
   <bi:MemberRef Name="Color" />  
</bi:SortMembers>  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Referenz für BI-Anmerkungen zu CSDL](../../../analysis-services/tabular-model-programming-compatibility-levels-1050-1103/conceptual-schema-definition-language-csdl/technical-reference-for-bi-annotations-to-csdl.md)  
  
  
