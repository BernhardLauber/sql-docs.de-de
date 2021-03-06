---
title: Verbindungshandles | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: odbc
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection handles [ODBC]
- handles [ODBC], connection
ms.assetid: 12222653-f04d-46d6-bdee-61348f5d550f
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: dc70c1ade4dcf55d6c66f4e6e44279dcc384fc25
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="connection-handles"></a>Verbindungshandles
Ein *Verbindung* besteht aus einem Treiber und einer Datenquelle. Ein Verbindungshandle identifiziert jede Verbindung. Das Verbindungshandle definiert, nicht nur den zu verwendenden Treiber, sondern welche Datenquelle zur Verwendung mit diesen Treiber. In einem Segment des Codes, die ODBC (der Treiber-Manager oder eines Treibers) implementiert, identifiziert das Verbindungshandle eine Struktur, die Verbindungsinformationen, z. B. Folgendes enthält:  
  
-   Der Status der Verbindung  
  
-   Der aktuellen Verbindungsebene Diagnose  
  
-   Die Ziehpunkte des Anweisungen und Deskriptoren, die derzeit für die Verbindung zugewiesen.  
  
-   Die aktuellen Einstellungen der einzelnen Attribute Verbindung  
  
 ODBC verhindert nicht, wenn der Treiber unterstützt mehrere gleichzeitige Verbindungen. Aus diesem Grund können mehrere Verbindungshandles in einer bestimmten ODBC-Umgebung auf eine Vielzahl von Treibern und Datenquellen, denselben Treiber und eine Vielzahl von Datenquellen, oder sogar mehrere Verbindungen mit dem gleichen Treibers und der Datenquelle zeigen. Einige Treiber zu begrenzen die Anzahl der aktiven Verbindungen, die sie unterstützen; die SQL_MAX_DRIVER_CONNECTIONS option **SQLGetInfo** gibt an, wie viele aktive Verbindungen, die ein bestimmter Treiber unterstützt.  
  
 Verbindungshandles werden in erster Linie verwendet, wenn eine Verbindung mit der Datenquelle herstellen (**SQLConnect**, **SQLDriverConnect**, oder **SQLBrowseConnect**) Verbindung wird getrennt von den Daten Quelle (**SQLDisconnect**), Abrufen von Informationen über die Treiber und die Datenquelle (**SQLGetInfo**), Abrufen von Diagnose (**SQLGetDiagField** und **SQLGetDiagRec**), und die Durchführung von Transaktionen (**SQLEndTran**). Sie werden auch verwendet, wenn festlegen und Abrufen von Verbindungsattributen (**SQLSetConnectAttr** und **SQLGetConnectAttr**) und beim Abrufen der im systemeigenen Format von einer SQL-Anweisung (**SQLNativeSql** ).  
  
 Verbindungshandles zugeordnet **SQLAllocHandle** und mit freigegebenen **SQLFreeHandle**.
