---
title: Herstellen einer Verbindung mit SQLDriverConnect | Microsoft Docs
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
helpviewer_keywords:
- data sources [ODBC], connection functions
- functions [ODBC], data source or driver connections
- connecting to data source [ODBC], SQLDriverConnect
- connecting to driver [ODBC], SQLDriverConnect
- connecting to data source [ODBC], functions
- connecting to driver [ODBC], functions
- SQLDriverConnect function [ODBC], connecting
- connection functions [ODBC]
- ODBC drivers [ODBC], connection functions
ms.assetid: e46e959f-d3c5-4ddb-810a-107bfcb83fd2
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: d9f6177b384da8866c8140cc30f1d32bca0bb635
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="connecting-with-sqldriverconnect"></a>Herstellen einer Verbindung mit SQLDriverConnect
**SQLDriverConnect** wird für die Verbindung mit einer Datenquelle mithilfe einer Verbindungszeichenfolge verwendet. **SQLDriverConnect** anstelle von **SQLConnect** folgende Gründe vorliegen:  
  
-   Um die Anwendung treiberspezifische Verbindungsinformationen verwenden zu können.  
  
-   Um anzugeben, dass der Treiber den Benutzer zur Eingabe von Verbindungsinformationen auffordert.  
  
-   Um eine Verbindung herstellen, ohne eine Datenquelle angeben.  
  
 Dieser Abschnitt enthält die folgenden Themen.  
  
-   [Treiberspezifische Verbindungsinformationen](../../../odbc/reference/develop-app/driver-specific-connection-information.md)  
  
-   [Auffordern des Benutzers zur Eingabe der Verbindungsinformationen](../../../odbc/reference/develop-app/prompting-the-user-for-connection-information.md)  
  
-   [Herstellen einer Verbindung mithilfe von Dateidatenquellen](../../../odbc/reference/develop-app/connecting-using-file-data-sources.md)  
  
-   [Herstellen einer Verbindung direkt mit dem Treiber](../../../odbc/reference/develop-app/connecting-directly-to-drivers.md)
