---
title: Bereitstellen von SQL Server 2016 PowerPivot und Power View in SharePoint 2016 | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d0a9834-db91-403f-847c-79a8f49fc916
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 166ce8f52401d5cd5cad70e19aea37871d57afe4
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2018
---
# <a name="deploying-sql-server-2016-powerpivot-and-power-view-in-sharepoint-2016"></a>Bereitstellen von SQL Server 2016 PowerPivot und Power View in SharePoint 2016
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  **Zusammenfassung:** Dieses Whitepaper bietet SharePoint-Administratoren und Architekten detaillierte Schritt-für-Schritt-Anleitungen für die Bereitstellung und Konfiguration einer Microsoft BI Demo-Umgebung auf Grundlage der Preview-Versionen von SharePoint Server 2016, Office Online-Server und des SQL Server 2016 BI-Stack für SharePoint 2016. Nach einer kurzen Einführung wichtiger architektonischer Änderungen und entsprechender Systemabhängigkeiten werden Software-und Konfigurationsanforderungen sowie der empfohlene Bereitstellungspfad für die Aktivierung und Überprüfung der BI-Funktionen in drei Hauptphasen beschrieben. Dieses Whitepaper behandelt auch bekannte Probleme in SharePoint Server 2016 Beta 2, Office Online Server Preview und SQL Server 2016 CTP 3.1 mit entsprechenden Lösungs- bzw. Umgehungsvorschlägen. In den endgültigen Produktversionen sind diese Umgehungen nicht mehr erforderlich. Überprüfen Sie vor der Bereitstellung von RTM-Releases, ob es eine aktuellere Version dieses Whitepapers gibt.  
  
 **Autor:** Kay Unkroth  
  
 **Technische Bearbeiter:** Adam Saxton, Anne Zorner, Craig Guyer, Frank Weigel, Gregory Appel, Heidi Steen, Jason Haak, Kasper de Jonge, Kirk Stark, Klaus Sobel, Mike Plumley, Mike Taghizadeh, Patrick Wheeler, Riccardo Muti, Steve Hord  
  
 **Veröffentlicht:** Dezember 2015  
  
 **Gilt für:** SQL Server 2016 CTP3.1, SharePoint 2016 Preview, Office Online Server Preview  
  
 Wenn Sie dieses englischsprachige Whitepaper lesen möchten, laden Sie das Word-Dokument [Deploying SQL Server 2016 PowerPivot and Power View in SharePoint 2016](http://download.microsoft.com/download/D/2/0/D20E1C5F-72EA-4505-9F26-FEF9550EFD44/Deploying%20SQL%20Server%202016%20PowerPivot%20and%20Power%20View%20in%20SharePoint%202016.docx) herunter.  
  
  
