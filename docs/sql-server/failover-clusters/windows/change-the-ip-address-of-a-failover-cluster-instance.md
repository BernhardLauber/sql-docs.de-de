---
title: "Ändern der IP-Adresse einer Failoverclusterinstanz | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: failover-clusters
ms.reviewer: 
ms.suite: sql
ms.technology: dbe-high-availability
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- modifying IP addresses
- failover clustering [SQL Server], IP addresses
- IP addresses [SQL Server]
- clusters [SQL Server], IP addresses
ms.assetid: b685f400-cbfe-4c5d-a070-227a1123dae4
caps.latest.revision: "33"
author: MikeRayMSFT
ms.author: mikeray
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: e60e644c6e427c0dd3abb5af6553743e2bfbdf56
ms.sourcegitcommit: b2d8a2d95ffbb6f2f98692d7760cc5523151f99d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2017
---
# <a name="change-the-ip-address-of-a-failover-cluster-instance"></a>Ändern der IP-Adresse einer Failoverclusterinstanz
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)] In diesem Thema wird beschrieben, wie die IP-Adressressource in einer Always On-Failoverclusterinstanz (FCI) mithilfe des Failovercluster-Manager-Snap-Ins geändert wird. Das Failovercluster-Manager-Snap-In ist die Clusterverwaltungsanwendung für den WSFC (Windows Server Failover Clustering)-Dienst.  
  
-   **Vorbereitungen:**  [Sicherheit](#Security)  
  
##  <a name="BeforeYouBegin"></a> Vorbereitungen  
 Bevor Sie beginnen, lesen Sie sich das folgende Thema in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Onlinedokumentation durch: [Vor dem Installieren des Failoverclusterings](../../../sql-server/failover-clusters/install/before-installing-failover-clustering.md).  
  
###  <a name="Security"></a> Sicherheit  
  
####  <a name="Permissions"></a> Berechtigungen  
 Zum Warten oder Aktualisieren einer FCI müssen Sie ein lokaler Administrator sein und über die Berechtigung verfügen, sich bei allen Knoten der FCI als Dienst anzumelden.  
  
##  <a name="WSFC"></a> Verwenden des Failovercluster-Manager-Snap-Ins  
 **So ändern Sie die IP-Adressressource für eine FCI**  
  
1.  Öffnen Sie des Failovercluster-Manager-Snap-In.  
  
2.  Erweitern Sie den Knoten **Dienste und Anwendungen** im linken Bereich, und klicken Sie auf die FCI.  
  
3.  Klicken Sie im rechten Bereich unter der Kategorie **Servername** mit der rechten Maustaste auf die SQL Server-Instanz, und wählen Sie die Option **Eigenschaften** , um das Dialogfeld **Eigenschaften** zu öffnen.  
  
4.  Ändern Sie auf der Registerkarte **Allgemein** die IP-Adressressource.  
  
5.  Klicken Sie auf **OK** , um das Dialogfeld zu schließen.  
  
6.  Klicken Sie im rechten Fensterbereich mit der rechten Maustaste auf „SQL IP Address1(Name der Failoverclusterinstanz)“, und wählen Sie **Offline schalten**aus. SQL IP Address1(failover cluster instance name), SQL Network Name(failover cluster instance name) und die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Statusänderung von Online in Ausstehende Offlineschaltung und anschließend Offline werden angezeigt.  
  
7.  Klicken Sie im rechten Fensterbereich mit der rechten Maustaste auf [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], und klicken Sie dann auf **Online schalten**. SQL IP Address1(failover cluster instance name), SQL Network Name(failover cluster instance name) und die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Statusänderung von Offline in Ausstehende Onlineschaltung und anschließend Online werden angezeigt.  
  
8.  Schließen Sie das Failovercluster-Manager-Snap-In.  
  
  
