---
title: DefaultDetails-Element (CSDLBI) | Microsoft Docs
ms.custom: 
ms.date: 03/07/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
applies_to: SQL Server 2016 Preview
ms.assetid: 05a08baa-23cc-4011-9c2e-f60a20bb87da
caps.latest.revision: "13"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 8010e9c0412b50c8d65a67c87c176bff02d1a887
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2018
---
# <a name="defaultdetails-element-csdlbi"></a>DefaultDetails-Element (CSDLBI)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Das DefaultDetails-Element stellt eine Liste mit Eigenschaftsverweisen, die zusammen den "Standardfeldsatz" von Spalten in der Tabelle zu definieren. Jede Eigenschaft kann nur auf ein Measure oder auf eine Spalte verweisen.  
  
## <a name="elements-and-attributes"></a>Elemente und Attribute  
 In der folgenden Tabelle sind die Elemente und Attribute aufgeführt, die das DefaultDetails-Element definieren.  
  
|Name|Ist erforderlich|Description|  
|----------|-----------------|-----------------|  
|DefaultDetailsPosition|nein|Eine positive ganze Zahl, die das Vorhandensein und die Position in der Auflistung angibt.|  
  
## <a name="example"></a>Beispiel  
 **Tabellarisch**  
  
 Im folgenden Beispiel wird in CSDLBI, Version 1.1, ein Auszug aus dem AdventureWorks-Beispieldatenmodell dargestellt. Es ist nur eine Standardspalte für die Tabelle Employees festgelegt (Title). Für die Tabelle Produkte wurden jedoch drei Spalten als Standardfeldsatz definiert.  
  
```  
  
<EntityType   
    Name="DimEmployee">  
....  
   <bi:DefaultDetails>  
      <bi:MemberRef Name="Title" />  
   </bi:DefaultDetails>  
.....  
<EntityType   
    Name="Products">  
.....  
   <bi:DefaultDetails>  
      <bi:MemberRef Name="Color" />  
      <bi:MemberRef Name="DealerPrice" />  
      <bi:MemberRef Name="Status" />  
   </bi:DefaultDetails>  
  
```  
  
## <a name="example"></a>Beispiel  
 **Multidimensional**  
  
 Im folgenden Beispiel wird in CSDLBI, Version 1.1, ein Auszug aus der Definition der Tabelle Bike im Contoso-Vorgangscube veranschaulicht. Diese Anmerkung gibt an, dass die Spalte Color standardmäßig angezeigt werden soll, wenn keine andere Anzeigenspalte angegeben wird.  
  
```  
  
<EntityType Name="Bike">  
   <Key>  
   <PropertyRef Name="RowNumber" />  
   </Key>  
....  
<bi:EntityType>  
   <bi:DisplayKey>  
      <bi:MemberRef Name="Color" />  
   </bi:DisplayKey>  
   <bi:DefaultDetails>  
      <bi:MemberRef Name="Color" />  
   </bi:DefaultDetails>  
   <bi:SortMembers>  
      <bi:MemberRef Name="Color" />  
   </bi:SortMembers>  
....  
</bi:EntityType>  
</EntityType>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Informationen zum tabellarischen Objektmodell auf Kompatibilität Ebenen 1050 bis 1103](../../../analysis-services/tabular-model-programming-compatibility-levels-1050-1103/representation/understanding-tabular-object-model-at-levels-1050-through-1103.md)   
 [CSDLBI-Konzepte](../../../analysis-services/tabular-model-programming-compatibility-levels-1050-1103/csdlbi-concepts.md)  
  
  
