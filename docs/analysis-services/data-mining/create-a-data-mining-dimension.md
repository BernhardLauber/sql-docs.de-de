---
title: Datamining-Dimension erstellen | Microsoft Docs
ms.custom: 
ms.date: 03/13/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology:
- analysis-services
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: mining structures [Analysis Services], dimensions
ms.assetid: 9f0c39e5-3516-43ab-b203-f3f6dbcff89a
caps.latest.revision: "12"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: e4b9351e6ef83e1fbfea89ffd1130db2879d7559
ms.sourcegitcommit: f1a6944f95dd015d3774a25c14a919421b09151b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2017
---
# <a name="create-a-data-mining-dimension"></a>Erstellen einer Data Mining-Dimension
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]Wenn Ihre Miningstruktur auf einem OLAP-Cube basiert, können Sie eine Dimension erstellen, die den Inhalt des Miningmodells enthält. Sie können dann die Dimension wieder in den Quellcube einbinden.  
  
 Sie können auch die Dimension durchsuchen, sie zum Untersuchen der Modellergebnisse verwenden oder die Dimension mit MDX abfragen.  
  
### <a name="to-create-a-data-mining-dimension"></a>So erstellen Sie eine Data Mining-Dimension  
  
1.  Wählen Sie im Data Mining-Designer in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]entweder die **Miningstruktur** -Registerkarte oder die **Miningmodelle** -Registerkarte aus.  
  
2.  Wählen Sie aus dem Menü **Miningmodell** die Option **Data Mining-Dimension erstellen**aus.  
  
     Das Dialogfeld **Data Mining-Dimension erstellen** wird geöffnet.  
  
3.  Wählen Sie in der **Modellname** -Liste des Dialogfelds **Data Mining-Dimension auswählen** ein OLAP-Miningmodell aus.  
  
4.  Geben Sie im Feld **Dimensionsname** einen Namen für die neue Data Mining-Dimension ein.  
  
5.  Wenn Sie einen Cube erstellen wollen, der die neue Data Mining-Dimension einbindet, wählen Sie **Cube erstellen**aus. Nachdem Sie **Cube erstellen**ausgewählt haben, können Sie einen neuen Namen für den Cube eingeben.  
  
6.  Klicken Sie auf **OK**.  
  
     Die Data Mining-Dimension wird erstellt und dem **Dimensionen** -Ordner im Projektmappen-Explorer hinzugefügt. Wenn Sie **Cube erstellen**ausgewählt haben, wird auch ein neuer Cube erstellt und dem **Cubes** -Ordner hinzugefügt.  
  
## <a name="see-also"></a>Siehe auch  
 [Tasks und Anweisungen für Miningstrukturen](../../analysis-services/data-mining/mining-structure-tasks-and-how-tos.md)  
  
  
