---
title: Tabellarische Modelle (SSAS) | Microsoft Docs
ms.custom: 
ms.date: 03/02/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: tabular-models
ms.reviewer: 
ms.suite: sql
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80027288-c203-4667-a3e1-40fa572b4975
caps.latest.revision: "17"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Active
ms.openlocfilehash: 1d770b114a708301f884de76d7c6a4cc39227195
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="tabular-modeling-ssas"></a>Tabellenmodellierung (SSAS)
  Tabellarische Modelle sind Analysis Services-Datenbanken, die im In-Memory- oder im DirectQuery-Modus ausgeführt werden. Sie greifen in relationalen Back-End-Datenquellen direkt auf Daten zu.  
  
 In-Memory ist die Standardeinstellung. Das In-Memory-Analysemodul nutzt modernste Komprimierungsalgorithmen und einen Multithreaded-Abfrageprozessor, um Berichterstellungsclientanwendungen wie Microsoft Excel und Microsoft [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)]schnellen Zugriff auf Objekte und Daten tabellarischer Modelle zu gewähren.  
  
 DirectQuery ist ein alternativer Abfragemodus für Modelle, die für den Arbeitsspeicher zu groß sind. Er eignet sich auch, wenn aufgrund von Datenflüchtigkeit keine angemessene Verarbeitungsstrategie möglich ist. In dieser Version erzielt DirectQuery eine größere Parität mit In-Memory-Modellen, indem Folgendes unterstützt wird: zusätzliche Datenquellen, die Verarbeitung von berechneten Tabellen und Spalten in einem DirectQuery-Modell, die Sicherheit auf Zeilenebene über DAX-Ausdrücke, die die Back-End-Datenbank erreichen, sowie die Optimierung von Abfragen, die zu einem höheren Durchsatz als in früheren Versionen führen.
  
 Tabellarische Modelle werden in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] unter Verwendung der Projektvorlage für tabellarische Modelle erstellt. Diese bietet eine Entwurfsoberfläche zum Erstellen von Modellen, Tabellen, Beziehungen und DAX-Ausdrücken. Sie können Daten aus mehreren Quellen importieren und das Modell erweitern, indem Sie Beziehungen, berechnete Tabellen und Spalten, Measures, KPIs, Hierarchien und Übersetzungen hinzufügen.  
  
 Anschließend können die Modelle in einer Instanz von Analysis Services bereitgestellt werden, die für den tabellarischen Servermodus konfiguriert wurde, in dem Clientanwendungen zur Berichterstellung eine Verbindung mit den Modellen herstellen können. Bereitgestellte Modelle können genauso wie mehrdimensionale Modelle in SQL Server Management Studio verwaltet werden. Sie können partitioniert werden, um die Verarbeitung zu optimieren, und durch die Verwendung der rollenbasierten Sicherheit bis auf Zeilenebene gesichert werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Tabellenmodelllösungen &#40;SSAS – tabellarisch&#41;](../../analysis-services/tabular-models/tabular-model-solutions-ssas-tabular.md) – in den Themen in diesem Abschnitt wird das Erstellen und Bereitstellen von Projektmappen für tabellarische Modelle beschrieben.
  
 [Tabellarische Modelldatenbanken &#40;SSAS – tabellarisch&#41;](../../analysis-services/tabular-models/tabular-model-databases-ssas-tabular.md) – in den Themen in diesem Abschnitt wird das Verwalten von bereitgestellten Projektmappen für tabellarische Modelle beschrieben.
  
 [Zugriff auf Daten im tabellarischen Modell](../../analysis-services/tabular-models/tabular-model-data-access.md) – in den Themen in diesem Abschnitt wird das Herstellen von Verbindungen mit bereitgestellten Projektmappen für tabellarische Modelle beschrieben.
  
## <a name="see-also"></a>Siehe auch  
 [Neuigkeiten in Analysis Services](../../analysis-services/what-s-new-in-analysis-services.md)   
 [Comparing Tabular and Multidimensional Solutions &#40;SSAS&#41; (Vergleichen von tabellarischen und mehrdimensionalen Lösungen (SSAS))](../../analysis-services/comparing-tabular-and-multidimensional-solutions-ssas.md)   
 [In Analysis Services verwendete Tools und Anwendungen](../../analysis-services/tools-and-applications-used-in-analysis-services.md)   
 [DirectQuery-Modus &#40;SSAS – tabellarisch&#41;](../../analysis-services/tabular-models/directquery-mode-ssas-tabular.md)   
 [Kompatibilitätsgrad für tabellarische Modelle in Analysis Services](../../analysis-services/tabular-models/compatibility-level-for-tabular-models-in-analysis-services.md)  
  
  
