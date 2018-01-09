---
title: Definieren und Identifizieren von Objekten (XMLA) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
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
helpviewer_keywords:
- objects [XML for Analysis]
- identifying objects [XML for Analysis]
- XML for Analysis, objects
- object references [XML for Analysis]
- object identifiers [XML for Analysis]
- object definitions [XML for Analysis]
- XMLA, objects
ms.assetid: 43b65f6d-0123-4556-81f0-c7a0b84361e5
caps.latest.revision: "13"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: eaea16c728177c1a2672bfd04075079598e920c9
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2018
---
# <a name="defining-and-identifying-objects-xmla"></a>Definieren und Identifizieren von Objekten (XMLA)
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]Objekte werden in XML für Analysis (XMLA) Befehle mithilfe von Objektbezeichnern und Objektverweisen identifiziert und mithilfe von Analysis Services Scripting Language (ASSL) Elemente XMLA-Befehle definiert.  
  
## <a name="object-identifiers"></a>Objektbezeichner  
 Ein Objekt wird mithilfe den eindeutigen Bezeichner des Objekts gemäß der Definition in einer Instanz von identifiziert [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]. Objektbezeichner können entweder explizit angegeben oder durch die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Instanz bestimmt werden, wenn [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] das Objekt erstellt. Können Sie die [Discover](../../analysis-services/xmla/xml-elements-methods-discover.md) Methode zum Abrufen der Objektbezeichner für nachfolgende **Discover** oder [Execute](../../analysis-services/xmla/xml-elements-methods-execute.md) Methodenaufrufe.  
  
## <a name="object-references"></a>Objektverweise  
 Zahlreiche XMLA-Befehle wie z. B. [löschen](../../analysis-services/xmla/xml-elements-commands/delete-element-xmla.md) oder [Prozess](../../analysis-services/xmla/xml-elements-commands/process-element-xmla.md), verwenden Sie einen Objektverweis zum Verweisen auf ein Objekt auf eindeutige Weise. Ein Objektverweis enthält den Objektbezeichner des Objekts, für das ein Befehl ausgeführt wird, sowie die Objektbezeichner der Vorgänger dieses Objekts. Beispielsweise enthält der Objektverweis für eine Partition den Objektbezeichner der Partition sowie die Objektbezeichner der übergeordneten Measuregruppe, des übergeordneten Cubes und der übergeordneten Datenbank dieser Partition.  
  
## <a name="object-definitions"></a>Objektdefinitionen  
 Die [erstellen](../../analysis-services/xmla/xml-elements-commands/create-element-xmla.md) und [Alter](../../analysis-services/xmla/xml-elements-commands/alter-element-xmla.md) Befehle in XMLA erstellen bzw. ändern, Objekte auf einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instanz. Die Definitionen für diese Objekte werden durch dargestellt ein [ObjectDefinition](../../analysis-services/xmla/xml-elements-properties/objectdefinition-element-xmla.md) Element, das Elemente aus ASSL enthält. Objektbezeichner können explizit für alle Haupt- und nebenobjekte angegeben werden, mithilfe der [ID](../../analysis-services/xmla/xml-elements-properties/id-element-xmla.md) Element. Wenn die **ID** Element nicht verwendet wird, die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instanz stellt einen eindeutigen Bezeichner, mit einer Benennungskonvention, die von dem zu identifizierenden Objekt abhängt. Weitere Informationen zur Verwendung der **erstellen** und **Alter** Befehle zum Definieren von Objekten finden Sie unter [erstellen und Ändern von Objekten &#40; XMLA &#41; ](../../analysis-services/multidimensional-models-scripting-language-assl-xmla/creating-and-altering-objects-xmla.md).  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [Object-Element &#40; XMLA &#41;](../../analysis-services/xmla/xml-elements-properties/object-element-xmla.md)   
 [ParentObject-Element &#40; XMLA &#41;](../../analysis-services/xmla/xml-elements-properties/parentobject-element-xmla.md)   
 [Source-Element &#40; XMLA &#41;](../../analysis-services/xmla/xml-elements-properties/source-element-xmla.md)   
 [Target-Element &#40; XMLA &#41;](../../analysis-services/xmla/xml-elements-properties/target-element-xmla.md)   
 [Entwickeln mit XMLA in Analysis Services](../../analysis-services/multidimensional-models-scripting-language-assl-xmla/developing-with-xmla-in-analysis-services.md)  
  
  
