---
title: MSSQLSERVER_21899 | Microsoft-Dokumentation
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
- 21899 (Database Engine error)
ms.assetid: 32b87a7c-5380-4638-b147-dd78618f6625
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 677f6c5b9a406bdc66d2d92bc696c59c74f77a51
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mssqlserver21899"></a>MSSQLSERVER_21899
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|SQL Server|  
|Ereignis-ID|21899|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|SQLErrorNum21899|  
|Meldungstext|Die Abfrage beim umgeleiteten Verleger '%s' zur Bestimmung, ob sysserver-Einträge für die Abonnenten des ursprünglichen Verlegers '%s' vorliegen, ist mit dem Fehler '%d', Fehlermeldung '%s', fehlgeschlagen.|  
  
## <a name="explanation"></a>Erklärung  
**sp_validate_redirected_publisher** fragt die Abonnement-Metadatentabellen von der Verlegerdatenbank beim Remoteserver ab, um seine zugeordneten Abonnenten zu bestimmen. Fehler 21899 wird zurückgegeben, wenn diese Abfrage fehlschlägt. Die Überprüfungsabfrage erfordert Zugriff auf die veröffentlichte Datenbank beim umgeleiteten Verleger. Wenn die Anmeldung, die beim Aufruf von **sp_adddistpublisher** für den ursprünglichen Verleger angegeben wurde, nicht berechtigt ist, beim umgeleiteten Verleger auf die veröffentlichte Datenbank zuzugreifen, wird der Fehler 21899 zurückgegeben.  
  
## <a name="user-action"></a>Benutzeraktion  
Überprüfen Sie die erwähnte Fehlermeldung, um die Fehlerursache zu bestimmen und entsprechende Korrekturmaßnahmen zu ergreifen  
  
