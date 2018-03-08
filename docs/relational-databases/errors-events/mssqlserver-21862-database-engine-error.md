---
title: MSSQLSERVER_21862 | Microsoft-Dokumentation
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
helpviewer_keywords: 21862 (Database Engine error)
ms.assetid: a1d393dd-453b-4d45-9aa5-7d371213e32b
caps.latest.revision: "11"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: ea459faf94613bc26a99192762fc86c872bbb756
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mssqlserver21862"></a>MSSQLSERVER_21862
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|MSSQLSERVER|  
|Ereignis-ID|21862|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|SQLErrorNum21862|  
|Meldungstext|FILESTREAM-Spalten können nicht in einer Veröffentlichung mit der Synchronisierungsmethode 'database snapshot' oder 'database snapshot character' veröffentlicht werden.|  
  
## <a name="explanation"></a>Erklärung  
Da der Zugriff auf FILESTREAM-Daten über eine Datenbankmomentaufnahme nicht möglich ist, kann der Momentaufnahme-Agent FILESTREAM-Daten nicht lesen, wenn für die Synchronisierungsmethode der Veröffentlichung der *Datenbankmomentaufnahme* - oder der *database_snapshot_character*-Parameter angegeben wurde.  
  
## <a name="user-action"></a>Benutzeraktion  
Verwenden Sie für die Veröffentlichung eine andere Synchronisierungsmethode als die *Datenbankmomentaufnahme* oder *database_snapshot_character*, oder schließen Sie die FILESTREAM-Spalte aus der Veröffentlichung aus.  
  
