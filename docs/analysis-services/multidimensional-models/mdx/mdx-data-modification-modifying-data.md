---
title: "Ändern von Daten (MDX) | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: data-mining
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- modifying data [MDX]
- Multidimensional Expressions [Analysis Services], data modifications
- MDX [Analysis Services], data modifications
- data modifications [MDX]
ms.assetid: 363b662c-b839-4971-bbd7-1842f73ce141
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: fcf75945b77c8ced0321089805f7e23fc7223821
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2018
---
# <a name="mdx-data-modification---modifying-data"></a>MDX - Datenänderung: Ändern von Daten
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
MDX (Multidimensional Expressions) kann nicht nur zum Abrufen und Verwalten von Daten aus Dimensionen und Cubes, sondern auch zum Aktualisieren oder *Rückschreiben* von Dimensions- und Cubedaten verwendet werden. Diese Updates können temporär (wie bei einer spekulativen oder "Was-wäre-wenn-Analyse") oder permanent sein (dies ist der Fall, wenn Änderungen aufgrund einer Datenanalyse vorgenommen werden müssen).  
  
 Updates von Daten sind auf Dimensions- oder Cubeebene möglich.  
  
 **Rückschreiben von Dimensionen**  
 Die [ALTER CUBE-Anweisung (MDX)](../../../mdx/mdx-data-definition-alter-cube.md) wird verwendet, um die Daten einer Dimension mit aktiviertem Schreibzugriff zu ändern, und die [REFRESH CUBE-Anweisung (MDX)](../../../mdx/mdx-data-definition-refresh-cube.md) wird verwendet, um das Löschen, Erstellen oder Aktualisieren von Attributwerten zu berücksichtigen. Mit der ALTER CUBE-Anweisung können Sie auch komplexe Operationen ausführen, so z. B. das Löschen einer gesamten Unterstruktur in einer Hierarchie oder das Heraufstufen der untergeordneten Elemente eines gelöschten Elements.  
  
 **Cuberückschreiben**  
 Sie verwenden die [UPDATE CUBE](../../../mdx/mdx-data-manipulation-update-cube.md) -Anweisung dazu, Änderungen an einem Cube mit aktiviertem Schreibzugriff vorzunehmen. Mit der UPDATE CUBE-Anweisung können Sie ein Tupel mit einem bestimmten Wert aktualisieren. Die [REFRESH CUBE-Anweisung (MDX)](../../../mdx/mdx-data-definition-refresh-cube.md) wird zum Aktualisieren von Daten in einer Clientsitzung mit aktualisierten Daten vom Server verwendet.  
  
 Weitere Informationen finden Sie unter [Verwenden von Cuberückschreiben &#40;MDX&#41;](../../../analysis-services/multidimensional-models/mdx/mdx-data-modification-using-cube-writebacks.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlegendes zu MDX-Abfrage &#40; Analysis Services &#41;](../../../analysis-services/multidimensional-models/mdx/mdx-query-fundamentals-analysis-services.md)  
  
  
