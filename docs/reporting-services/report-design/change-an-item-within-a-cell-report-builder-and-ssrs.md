---
title: "Ändern eines Elements in einer Zelle (Berichts-Generator und SSRS) | Microsoft-Dokumentation"
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
ms.assetid: 91a54778-8929-41f9-bb4c-826cec636be4
caps.latest.revision: "8"
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: cf872e237310d4dfc9c68fd5a6bd25118a626aec
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2017
---
# <a name="change-an-item-within-a-cell-report-builder-and-ssrs"></a>Ändern eines Elements in einer Zelle (Berichts-Generator und SSRS)
In paginierten [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Berichten kann nur ein Nichtcontainerelement, z.B. ein Textfeld, eine Zeile oder ein Bild, durch ein neues Berichtselement ersetzt werden. Sie können beispielsweise eine Tabelle in ein Textfeld ziehen, um das Textfeld durch eine Tabelle zu ersetzen.  
  
 Enthält die Zelle ein Containerelement, wie z. B. ein Rechteck, eine Liste, eine Tabelle oder eine Matrix, wird das neue Element zum enthaltenen Element hinzugefügt, anstatt es zu ersetzen. Um ein Containerelement durch ein neues Element zu ersetzen, löschen Sie den Container. Beim Löschen des Containerelements wird dafür ein Textfeld eingefügt, das Sie durch ein anderes Element ersetzen können.  
  
 Standardmäßig enthalten alle Zellen in einem Tabellen-, Matrix- oder Listendatenbereich ein Textfeld.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="to-change-an-item-within-a-cell"></a>So ändern Sie ein Element in einer Zelle  
  
-   Klicken Sie auf der Registerkarte **Einfügen** in der Gruppe **Datenbereiche** oder **Berichtselemente** auf das Element, das Sie dem Bericht hinzufügen möchten, und klicken Sie dann auf den Bericht. Das Element wird dem Bericht hinzugefügt.  
  
> [!NOTE]  
>  Das Dialogfeld **Bildeigenschaften** wird geöffnet, wenn Sie ein Bildberichtselement in eine Zelle ziehen, in der Sie Eigenschaften wie die Quelle des Bilds festlegen können, bevor das Bild der Zelle hinzugefügt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Bilder, Textfelder, Rechtecke und Linien &#40;Berichts-Generator und SSRS&#41;](../../reporting-services/report-design/images-text-boxes-rectangles-and-lines-report-builder-and-ssrs.md)   
 [Tabellen, Matrizen und Listen &#40;Berichts-Generator und SSRS&#41;](../../reporting-services/report-design/tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
