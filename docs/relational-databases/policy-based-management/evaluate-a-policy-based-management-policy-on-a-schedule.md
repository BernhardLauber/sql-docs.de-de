---
title: Auswerten einer Richtlinie der richtlinienbasierten Verwaltung nach einem Zeitplan | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: ''
ms.component: performance-monitor
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Policy-Based Management, evaluate policy
ms.assetid: bea09522-ff47-4037-ab55-a98ea7c10099
caps.latest.revision: 6
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 9bd58766e370d8752dd0b8376c810ac7a5a3e6df
ms.sourcegitcommit: d6b1695c8cbc70279b7d85ec4dfb66a4271cdb10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/10/2018
---
# <a name="evaluate-a-policy-based-management-policy-on-a-schedule"></a>Auswerten einer Richtlinie der richtlinienbasierten Verwaltung nach einem Zeitplan
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  In diesem Thema wird beschrieben, wie Sie eine Richtlinie der richtlinienbasierten Verwaltung mithilfe von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] nach einem Zeitplan in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]auswerten.  
  
 **In diesem Thema**  
  
-   **Vorbereitungen:**  
  
     [Sicherheit](#Security)  
  
-   **Auswerten einer Richtlinie nach einem Zeitplan mit:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
##  <a name="BeforeYouBegin"></a> Vorbereitungen  
  
###  <a name="Security"></a> Sicherheit  
  
####  <a name="Permissions"></a> Berechtigungen  
 Erfordert die Mitgliedschaft in der PolicyAdministratorRole-Rolle in der msdb-Datenbank.  
  
##  <a name="SSMSProcedure"></a> Verwendung von SQL Server Management Studio  
  
#### <a name="to-evaluate-a-policy-on-a-schedule"></a>So werten Sie eine Richtlinie nach einem Zeitplan aus  
  
1.  Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, in dem der auszuwertende Richtlinienzeitplan enthalten ist.  
  
2.  Klicken Sie auf das Pluszeichen, um den Ordner **Verwaltung** zu erweitern.  
  
3.  Klicken Sie auf das Pluszeichen, um **Richtlinienverwaltung**zu erweitern.  
  
4.  Klicken Sie auf das Pluszeichen, um den Ordner **Richtlinien** zu erweitern.  
  
5.  Klicken Sie mit der rechten Maustaste auf die Richtlinie, deren Zeitplan Sie auswerten möchten, und wählen Sie **Eigenschaften**aus.  
  
6.  Klicken Sie im Dialogfeld **Richtlinie öffnen** > *Richtlinienname* in der Liste **Auswertungsmodus** auf die Option **Nach Zeitplan**.  
  
7.  Klicken Sie unter **Zeitplan**auf **Auswählen** , um einen vorhandenen Zeitplan anzugeben, oder klicken Sie auf **Neu** , um einen neuen Zeitplan zu erstellen.  
  
8.  Wenn Sie fertig sind, klicken Sie auf **OK**.  
  
  
