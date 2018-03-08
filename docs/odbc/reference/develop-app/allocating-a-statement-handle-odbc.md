---
title: Zuordnen eines Anweisungshandles ODBC | Microsoft Docs
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
- SQL statements [ODBC], statement handles
- statement handles [ODBC]
- allocating statement handles [ODBC]
- handles [ODBC], statement
ms.assetid: 4ce3b446-34ab-46dc-96e5-f40ec95c267e
caps.latest.revision: "6"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 77fec32031efa8fddfef4859c3ba18f57c9eabd5
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="allocating-a-statement-handle-odbc"></a>Zuordnen eines Anweisungshandles ODBC
Bevor die Anwendung eine Anweisung ausgeführt werden kann, muss sie wie folgt ein Anweisungshandle zuordnen:  
  
1.  Die Anwendung deklariert eine Variable vom Typ Befehls beschäftigt. Er ruft dann **SQLAllocHandle** und übergibt die Adresse dieser Variablen wird das Handle für die Verbindung in der die Anweisung und die Option SQL_HANDLE_STMT zuordnen. Beispiel:  
  
    ```  
    SQLHSTMT hstmt1;  
  
    SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
    ```  
  
2.  Der Treiber-Manager weist eine Struktur zum Speichern von Informationen über die Anweisung und die Aufrufe **SQLAllocHandle** im Treiber mit der Option SQL_HANDLE_STMT auf.  
  
3.  Der Treiber ordnet ihre eigene Struktur zum Speichern von Informationen über die Anweisung und gibt das Anweisungshandle Treiber an den Treiber-Manager.  
  
4.  Der Treiber-Manager gibt das Anweisungshandle-Treiber-Manager für die Anwendung in der Anwendungsvariablen zurück.  
  
 Das Anweisungshandle identifiziert, welche Anweisung beim Aufrufen von ODBC-Funktionen verwenden. Weitere Informationen zu Anweisungshandles, finden Sie unter [Anweisungshandles](../../../odbc/reference/develop-app/statement-handles.md).
