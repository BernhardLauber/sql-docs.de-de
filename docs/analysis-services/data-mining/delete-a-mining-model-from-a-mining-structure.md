---
title: "Löschen eines Miningmodells aus einer Miningstruktur | Microsoft Docs"
ms.custom: 
ms.date: 03/04/2017
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
helpviewer_keywords:
- mining structures [Analysis Services], mining models
- deleting mining models
- removing mining models
- mining models [Analysis Services], deleting
ms.assetid: 9ab1506b-856e-4762-a663-5adf15ac71e3
caps.latest.revision: "29"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 470e1d74434261b08c47f93c060c4ac4da143cb2
ms.sourcegitcommit: f1a6944f95dd015d3774a25c14a919421b09151b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2017
---
# <a name="delete-a-mining-model-from-a-mining-structure"></a>Löschen eines Miningmodells aus einer Miningstruktur
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]Löschen von Miningmodellen mit Data Mining-Designer mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], oder mithilfe von DMX-Anweisungen.  
  
### <a name="delete-a-mining-model-using-sql-server-data-tools"></a>Löschen eines Miningmodells mit SQL Server-Datentools  
  
1.  Wählen Sie die Registerkarte **Miningmodelle** in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aus.  
  
2.  Klicken Sie mit der rechten Maustaste auf das zu löschende Modell, und anschließend auf **Löschen**.  
  
     Das Dialogfeld **Objekte löschen** wird angezeigt.  
  
3.  Klicken Sie auf **OK**.  
  
### <a name="delete-a-mining-model-using-sql-server-management-studio"></a>Löschen eines Miningmodells mit SQL Server Management Studio  
  
1.  Öffnen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank, die das Modell enthält.  
  
2.  Erweitern Sie **Miningstrukturen**und anschließend **Miningmodelle**.  
  
3.  Klicken Sie mit der rechten Maustaste auf das zu löschende Modell, und anschließend auf **Löschen**.  
  
     Durch Löschen des Modells werden nicht die Trainingsdaten, sondern nur die Metadaten und alle Muster gelöscht, die beim Trainieren des Modells erstellt wurden.  
  
### <a name="delete-a-mining-model-using-dmx"></a>Löschen eines Miningmodells mit DMX  
  
-   [DROP MINING MODEL &#40;DMX&#41;](../../dmx/drop-mining-model-dmx.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Miningmodelltasks und Anweisungen](../../analysis-services/data-mining/mining-model-tasks-and-how-tos.md)  
  
  
