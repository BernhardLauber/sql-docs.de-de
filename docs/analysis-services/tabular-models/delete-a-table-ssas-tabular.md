---
title: "Löschen einer Tabelle (SSAS – tabellarisch) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
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
ms.assetid: be4ed45f-fde3-466c-9869-49bd3ddb505e
caps.latest.revision: "9"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 36438a8871c90ac00bcaf0e16ca184b4d9286a81
ms.sourcegitcommit: f1a6944f95dd015d3774a25c14a919421b09151b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2017
---
# <a name="delete-a-table-ssas-tabular"></a>Löschen einer Tabelle (SSAS – tabellarisch)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]Im Modell-Designer können Sie Tabellen in der arbeitsbereichsdatenbank des Modells löschen, die Sie nicht mehr benötigen. Das Löschen einer Tabelle wirkt sich nicht auf die ursprünglichen Quelldaten aus, sondern nur auf die importierten Daten, mit denen Sie gearbeitet haben. Das Löschen einer Tabelle kann nicht rückgängig gemacht werden.  
  
### <a name="to-delete-a-table"></a>So löschen Sie eine Tabelle  
  
-   Klicken Sie unten im Modell-Designer mit der rechten Maustaste auf die Registerkarte der Tabelle, die gelöscht werden soll, und klicken Sie dann auf **Löschen**.  
  
## <a name="considerations-when-deleting-tables"></a>Überlegungen beim Löschen von Tabellen  
  
-   Wenn Sie eine Tabelle löschen, wird die gesamte Registerkarte gelöscht, auf der sich die Tabelle befand.  
  
-   Wenn dieser Tabelle Measures zugeordnet waren, wird die Definition des Measures ebenfalls gelöscht.  
  
-   Wenn Sie mithilfe dieser Tabelle berechnete Spalten erstellt haben, werden auch die Spalten in dieser Tabelle gelöscht. Berechnete Spalten in anderen Tabellen, die Spalten aus der gelöschten Tabelle verwenden, verursachen einen Fehler.  
  
## <a name="see-also"></a>Siehe auch  
 [Tabellen und Spalten &#40;SSAS – tabellarisch&#41;](../../analysis-services/tabular-models/tables-and-columns-ssas-tabular.md)  
  
  
