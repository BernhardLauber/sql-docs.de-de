---
title: MSSQLSERVER_10539 | Microsoft-Dokumentation
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: errors-events
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords: 10539 (Database Engine error)
ms.assetid: 49c26ff7-18b8-4f07-a087-f45f63463b3b
caps.latest.revision: "9"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 68bd0b80a316e8b2cd4944310c19b7b21f679906
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mssqlserver10539"></a>MSSQLSERVER_10539
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|SQL Server|  
|Ereignis-ID|10539|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|PG_NO_PLAN_FOR_STMT|  
|Meldungstext|Die Planhinweisliste '%.*ls' kann nicht aus dem Cache erstellt werden, weil kein Abfrageplan für die Anweisung mit dem Startoffset %d verfügbar ist. Dieses Problem kann auftreten, wenn die Anweisung von Datenbankobjekten abhängig ist, die noch nicht erstellt wurden. Stellen Sie sicher, dass alle erforderlichen Datenbankobjekte vorhanden sind, und führen Sie die Anweisung vor dem Erstellen der Planhinweisliste aus.|  
  
## <a name="explanation"></a>Erklärung  
Im Plancache ist kein Abfrageplan für die Anweisung mit dem angegebenen Startoffset vorhanden.  
  
## <a name="user-action"></a>Benutzeraktion  
Stellen Sie sicher, dass alle erforderlichen Datenbankobjekte vorhanden sind, und führen Sie die Anweisung vor dem Erstellen der Planhinweisliste aus.  
  
## <a name="see-also"></a>Siehe auch  
[sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](~/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql.md)  
  
