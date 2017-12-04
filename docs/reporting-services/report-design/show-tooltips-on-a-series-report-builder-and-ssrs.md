---
title: "Anzeigen von QuickInfos für eine Reihe (Berichts-Generator und SSRS) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c9606ff-e1c3-4cf7-a4e7-bb16f1a9e8ab
caps.latest.revision: "8"
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.workload: On Demand
ms.openlocfilehash: 669d6fdc4560d40b0cb3cfb165c4622a0f6b4eb1
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2017
---
# <a name="show-tooltips-on-a-series-report-builder-and-ssrs"></a>Anzeigen von QuickInfos für eine Reihe (Berichts-Generator und SSRS)
  Sie können den einzelnen Datenpunkten in einem Diagramm QuickInfos hinzufügen, um Informationen zum Datenpunkt anzuzeigen, beispielsweise den Gruppennamen, den Wert des Datenpunkts oder den Prozentsatz des Datenpunkts in Bezug auf die Gesamtreihe. Diese Informationen werden angezeigt, wenn Benutzer mit dem Cursor auf den Datenpunkt in einem gerenderten paginierten Bericht zeigen.  
  
 Einer berechneten Reihe können keine QuickInfos hinzugefügt werden.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="to-specify-a-tooltip-on-each-data-point"></a>So geben Sie eine QuickInfo für die Datenpunkte an  
  
1.  Klicken Sie mit der rechten Maustaste auf die Reihe, oder klicken Sie mit der rechten Maustaste auf das Feld im Bereich **Werte** , und klicken Sie auf **Reiheneigenschaften**.  
  
2.  Klicken Sie auf **Reihendaten** , und geben Sie für die **ToolTip** -Eigenschaft eine Zeichenfolge oder einen Ausdruck ein. Sie können alle diagrammspezifischen Schlüsselwörter zur Darstellung anderer Elemente im Diagramm verwenden. Weitere Informationen finden Sie unter [Formatieren von Datenpunkten in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](../../reporting-services/report-design/formatting-data-points-on-a-chart-report-builder-and-ssrs.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Formatieren von Datenpunkten in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](../../reporting-services/report-design/formatting-data-points-on-a-chart-report-builder-and-ssrs.md)   
 [Ändern des Texts eines Legendenelements (Berichts-Generator und SSRS)](../../reporting-services/report-design/chart-legend-change-item-text-report-builder.md)   
 [Formatieren von Reihenfarben in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](../../reporting-services/report-design/formatting-series-colors-on-a-chart-report-builder-and-ssrs.md)   
 [Hinzufügen einer Drillthroughaktion für einen Bericht (Berichts-Generator und SSRS)](../../reporting-services/report-design/add-a-drillthrough-action-on-a-report-report-builder-and-ssrs.md)  
  
  
