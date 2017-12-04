---
title: Beginnen der Kreisdiagrammwerte an der Kreisoberseite (Berichts-Generator und SSRS) | Microsoft-Dokumentation
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
ms.assetid: d0e6fb59-ca4e-4d70-97cb-0ad183da21d3
caps.latest.revision: "7"
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: f1afb95b67f70659bc00a9c2329ebf437de34db0
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2017
---
# <a name="start-pie-chart-values-at-the-top-of-the-pie-report-builder-and-ssrs"></a>Beginnen der Kreisdiagrammwerte an der Kreisoberseite (Berichts-Generator und SSRS)
Standardmäßig beginnt bei Kreisdiagrammen in paginierten [!INCLUDE[ssRSnoversion_md](../../includes/ssrsnoversion-md.md)] -Berichten der erste Wert im Dataset bei 90 Grad zur Oberseite des Kreises versetzt. 

![Berichts-Generator-Kreisdiagramm-beginnt-bei-90](../../reporting-services/media/report-builder-pie-chart-start-at-90.png)

*Die Diagrammwerte beginnen bei 90 Grad.*

Sie können den ersten Wert aber auch ganz oben anordnen. 

![Berichts-Generator-Kreisdiagramm-Beginn-oben](../../reporting-services/media/report-builder-pie-chart-start-at-top.png)

*Die Diagrammwerte beginnen an der Kreisoberseite.*
  
## <a name="to-start-the-pie-chart-at-the-top-of-the-pie"></a>So beginnen Sie das Kreisdiagramm an der Kreisoberseite  
  
1.  Klicken Sie auf den Kreis selbst.  
  
2.  Zum Anzeigen des Bereichs **Eigenschaften** klicken Sie auf der Registerkarte **Ansicht** auf **Eigenschaften**.  
  
3.  Ändern Sie im Bereich **Eigenschaften** unter **Benutzerdefinierte Attribute**den Eintrag **PieStartAngle** von **0** in **270**.  
  
4.  Klicken Sie auf **Ausführen** , um den Bericht in der Vorschau anzuzeigen.  
  
 Der erste Wert beginnt jetzt an der Kreisdiagrammoberseite.  
  
## <a name="see-also"></a>Siehe auch  
 [Formatieren eines Diagramms &#40;Berichts-Generator und SSRS&#41;](../../reporting-services/report-design/formatting-a-chart-report-builder-and-ssrs.md)   
 [Kreisdiagramme &#40;Berichts-Generator und SSRS&#41;](../../reporting-services/report-design/pie-charts-report-builder-and-ssrs.md)  
  
  
