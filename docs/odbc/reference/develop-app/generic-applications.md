---
title: Allgemeiner Anwendungen | Microsoft Docs
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
- interoperability [ODBC], generic applications
- interoperability [ODBC], levels
- generic applications [ODBC]
ms.assetid: dda2a3c4-76ef-40a6-b3a1-9e95bed61618
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: ae9c4bc73af6fdb777abf617cbed8b81eed5c043
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="generic-applications"></a>Allgemeiner Anwendungen
Allgemeine Anwendungen manchmal eine fest programmiertes aufgeführte Aufgabe ausführen, z. B. als Kalkulationstabelle, Abrufen von Daten aus einer Datenbank. Sie können auch eine Vielzahl von benutzerdefinierten Tasks, z. B. eine Standardabfrage-Anwendung, die der Benutzer zum eingeben und Ausführen einer SQL-Anweisung ausführen. Was allgemeine Anwendungen gemeinsam haben werden, dass sie mit einer Vielzahl von verschiedenen DBMS funktionieren müssen und, dass der Entwickler nicht im Voraus weiß, was diese DBMS werden.  
  
 Aus diesem Grund müssen allgemeine Anwendungen sehr interoperabel sein. Entwickler muss verschiedene Auswahlmöglichkeiten, trading deaktiviert Interoperabilität für Funktionen und muss Code schreiben, der erwartet, Treiber dass, um eine Breite Palette von Funktionen zu unterstützen. Während allgemeine Anwendungen für die Zusammenarbeit mit gängigen DBMS optimiert werden können, enthalten sie selten treiberspezifische oder DBMS-spezifischen Code.
