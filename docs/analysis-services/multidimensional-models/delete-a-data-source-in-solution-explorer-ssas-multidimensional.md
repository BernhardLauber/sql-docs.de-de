---
title: Löschen einer Datenquelle im Projektmappen-Explorer (SSAS – mehrdimensional) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: data-mining
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql13.asvs.deleteobjects.f1
helpviewer_keywords:
- data sources [Analysis Services], deleting
- deleting data sources
- removing data sources
ms.assetid: b45441ef-f909-4736-98b9-cc80d0acac99
caps.latest.revision: 46
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 480082010e78c1db2c4e90af3176b797b97f26d7
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2018
---
# <a name="delete-a-data-source-in-solution-explorer-ssas-multidimensional"></a>Löschen einer Datenquelle in Projektmappen-Explorer (SSAS – mehrdimensional)
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]Sie können ein Datenquellenobjekt, um es dauerhaft aus einem mehrdimensionalen Analysis Services-Modellprojekt zu entfernen, löschen.  
  
 In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]bilden Datenquellen die Grundlage, auf der Datenquellensichten erstellt werden. Datenquellensichten werden wiederum verwendet, um Dimensionen, Cubes und Miningstrukturen in einem Projekt oder einer Datenbank von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] zu definieren. Aus diesem Grund führt das Löschen einer Datenquelle u. U. dazu, dass andere [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Objekte in einem [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt ungültig werden. Sie sollten immer die Liste der abhängigen Objekte überprüfen, die vor dem Löschen des Objekts bereitgestellt wird.  
  
> [!IMPORTANT]  
>  Datenquellen, von denen andere Objekte abhängen, können nicht aus einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank gelöscht werden, die von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] im Onlinemodus geöffnet wurde. Sie müssen in der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank alle Objekte löschen, die von dieser Datenquelle abhängig sind, bevor Sie die Datenquelle löschen. Weitere Informationen zum Onlinemodus finden Sie unter [Connect in Online Mode to an Analysis Services Database](../../analysis-services/multidimensional-models/connect-in-online-mode-to-an-analysis-services-database.md).  
  
### <a name="to-delete-a-data-source"></a>So löschen Sie eine Datenquelle  
  
1.  Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das Projekt, oder stellen Sie eine Verbindung mit der Datenbank her, aus dem bzw. der Sie eine Datenquelle löschen möchten.  
  
2.  Erweitern Sie im **Projektmappen-Explorer**den Ordner **Datenquellen** .  
  
3.  Klicken Sie mit der rechten Maustaste auf die Datenquelle, und klicken Sie dann auf **Löschen**. Das Dialogfeld **Objekte löschen**  wird geöffnet und zeigt die Objekte an, die für ungültig erklärt werden, wenn Sie die Datenquelle löschen. Überprüfen Sie diese Liste sorgfältig, bevor Sie auf **OK** klicken, um die Datenquelle zu löschen.  
  
4.  Speichern Sie das Projekt.  
  
     Nachdem Sie eine Datenquelle aus einem [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt gelöscht haben, müssen Sie das geänderte Projekt speichern. Andernfalls erhalten Sie einen Fehler, wenn Sie das Projekt das nächste Mal öffnen, da die zugrunde liegende XML-Datei der gelöschten Datenquelle fehlt, wenn das Projekt versucht, die gelöschte Datenquelle zu laden.  
  
## <a name="see-also"></a>Siehe auch  
 [Datenquellen in mehrdimensionalen Modellen](../../analysis-services/multidimensional-models/data-sources-in-multidimensional-models.md)   
 [Unterstützte Datenquellen &#40;SSAS – mehrdimensional&#41;](../../analysis-services/multidimensional-models/supported-data-sources-ssas-multidimensional.md)  
  
  
