---
title: MSSQLSERVER_15517 | Microsoft-Dokumentation
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
- 15517 (Database Engine error)
ms.assetid: f94287f5-129f-4c52-9d34-62b996088001
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 7d35b694fdb0f27bbbe3cabc9c36df66553e4c87
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mssqlserver15517"></a>MSSQLSERVER_15517
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|Ereignis-ID|15517|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|SEC_CANNOTEXECUTEASUSER|  
|Meldungstext|Die Ausführung als Datenbankprinzipal ist nicht möglich, weil der Prinzipal „*principal*“ nicht vorhanden ist, für diesen Typ von Prinzipal kein Identitätswechsel möglich ist, oder Sie nicht die erforderliche Berechtigung haben.|  
  
## <a name="user-action"></a>Benutzeraktion  
Verwenden Sie den Namen eines vorhandenen Prinzipals, oder rufen Sie die IMPERSONATE-Berechtigung für den betreffenden Prinzipal ab.  
  
15517 kann zudem nach dem Anfügen und Wiederherstellen einer Datenbank durch eine Person auftreten, die nicht mit dem ursprünglichen Datenbankbesitzer identisch ist. Ändern Sie zum Beheben dieses Fehlers den db_owner in eine Anmeldung auf Ihrem Server, indem Sie den folgenden Befehl ausführen:  
  
```  
ALTER AUTHORIZATION ON DATABASE:: DBName TO [NewLogin]  
```  
  
## <a name="see-also"></a>Siehe auch  
[In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;](~/relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
