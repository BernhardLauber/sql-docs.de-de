---
title: MSSQLSERVER_7711 | Microsoft-Dokumentation
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
helpviewer_keywords: 7711 (Database Engine error)
ms.assetid: a5c7cd6e-18d6-47ef-902b-db9dd64bba34
caps.latest.revision: "8"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: da817a514d1c472010d87a71819ad8f1206d0546
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mssqlserver7711"></a>MSSQLSERVER_7711
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|SQL Server|  
|Ereignis-ID|7711|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|PRT_RANGE_OVERLAP|  
|Meldungstext|Die DATA_COMPRESSION-Option wurde für die Tabelle oder, sofern sie partitioniert ist, für mindestens eine ihrer Partitionen mehrfach angegeben.|  
  
## <a name="explanation"></a>Erklärung  
In einer der folgenden Anweisungen ist ein Fehler in der DATA_COMPRESSION-Option aufgetreten:  
  
-   CREATE TABLE  
  
-   ALTER TABLE  
  
-   CREATE INDEX  
  
-   ALTER INDEX  
  
Wenn die angegebene Tabelle bzw. der angegebene Index partitioniert ist, wurde die DATA_COMPRESSION-Option für mindestens eine der Partitionen mehrfach aufgeführt. Wenn die Tabelle bzw. der Index nicht partitioniert ist, wurde die DATA_COMPRESSION-Option mehrfach angegeben.  
  
## <a name="user-action"></a>Benutzeraktion  
Stellen Sie bei einer partitionierten Tabelle bzw. einem partitionierten Index sicher, dass die DATA_COMPRESSION-Option für jede Partition nur einmal angegeben wird. Verwenden Sie für eine nicht partitionierte Tabelle bzw. einen nicht partitionierten Index die DATA_COMPRESSION-Option nur einmal in der Anweisung.  
  
