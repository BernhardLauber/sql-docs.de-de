---
title: Erweitern von OLAP durch personalisierungen | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: multidimensional-models
ms.reviewer: 
ms.suite: sql
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to: SQL Server 2016 Preview
helpviewer_keywords: Analysis Services, extensibility
ms.assetid: 348e49fc-4390-43c1-9b6c-61b386ff4373
caps.latest.revision: "10"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 7ec3cf33f788c6e208919d9d86a2ac74de9938bc
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="extending-olap-through-personalizations"></a>Erweitern von OLAP durch Personalisierungen
  Analysis Services stellt viele systeminterne Funktionen für die Verwendung mit den Sprachen MDX (Multidimensional Expressions) und Data Mining Extensions (DMX). Diese Funktionen sind ebenso für herkömmliche statistische Berechnungen wie zum Durchlaufenden der Elemente einer Hierarchie geeignet. Wie bei jedem komplexen und robusten Produkt ist gibt es jedoch immer die Bestrebung, die Funktionalität des Produkts zu erweitern.  
  
 Deshalb können Sie einer Instanz des Diensts mithilfe der Analysis Services Assemblys und Personalisierungserweiterungen hinzufügen, um die Geschäftsanforderungen zu erfüllen, wenn die Standardfunktionalität einmal nicht ausreichen sollte.  
  
## <a name="assemblies"></a>Assemblys  
 Assemblys können Sie die Geschäftsfunktionalität von MDX und DMX erweitern. Sie integrieren die gewünschte Funktionalität in eine Bibliothek, z. B. eine DLL (Dynamic Link Library), und fügen dann die Bibliothek als Assembly einer Instanz von Analysis Services oder einer Analysis Services-Datenbank hinzu. Die öffentlichen Methoden in der Bibliothek werden dann als benutzerdefinierte Funktionen für MDX- und DMX-Ausdrücke, Prozeduren, Berechnungen, Aktionen und Clientanwendungen verfügbar gemacht.  
  
## <a name="personalized-extensions"></a>Personalisierungserweiterungen  
 SQL Server Analysis Services-Personalisierungserweiterungen sind die Grundlage für das Konzept der Implementierung einer Plug-In-Architektur. Analysis Services-Personalisierungserweiterungen stellen eine einfache und elegante Modifikation der vorhandenen Architektur der verwalteten Assembly dar. Sie werden im Analysis Services-<xref:Microsoft.AnalysisServices.AdomdServer>-Objektmodell, in der MDX-Syntax (Multidimensional Expressions) und in den Schemarowsets zur Verfügung gestellt.  
  
## <a name="see-also"></a>Siehe auch  
 [Mehrdimensionales Modell Assemblys-Verwaltung](../../../analysis-services/multidimensional-models/multidimensional-model-assemblies-management.md)   
 [Personalisierungserweiterungen für Analysis Services](../../../analysis-services/multidimensional-models/extending-olap/analysis-services-personalization-extensions.md)  
  
  
