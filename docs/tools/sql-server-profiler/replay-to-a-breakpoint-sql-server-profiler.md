---
title: Wiedergeben bis zu einem Breakpoint (SQL Server Profiler) | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: sql-server-profiler
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- breakpoints [SQL Server]
- traces [SQL Server], replaying
ms.assetid: 3caf751e-df3b-40c7-b5e8-4490ae178e0c
caps.latest.revision: "25"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 2feefa23b61938103d68f848df28b76436a87892
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="replay-to-a-breakpoint-sql-server-profiler"></a>Wiedergeben bis zu einem Breakpoint (SQL Server Profiler)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]In diesem Thema wird beschrieben, wie das Festlegen von Breakpoints in einer Ablaufverfolgungsdatei oder-Tabelle, die Sie mithilfe von wiedergeben möchten [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]. Durch das Festlegen von Breakpoints in einer Ablaufverfolgungsdatei oder in einer Tabelle können Sie die Wiedergabe der Ablaufverfolgung bei speziellen Ereignissen anhalten. Die Verwendung von Breakpoints bei der Wiedergabe einer Ablaufverfolgung unterstützt das Debuggen, da Sie die Wiedergabe langer Ablaufverfolgungsskripts in kurze Segmente unterteilen und sie jeweils inkrementell analysieren können.  
  
### <a name="to-replay-to-a-breakpoint"></a>So geben Sie bis zu einem Breakpoint wieder  
  
1.  Öffnen Sie die Ablaufverfolgungsdatei oder -tabelle, die Sie wiedergeben möchten. Weitere Informationen finden Sie unter [Öffnen einer Ablaufverfolgungsdatei &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md) oder den Optimierungsratgeber von [Öffnen einer Ablaufverfolgungstabelle &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md)die richtigen Ereignisse und Spalten aufgezeichnet werden.  
  
     Stellen Sie sicher, dass die geöffnete Ablaufverfolgungsdatei oder -tabelle die Ereignisklassen enthält, die für die Wiedergabe erforderlich sind. Weitere Informationen finden Sie unter [Replay Requirements](../../tools/sql-server-profiler/replay-requirements.md).  
  
2.  Klicken Sie im Ablaufverfolgungsfenster auf ein Ereignis, das Sie als Breakpoint verwenden möchten. Wenden Sie zum Festlegen eines Breakpoints eine der drei folgenden Methoden an:  
  
    -   Drücken Sie F9.  
  
    -   Klicken Sie im Menü **Wiedergeben** auf **Breakpoint ein/aus**  
  
    -   Klicken Sie mit der rechten Maustaste auf das Ereignis, und klicken Sie anschließend auf **Breakpoint ein/aus**.  
  
     Neben dem ausgewählten Ablaufverfolgungsereignis wird ein rotes Aufzählungszeichen angezeigt, mit dem das Ereignis als Breakpoint in der Ablaufverfolgung gekennzeichnet wird.  
  
     Wiederholen Sie diesen Schritt, um mehrere Breakpoints festzulegen.  
  
3.  Klicken Sie im Menü **Wiedergeben** auf **Starten**, und stellen Sie dann eine Verbindung mit dem Server her, auf dem die Ablaufverfolgung wiedergegeben werden soll.  
  
4.  Überprüfen Sie im Dialogfeld **Wiedergabekonfiguration** die Einstellungen, und klicken Sie dann auf **OK**.  
  
     Die Wiedergabe wird gestartet und hält an, wenn ein Breakpoint erreicht wird.  
  
5.  Drücken Sie F5, um die Wiedergabe fortzusetzen, und zum nächsten Breakpoint überzugehen.  
  
6.  Wiederholen Sie Schritt 5 bis zum Ende der Ablaufverfolgung.  
  
## <a name="see-also"></a>Siehe auch  
 [Wiedergeben bis zu einer Cursorposition &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/replay-to-a-cursor-sql-server-profiler.md)   
 [Wiedergeben von Ablaufverfolgungen](../../tools/sql-server-profiler/replay-traces.md)   
 [SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
