---
title: Anzeigen einer Datenbank-Momentaufnahme (SQL Server) | Microsoft-Dokumentation
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: databases
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- database snapshots [SQL Server], viewing
- displaying database snapshots
- viewing database snapshots
ms.assetid: 123f19b2-0850-4033-8507-59ebdfb368ee
caps.latest.revision: "22"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 03c9b9bac4bc4ec50aad8f64099bcbf5a60710e4
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="view-a-database-snapshot-sql-server"></a>Anzeigen einer Datenbank-Momentaufnahme (SQL Server)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)] In diesem Thema wird erläutert, wie eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbank-Momentaufnahme mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] angezeigt wird.  
  
> [!NOTE]  
>  Wenn Sie Datenbank-Momentaufnahmen erstellen, wiederherstellen oder löschen möchten, müssen Sie [!INCLUDE[tsql](../../includes/tsql-md.md)]verwenden.  
  
 **In diesem Thema**  
  
-   **Anzeigen einer Datenbank-Momentaufnahme mit:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="SSMSProcedure"></a> Verwendung von SQL Server Management Studio  
 **So zeigen Sie eine Datenbankmomentaufnahme an**  
  
1.  Stellen Sie im Objekt-Explorer eine Verbindung mit der Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] her, und erweitern Sie die Instanz.  
  
2.  Erweitern Sie **Datenbanken**.  
  
3.  Erweitern Sie **Datenbank-Momentaufnahmen**, und wählen Sie die gewünschte Momentaufnahme aus.  
  
##  <a name="TsqlProcedure"></a> Verwenden von Transact-SQL  
 **So zeigen Sie eine Datenbankmomentaufnahme an**  
  
1.  Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.  
  
2.  Klicken Sie in der Standardleiste auf **Neue Abfrage**.  
  
3.  Zum Anzeigen der Datenbank-Momentaufnahmen der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz fragen Sie die Spalte **source_database_id** der [sys.databases](../../relational-databases/system-catalog-views/sys-databases-transact-sql.md) -Katalogsicht nach Nicht-NULL-Werten ab.  
  
##  <a name="RelatedTasks"></a> Verwandte Aufgaben  
  
-   [Erstellen einer Datenbankmomentaufnahme &#40;Transact-SQL&#41;](../../relational-databases/databases/create-a-database-snapshot-transact-sql.md)  
  
-   [Wiederherstellen einer Datenbank zu einer Datenbank-Momentaufnahme](../../relational-databases/databases/revert-a-database-to-a-database-snapshot.md)  
  
-   [Löschen einer Datenbankmomentaufnahme &#40;Transact-SQL&#41;](../../relational-databases/databases/drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Datenbank-Momentaufnahmen &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md)  
  
  
