---
title: SQLCloseCursor aufrufen | Microsoft Docs
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
- application upgrades [ODBC], SQLCloseCursor
- backward compatibility [ODBC], SqlCloseCursor
- SQLCloseCursor function [ODBC], calling
- upgrading applications [ODBC], SQLCloseCursor
- compatibility [ODBC], SQLCloseCursor
ms.assetid: ef448c39-a9ad-4f07-8ef3-65bd4cef672a
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 3c3870a36138fd55a2e404d38e28db327990ba1b
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="calling-sqlclosecursor"></a>SQLCloseCursor aufrufen
Da **SQLCloseCursor** ist nahezu identisch mit **SQLFreeStmt** mit SQL_CLOSE, führt der Treiber-Manager diese Funktion nicht zuordnen. Ersatzfunktionen werden zugeordnet, sodass vorhandene ODBC 2.*.x* Anwendungen können problemlos verschieben, um ODBC 3.. *X* mit den neuen Funktionen. Eine solche Verschiebung erleichtert das für solche Anwendungen mit neuen ODBC 3. beginnen. *x* -Funktionen in bedingten Code modulare Weise. **SQLCloseCursor** stellt keinen keine neuen Funktionen dar. Eine Anwendung ist keine Vorteile erzielen, indem Sie die zu **SQLCloseCursor** aus **SQLFreeStmt** mit SQL_CLOSE.
