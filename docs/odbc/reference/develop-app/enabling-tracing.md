---
title: Aktivieren der Ablaufverfolgung | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: odbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tracing options [ODBC], enabling
ms.assetid: 48e318bd-2487-4708-a698-ea01f36a45e9
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 21f9d8b3d96f2860ed532279acc74ac3f7c717dc
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="enabling-tracing"></a>Aktivieren der Ablaufverfolgung
Ablaufverfolgung kann in der folgenden drei Arten aktiviert werden:  
  
-   Legen Sie die **Ablaufverfolgung** und **TraceFile** Schlüsselwörter im Registrierungseintrag Odbc.ini. Dies aktiviert oder deaktiviert die Ablaufverfolgung, wenn **SQLAllocHandle** mit einem *HandleType* SQL_HANDLE_ENV aufgerufen wird. Diese Optionen werden in der Registerkarte "Ablaufverfolgung" im Dialogfeld ODBC-Datenquellen-Administrator angezeigt wird, während Data Source-Setup festgelegt. Weitere Informationen finden Sie unter [Registrierungseinträge für Datenquellen](../../../odbc/reference/install/registry-entries-for-data-sources.md).  
  
-   Rufen Sie **SQLSetConnectAttr** SQL_ATTR_TRACE-Verbindungsattribut auf SQL_OPT_TRACE_ON festgelegt. Dies aktiviert oder deaktiviert die Ablaufverfolgung für die Dauer der Verbindung. Weitere Informationen finden Sie unter der [SQLSetConnectAttr](../../../odbc/reference/syntax/sqlsetconnectattr-function.md) funktionsbeschreibung.  
  
-   Verwendung **ODBCSharedTraceFlag** zu aktivieren oder deaktivieren Sie die Protokollierung dynamisch. (Weitere Informationen finden Sie im nächste Thema [dynamische Tracing](../../../odbc/reference/develop-app/dynamic-tracing.md).)
