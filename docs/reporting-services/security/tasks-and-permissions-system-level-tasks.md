---
title: Aufgaben auf Systemebene | Microsoft-Dokumentation
ms.custom: 
ms.date: 03/01/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.service: 
ms.component: security
ms.reviewer: 
ms.suite: pro-bi
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: system-level tasks [Reporting Services]
ms.assetid: 7023b388-40b2-4590-b227-115cf380a1e7
caps.latest.revision: "36"
author: guyinacube
ms.author: asaxton
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: fcfb30e90a7e5e387b6a7e244a842a41c8ce7012
ms.sourcegitcommit: b2d8a2d95ffbb6f2f98692d7760cc5523151f99d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2017
---
# <a name="tasks-and-permissions---system-level-tasks"></a>Aufgaben und Berechtigungen: Aufgaben auf Systemebene
  Eine Aufgabe auf Systemebene ist eine Auflistung von Berechtigungen im Hinblick auf Vorgänge, die die Berichtsserversite insgesamt betreffen. [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] enthält auch Aufgaben auf Elementebene, die sich auf bestimmte Elemente beziehen. Weitere Informationen finden Sie unter [Aufgaben auf Elementebene](../../reporting-services/security/tasks-and-permissions-item-level-tasks.md). Weitere Informationen zu Aufgaben und Berechtigungen im Allgemeinen finden Sie unter [Tasks and Permissions](../../reporting-services/security/tasks-and-permissions.md).  
  
> [!NOTE]  
>  Wenn Sie mit diesen Aufgaben programmgesteuert arbeiten, müssen Sie Methoden verwenden, die Aufgaben auf Systemebene unterstützen. Weitere Informationen finden Sie unter <xref:ReportService2010.ReportingService2010.ListTasks%2A> und <xref:ReportService2010.ReportingService2010.ListRoles%2A>.  
  
## <a name="permissions-in-system-level-tasks"></a>Berechtigungen für Aufgaben auf Systemebene  
 In der folgenden Tabelle sind die Berechtigungsarten für jede Systemaufgabe aufgeführt. Die Berechtigungsarten sind nur zu Informationszwecken aufgeführt, um eine genauere Beschreibung der über die verschiedenen Aufgaben verfügbaren Funktionalität bereitzustellen.  
  
|Task|Berechtigungen|  
|----------|-----------------|  
|Berichtsdefinitionen ausführen|Berichtsdefinitionen ausführen (Berechtigungs- und Aufgabenname sind identisch)|  
|Ereignisse generieren|Ereignisse generieren|  
|Aufträge verwalten|Lesen von Systemeigenschaften<br /><br /> Aktualisieren von Systemeigenschaften|  
|Berichtsservereigenschaften verwalten|Lesen von Systemeigenschaften<br /><br /> Aktualisieren von Systemeigenschaften|  
|Rollen verwalten|Erstellen von Rollen<br /><br /> Löschen von Rollen<br /><br /> Lesen von Rolleneigenschaften<br /><br /> Aktualisieren von Rolleneigenschaften|  
|Freigegebene Zeitpläne verwalten|Erstellen von Zeitplänen|  
|Berichtsserversicherheit verwalten|Lesen von Systemsicherheitsrichtlinien<br /><br /> Aktualisieren von Systemsicherheitsrichtlinien|  
|Berichtsservereigenschaften anzeigen|Lesen von Systemeigenschaften|  
|Freigegebene Zeitpläne anzeigen|Lesen von Zeitplänen|  
  
## <a name="see-also"></a>Siehe auch  
 [Erteilen von Berechtigungen für einen Berichtsserver im einheitlichen Modus](../../reporting-services/security/granting-permissions-on-a-native-mode-report-server.md)  
  
  
