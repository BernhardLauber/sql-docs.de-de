---
title: Zuordnung der Cursor Attributes1 Informationstypen | Microsoft Docs
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
- compatibility [ODBC], mapping cursor attributes1 information types
- application upgrades [ODBC], mapping cursor attributes1 information types
- mapping cursor attributes1 information types [ODBC]
- backward compatibility [ODBC], mapping cursor attributes1 information types
- upgrading applications [ODBC], mapping cursor attributes1 information types
ms.assetid: 9f112449-ca86-45ac-a865-e6174d67f91b
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 2d40ff95acc4011e7cc3dc12785ea6cef7340e35
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="mapping-the-cursor-attributes1-information-types"></a>Zuordnung der Cursor Attributes1 Informationstypen
Wenn eine ODBC-3. *x* Anwendung ruft **SQLGetInfo** in einer ODBC 2.*.x* Treiber mit der Informationstyp SQL_XXXX_CURSOR_ATTRIBUTES1 (für dynamische, nur vorwärts Keyset-Treiber oder statische Cursor), welche die ODBC 2. die Einstellung der Bits, die vom Treiber-Manager zurückgegeben abhängig. *x* gibt der Treiber die entsprechenden ODBC 2. *X* Informationstypen. Die Bits werden festgelegt, wie in der folgenden Tabelle gezeigt.  
  
|Bit<br /><br /> SQL_XXXX_CURSOR_ATTRIBUTES1|Cursortyp|ODBC-2. *x* Informationen<br /><br /> Typ|  
|-----------------------------------------------|-----------------|-------------------------------------|  
|SQL_CA1_NEXT|Alle|SQL_FETCH_DIRECTION|  
|SQL_CA1_ABSOLUTE SQL_CA1_RELATIVE SQL_CA1_BOOKMARK|Dynamische, keysetgesteuerte, statische|SQL_FETCH_DIRECTION|  
|SQL_CA1_LOCK_NO_CHANGE SQL_CA1_LOCK_UNLOCK SQL_CA1_LOCK_EXCLUSIVE|Dynamische, keysetgesteuerte, statische|SQL_LOCK_TYPES|  
|SQL_CA1_POSITIONED_UPDATE SQL_CA1_POSITIONED_DELETE SQL_CA1_SELECT_FOR_UPDATE|Alle|SQL_POSITIONED_STATEMENTS|  
|SQL_CA1_POS_POSITION SQL_CA1_POS_DELETE SQL_CA1_POS_REFRESH SQL_CA1_POS_BULK_ADD|Dynamische, keysetgesteuerte, statische|SQL_POS_OPERATIONS|
