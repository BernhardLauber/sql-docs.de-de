---
title: MSSQLSERVER_2596 | Microsoft-Dokumentation
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
- 2596 (Database Engine error)
ms.assetid: 49ab892f-8ba3-4ba1-b562-ddf205019802
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: e16d2a73689ce73d49da4b36fe1569e95a750019
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mssqlserver2596"></a>MSSQLSERVER_2596
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|SQL Server|  
|Ereignis-ID|2596|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|DBCC_DATABASE_IN_READ_ONLY_MODE|  
|Meldungstext|Die REPAIR-Anweisung wurde nicht verarbeitet. Die Datenbank kann nicht im schreibgeschützten Modus sein.|  
  
## <a name="explanation"></a>Erklärung  
Diese Meldung gibt an, dass sich die Datenbank im schreibgeschützten Modus befindet. Reparaturen sind nicht möglich, wenn sich eine Datenbank im schreibgeschützten Modus befindet.  
  
## <a name="user-action"></a>Benutzeraktion  
Legen Sie die Datenbank mithilfe der ALTER DATABASE-Anweisung auf Lese-/Schreibzugriff fest, und führen Sie anschließend den DBCC-Befehl erneut aus.  
  
## <a name="see-also"></a>Siehe auch  
[ALTER DATABASE &#40;Transact-SQL&#41;](~/t-sql/statements/alter-database-transact-sql-set-options.md)  
  
