---
title: Setup-Programm | Microsoft Docs
ms.custom: ''
ms.date: 08/31/2016
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
- installing ODBC components [ODBC], setup program
ms.assetid: 9cc5d75d-b293-41e5-927c-10f4af2e7af1
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 03f834f4258ccc01c551a5e59c2b27dce4a829ef
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="setup-program"></a>Setup-Programm
> **Hinweis:** ab Windows XP und Windows Server 2003, **ODBC ist in der Windows-Betriebssystem enthalten**. Sie sollten nur explizit ODBC in früheren Versionen von Windows installieren.  
  
 Der Benutzer führt das Setup-Programm, um den Setupvorgang zu starten. Das Setup-Programm ist von der Anwendung oder Treiber Entwickler geschrieben. Neben der Installation von ODBC-Komponenten, können sie andere Software installieren. Anwendungsentwickler können z. B. das gleiche Setup-Programm sowohl ODBC-Komponenten zu installieren und ihre Anwendungen zu installieren verwenden.  
  
 Entwickler können das Setup-Programm von Grund auf neu, schreiben, mit dem Setup-Hilfsprogramme von Microsoft® Windows® SDK oder das Setup Software anderer Anbieter. Dies gibt Ihnen Entwickler vollständige Kontrolle über das Setupprogramm Aussehen und Verhalten. Das Setup-Programm kann zur Installation zusätzliche Software, z. B. eine ODBC-Anwendung geschrieben werden. Weitere Informationen zu Windows SDK-Setup-Hilfsprogramme finden Sie unter der Windows-SDK-Dokumentation.  
  
 Wie viel der Installation tatsächlich vom Setupprogramm abgeschlossen ist, hängt davon ab, was Aufrufe in das DLL-Installationsprogramm fungiert. Das Installationsprogramm DLL enthält Funktionen, um einzelne ODBC-Komponenten zu installieren. Ruft das Setup-Programm einfach **SQLInstallDriverManager**, **SQLInstallDriverEx**, oder **SQLInstallTranslatorEx** im Installationsprogramm DLL, die den Pfad der abzurufenden der Verzeichnis, in dem die Komponente installiert werden und Informationen über die Komponente zur Registrierung hinzugefügt ist. Diese Funktionen kopieren Sie Dateien nicht tatsächlich; das Setup-Programm wird anhand der Informationen in den Argumenten dieser Funktionen.  
  
 Das Installationsprogramm DLL enthält auch Funktionen zum Entfernen von ODBC-Komponenten. Der Setup-Programm ruft **SQLRemoveDriverManager**, **SQLRemoveDriver**, oder **SQLRemoveTranslator** im Installationsprogramm DLL um eine Komponente Auslastung zu verringern. Anzahl der in der Registrierung und, wenn neue Verwendungsanzahl der Komponente auf 0 liegt, entfernen Sie alle Informationen über die Komponente aus der Registrierung. Diese Funktionen bauen Sie die Dateien für die Komponente nicht tatsächlich; das Setup-Programm wird auf 0 fällt die Verwendungsanzahl der neuen.
