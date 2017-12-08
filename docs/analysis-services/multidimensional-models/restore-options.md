---
title: Wiederherstellungsoptionen | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: multidimensional-models
ms.reviewer: 
ms.suite: sql
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- databases [Analysis Services], restoring
- restoring databases [Analysis Services]
ms.assetid: 75c73802-f321-4671-afc7-54505d62c013
caps.latest.revision: "23"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 23b028bc2e8819d63fafe0a8f915238492088fc4
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="restore-options"></a>Wiederherstellungsoptionen
  Es gibt viele Möglichkeiten zum Wiederherstellen einer [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank. Jede dieser Möglichkeiten setzt jedoch voraus, dass Sie sowohl für den Servercomputer als auch für die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank über Administratorberechtigungen verfügen. Zum Wiederherstellen einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank können Sie das Dialogfeld **Datenbank wiederherstellen** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]öffnen, die entsprechenden Konfigurationsoptionen auswählen und dann die Wiederherstellung vom Dialogfeld aus ausführen. Sie können aber auch mithilfe der in der Datei bereits angegebenen Einstellungen ein Skript erstellen. Das Skript kann gespeichert und immer bei Bedarf ausgeführt werden. Bei dieser Methode wird die Wiederherstellung wie im nächsten Abschnitt beschrieben mithilfe von XMLA abgeschlossen.  
  
## <a name="restoring-databases-using-xmla"></a>Wiederherstellen von Datenbanken mithilfe von XMLA  
 Mit dem XMLA-Befehl Restore kann durch Ausführen einer auf einer ABF-Datei basierenden Wiederherstellung der Wiederherstellungsprozess automatisiert werden. Für den Befehl Restore kann eine Reihe von Eigenschaften festgelegt werden, um Sicherheitsdefinitionen, den Speicherort von Remotepartitionen und das Verschieben von relationalen OLAP-Objekten (ROLAP) anzugeben. Weitere Informationen finden Sie unter [Restore-Element &#40;XMLA&#41;](../../analysis-services/xmla/xml-elements-commands/restore-element-xmla.md).  
  
> [!IMPORTANT]  
>  Für jede Sicherungsdatei muss der Benutzer, der den Wiederherstellungsbefehl ausführt, über die Berechtigung zum Lesen von dem für jede Datei angegebenen Sicherungsspeicherort verfügen. Zum Wiederherstellen einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank, die nicht auf dem Server installiert ist, muss der Benutzer zusätzlich Mitglied der Serverrolle für die betreffende [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz sein. Zum Überschreiben einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank muss der Benutzer entweder Mitglied der Serverrolle für die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz oder Mitglied einer Datenbankrolle mit der Berechtigung „Vollzugriff“ (Administrator) für die wiederherzustellende Datenbank sein.  
  
> [!NOTE]  
>  Nach dem Wiederherstellen einer vorhandenen Datenbank verliert der Benutzer, der die Datenbank wiederhergestellt hat, möglicherweise den Zugriff auf diese Datenbank. Dies ist u. U. der Fall, wenn der Benutzer zum Zeitpunkt der Sicherung kein Mitglied der Serverrolle oder der Datenbankrolle mit der Berechtigung "Vollzugriff (Administrator)" war.  
  
## <a name="see-also"></a>Siehe auch  
 [Dialogfeld Datenbank wiederherstellen &#40;Analysis Services – Mehrdimensionale Daten&#41;](http://msdn.microsoft.com/library/a3990d47-55e2-424e-8eac-87edc937e806)   
 [Sichern und Wiederherstellen von Analysis Services-Datenbanken](../../analysis-services/multidimensional-models/backup-and-restore-of-analysis-services-databases.md)   
 [Restore-Element &#40; XMLA &#41;](../../analysis-services/xmla/xml-elements-commands/restore-element-xmla.md)   
 [Sichern, Wiederherstellen und Synchronisieren von Datenbanken &#40;XMLA&#41;](../../analysis-services/multidimensional-models-scripting-language-assl-xmla/backing-up-restoring-and-synchronizing-databases-xmla.md)  
  
  
