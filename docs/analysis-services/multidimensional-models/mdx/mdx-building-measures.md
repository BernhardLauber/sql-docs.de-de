---
title: Erstellen von Measures in MDX | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0347835-4983-4d26-acbb-6c8fae7992bd
caps.latest.revision: "6"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 5d1e4e637d3cee754573c2d59776d7241c89d2bf
ms.sourcegitcommit: f1a6944f95dd015d3774a25c14a919421b09151b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2017
---
# <a name="mdx-building-measures"></a>MDX-Erstellen von Measures
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]In MDX (Multidimensional Expressions), ist ein Measure ein benannter DAX-Ausdruck, der durch Berechnen des Ausdrucks, um einen Wert in einem tabellarischen Modell zurückzugeben aufgelöst wird. Diese einfach klingende Definition hat immense Auswirkungen. Die Erstellung und Verwendung von Measures in einer MDX-Abfrage eröffnet umfassende Änderungsmöglichkeiten für Tabellendaten.  
  
> [!WARNING]  
>  Measures können nur in tabellarischen Modellen definiert werden. Wenn die Datenbank auf den mehrdimensionalen Modus festgelegt ist, tritt beim Erstellen eines Measures ein Fehler auf.  
  
 Mit dem WITH-Schlüsselwort können Sie ein Measure erstellen, das als Teil einer MDX-Abfrage definiert ist und deren Bereich daher auf die Abfrage beschränkt ist. Anschließend können Sie das Measure in einer SELECT-Anweisung von MDX verwenden. Bei dieser Vorgehensweise kann das mit dem WITH-Schlüsselwort erstellte berechnete Element geändert werden, ohne dass die SELECT-Anweisung davon beeinflusst wird. In MDX wird auf das Measure jedoch auf andere Weise als in DAX-Ausdrücken verwiesen. Zum Verweisen auf das Measure benennen Sie es als Mitglied der [Measures]-Dimension, wie im folgenden MDX-Beispiel dargestellt:  
  
```  
with measure  'Sales Territory'[Total Sales Amount] = SUM('Internet Sales'[Sales Amount]) + SUM('Reseller Sales'[Sales Amount])  
select measures.[Total Sales Amount] on columns  
     ,NON EMPTY [Date].[Calendar Year].children on rows  
from [Model]  
  
```  
  
 Nach der Ausführung werden die folgenden Daten zurückgegeben:  
  
||Total Sales Amount||  
|-|------------------------|-|  
|2001|11331808.96||  
|2002|30674773.18||  
|2003|41993729.72||  
|2004|25808962.34||  
  
## <a name="see-also"></a>Siehe auch  
 [CREATE MEMBER-Anweisung &#40;MDX&#41;](../../../mdx/mdx-data-definition-create-member.md)   
 [MDX-Funktionsreferenz &#40;MDX&#41;](../../../mdx/mdx-function-reference-mdx.md)   
 [SELECT-Anweisung &#40; MDX &#41;](../../../mdx/mdx-data-manipulation-select.md)  
  
  
