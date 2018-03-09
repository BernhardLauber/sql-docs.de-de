---
title: MSSQLSERVER_32042 | Microsoft-Dokumentation
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: errors-events
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords:
- 32042 (Database Engine error)
ms.assetid: 53a51c7a-dcd4-4c15-b4d2-6aaa9dce76da
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 565be96fc2300d7a54b3d98ec0f2564e424a49cc
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mssqlserver32042"></a>MSSQLSERVER_32042
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|SQL Server|  
|Ereignis-ID|32042|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|SQLErrorNum32042|  
|Meldungstext|Die Warnung für 'Nicht gesendetes Protokoll' wurde ausgelöst. Der aktuelle Wert von '%d' überschreitet den Threshold '%d'.|  
  
## <a name="explanation"></a>Erklärung  
Dieses Ereignis der Datenbankspiegelung wird für die Prinzipalserverinstanz ausgelöst, um anzugeben, dass der Umfang des nicht gesendeten Protokolls einen vom Benutzer angegebenen Schwellenwert erreicht hat. Normalerweise tritt dieses Ereignis auf, weil sich die Leistung des Systems geändert hat. Entweder hat sich die Bandbreite zwischen den beiden Systemen reduziert, oder die Last hat sich erhöht.  
  
Der Umfang des nicht gesendeten Protokolls ist eine Leistungsmetrik, mit der Sie die Wahrscheinlichkeit eines Datenverlusts im Hinblick auf die Anzahl von Kilobyte (KB) des nicht gesendeten Protokolls ermitteln können. Diese Metrik ist insbesondere für Sitzungen im Modus für hohe Leistung relevant. Diese Metrik ist jedoch auch für Sitzungen im Modus für hohe Sicherheit relevant, wenn die Spiegelung angehalten oder ausgesetzt wird, weil die Partner getrennt werden.  
  
## <a name="user-action"></a>Benutzeraktion  
Prüfen Sie die Auslastung für die Instanzen des Prinzipalservers und des Spiegelservers sowie die entsprechenden Netzwerkverbindungen, um die Ursache zu ermitteln.  
  
## <a name="see-also"></a>Siehe auch  
[Datenbankspiegelung &#40;SQL Server&#41;](~/database-engine/database-mirroring/database-mirroring-sql-server.md)  
[Verwenden von Warnungsschwellenwerten und Warnmeldungen für Spiegelungsleistungsmetriken &#40;SQL Server&#41;](~/database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
