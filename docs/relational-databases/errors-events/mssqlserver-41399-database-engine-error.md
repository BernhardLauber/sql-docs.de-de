---
title: MSSQLSERVER_41399 | Microsoft-Dokumentation
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
helpviewer_keywords: 41399 (Database Engine error)
ms.assetid: 5e5acb07-16ca-4329-8210-cd2bab0c904f
caps.latest.revision: "6"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: c700e06b34b155f8b1f0885dd541d68cc9115fd5
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mssqlserver41399"></a>MSSQLSERVER_41399
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|Ereignis-ID|41399|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|MAX_SORT_ROW_WIDTH_EXCEEDED|  
|Meldungstext|Der Sortiervorgang ist zu komplex. Weitere Informationen finden Sie in der SQL Server-Onlinedokumentation.|  
  
## <a name="explanation"></a>Erklärung  
Durch das Sortieren der Ergebnisse eines Join -und Aggregationsvorgangs erhöht sich die Komplexität des Sortiervorgangs, da die Größe der Zeile im Sortierungspuffer zunimmt. Dieser Fehler bewirkt, dass die Größe der Zeile größer als die maximale Größe ist, die vom SORT-Operator in systemintern kompilierten gespeicherten Prozeduren unterstützt wird. Beachten Sie, dass die Größe einer Zeile im Sortierungspuffer ausschließlich von der Anzahl der Joins sowie der Anzahl und dem Typ der Aggregatfunktionen bestimmt wird. Die Größe der Zeilen in den Basistabellen wirkt sich nicht auf die Größe der Zeile im Puffer aus.  
  
## <a name="user-action"></a>Benutzeraktion  
Verringern Sie die Komplexität der Abfrage, indem Sie Joins oder Aggregatfunktionen entfernen.  
  
## <a name="see-also"></a>Siehe auch  
[In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;](~/relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
