---
title: "Rendering- und Ausführungsmethoden | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: reference
applies_to: SQL Server 2016 Preview
helpviewer_keywords:
- rendered reports [Reporting Services]
- reports [Reporting Services], execution options
- methods [Reporting Services], execution options
- methods [Reporting Services], rendering
ms.assetid: 12626aad-f0be-4653-87d0-60eb3a3fff78
caps.latest.revision: "36"
author: guyinacube
ms.author: asaxton
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: 14e0f7182e022d07f2b98affbd59e27cf7b91ba4
ms.sourcegitcommit: 9678eba3c2d3100cef408c69bcfe76df49803d63
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2017
---
# <a name="rendering-and-execution-methods"></a>Rendering-Methode und Execution-Methode
  Mit diesen Methoden können Sie das Ausführen und Zwischenspeichern von Elementen und das Rendern von Berichten verwalten.  
  
|Methode|Aktion|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.FlushCache%2A>|Erklärt den Cache für ein Element für ungültig.|  
|<xref:ReportService2010.ReportingService2010.GetCacheOptions%2A>|Gibt die Cachekonfiguration für ein Element und die Einstellungen zurück, die beschreiben, wann die zwischengespeicherte Kopie des Elements nicht mehr gültig ist.|  
|<xref:ReportService2010.ReportingService2010.GetExecutionOptions%2A>|Gibt die Ausführungsoption und die zugehörigen Einstellungen für ein einzelnes Element zurück.|  
|<xref:ReportService2010.ReportingService2010.ListExecutionSettings%2A>|Gibt eine Liste unterstützter Ausführungseinstellungen zurück.|  
|<xref:ReportExecution2005.ReportExecutionService.Render%2A>|Verarbeitet den angegebenen Bericht und rendert ihn im angegebenen Format.|  
|<xref:ReportService2010.ReportingService2010.SetCacheOptions%2A>|Konfiguriert ein Element für die Zwischenspeicherung und gibt Einstellungen an, die festlegen, wann die zwischengespeicherte Kopie des Elements nicht mehr gültig ist.|  
|<xref:ReportService2010.ReportingService2010.SetExecutionOptions%2A>|Legt Ausführungsoptionen und zugeordnete Ausführungseigenschaften für ein angegebenes Element fest.|  
|<xref:ReportService2010.ReportingService2010.UpdateItemExecutionSnapshot%2A>|Generiert für ein angegebenes Element eine Momentaufnahme der Elementausführung.|  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Anwendungen mit dem Webdienst und .NET Framework](../../../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)   
 [Berichtsserver-Webdienst](../../../reporting-services/report-server-web-service/report-server-web-service.md)   
 [Webdienstmethoden für Berichtsserver](../../../reporting-services/report-server-web-service/methods/report-server-web-service-methods.md)   
 [Technische Referenz (SSRS)](../../../reporting-services/technical-reference-ssrs.md)  
  
  
