---
title: Konnte nicht geladen werden, Datei oder Assembly Microsoft Datendienste | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: power-pivot-sharepoint
ms.reviewer: 
ms.suite: sql
ms.technology: analysis-services
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 81ed0f44-8782-462d-af8f-0ba5b975df27
caps.latest.revision: "7"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 175e7b5645a022dd7c840ae3065b4569bdf7a10f
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="could-not-load-file-or-assembly-microsoft-data-services"></a>Datei oder Assembly Microsoft Datendienste konnte nicht geladen werden
  In SharePoint 2010-Umgebungen mit [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] für SharePoint tritt dieser Fehler auf, wenn Sie versuchen, einen Datenfeed zu exportieren und das System nicht über die erforderliche Version von Microsoft ADO.NET Data Services verfügt.  
  
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Gilt für|[!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] für SharePoint|  
|Produktversion|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|  
|Ursache|ADO.NET Data Services 3.5 SP1 wurde nicht gefunden.|  
|Meldungstext|Die Datei oder Assembly "Microsoft.Data.Services, Version=3 .5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" oder eine Abhängigkeit davon wurde nicht gefunden. Die angegebene Datei wurde nicht gefunden.|  
  
## <a name="explanation"></a>Erklärung  
 SharePoint 2010 enthält die Schaltfläche Als Datenfeed exportieren, mit der Sie eine SharePoint-Liste als XML-Datenfeed exportieren können. Außerdem unterstützen sowohl Reporting Services in SharePoint-Modus als auch [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] für SharePoint Datenfeedfunktionen, die ADO.NET Data Services erfordern.  
  
 Wenn ADO.NET Data Services nicht installiert sind, tritt dieser Fehler beim Anfordern eines Datenfeeds auf.  
  
## <a name="user-action"></a>Benutzeraktion  
  
1.  Wechseln Sie zu den Hardware- und Softwareanforderungen für SharePoint 2010, [Hardware- und Softwareanforderungen (SharePoint Server 2010)](http://go.microsoft.com/fwlink/?LinkId=169734) (http://go.microsoft.com/fwlink/?LinkId=169734).  
  
2.  Suchen Sie unter **Installieren der erforderlichen Software**den Link für ADO.NET Data Services 3.5, der dem verwendeten Betriebssystem entspricht.  
  
3.  Klicken Sie auf den Link, und führen Sie das Setupprogramm aus, durch das der Dienst installiert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Bereitstellen von Power Pivot-Lösungen in SharePoint](../../analysis-services/power-pivot-sharepoint/deploy-power-pivot-solutions-to-sharepoint.md)  
  
  
