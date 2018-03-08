---
title: Spaltenverteilungen [Datamining] | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
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
- normal distribution type [data mining]
- uniform distribution type [data mining]
- columns [data mining], distributions
- log normal distribution type [data mining]
- continuous columns
- distributions [data mining]
ms.assetid: 87e700de-32be-4bc8-b01d-ba4ee1ab48de
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 98ba6df252c33f55aa5081ed6714c316c0ad1c4b
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2018
---
# <a name="column-distributions-data-mining"></a>Spaltenverteilungen [Data Mining]
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]können Sie Spaltenverteilungen in einer Miningstruktur definieren, um zu beeinflussen, wie Algorithmen die Daten in diesen Spalten verarbeiten, wenn Sie Miningmodelle erstellen. Für einige Algorithmen ist es hilfreich, vor dem Verarbeiten des Modells für jede kontinuierliche Spalte die Verteilung zu definieren, wenn für die Spalten bekannt ist, dass sie normal verteilte Werte enthalten. Wenn Sie die Verteilungen nicht definieren, liefern die sich ergebenden Miningmodelle möglicherweise ungenauere Vorhersagen, da die Algorithmen weniger Informationen zum Interpretieren der Daten haben.  
  
 Die in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] verfügbaren Algorithmen unterstützen folgende Verteilungstypen:  
  
 **Normal**  
 Die Werte für die kontinuierliche Spalte bilden ein Histogramm, das einer Normalverteilung folgt.  
  
 ![Histogramm mit normalverteilung](../../analysis-services/data-mining/media/normal-distribution.gif "Histogramm mit normalverteilung")  
  
 **Log Normal**  
 Die Werte für die kontinuierliche Spalte bilden ein Histogramm, in dem die Kurve am oberen Ende einen gedehnten Verlauf und am unteren Ende  einen Schrägverlauf aufweist.  
  
 ![Histogramm mit protokollnormalverteilung](../../analysis-services/data-mining/media/log-normal-distribution.gif "Histogramm mit protokollnormalverteilung")  
  
 **Uniform**  
 Die Werte für die kontinuierliche Spalte bilden eine flache Kurve, in der alle Werte gleich wahrscheinlich sind.  
  
 ![Histogramm mit gleichverteilung](../../analysis-services/data-mining/media/uniform-distribution.gif "Histogramm mit gleichverteilung")  
  
 Weitere Informationen zu den von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] bereitgestellten Algorithmen finden Sie unter [Data Mining-Algorithmen &#40;Analysis Services – Data Mining&#41;](../../analysis-services/data-mining/data-mining-algorithms-analysis-services-data-mining.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Content-Arten &#40; Datamining &#41;](../../analysis-services/data-mining/content-types-data-mining.md)   
 [Miningstrukturen &#40; Analysis Services – Datamining &#41;](../../analysis-services/data-mining/mining-structures-analysis-services-data-mining.md)   
 [Diskretisierungsmethoden &#40; Datamining &#41;](../../analysis-services/data-mining/discretization-methods-data-mining.md)   
 [Verteilungen &#40; DMX &#41;](../../dmx/distributions-dmx.md)   
 [Miningstrukturspalten](../../analysis-services/data-mining/mining-structure-columns.md)  
  
  
