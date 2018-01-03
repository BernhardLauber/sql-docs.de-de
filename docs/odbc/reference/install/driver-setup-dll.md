---
title: "Setup-DLL für Treiber | Microsoft Docs"
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
- installing ODBC components [ODBC], driver setup DLL
- ODBC drivers [ODBC], driver setup DLL
- driver setup DLL [ODBC]
ms.assetid: 49bab021-81fa-402e-b7a4-a5214f1fadc4
caps.latest.revision: "8"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: fd507929bcb54079f62f81829f5e721834efe21e
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="driver-setup-dll"></a>Treiber-Setup-DLL
> [!NOTE]  
>  Ab Windows XP und Windows Server 2003, ist ODBC in der Windows-Betriebssystem enthalten. Sie sollten nur explizit ODBC in früheren Versionen von Windows installieren.  
  
 Der Setup-Treiber-DLL enthält die **ConfigDriver** und **ConfigDSN** Funktionen. **ConfigDriver** treiberspezifische installationstasks wie das Eingeben von treiberspezifische Informationen in der Registrierung führt. **ConfigDSN** verwaltet treiberspezifische Informationen zu den Datenquellen in der Registrierung. Eine vollständige Beschreibung dieser Funktionen, finden Sie unter [Setup DLL-API-Referenz](../../../odbc/reference/syntax/setup-dll-api-reference.md).  
  
 **ConfigDSN** Ruft die folgenden Funktionen in der Installer DLL Datenquelleninformationen in der Registrierung zu verwalten:  
  
-   **SQLWriteDSNToIni**. Fügen Sie eine Datenquelle hinzu.  
  
-   **SQLRemoveDSNFromIni**. Löschen einer Datenquelle an.  
  
-   **SQLWritePrivateProfileString**. Schreiben Sie einen treiberspezifische Wert unter einem Data Source-Spezifikation Unterschlüssel.  
  
-   **SQLGetPrivateProfileString**. Gelesen Sie einen treiberspezifische-Wert aus dem Data Source-Spezifikation Unterschlüssel.  
  
-   **SQLGetTranslator**. Fordert den Benutzer für einen Übersetzer Namen und eine Option. Diese Funktion ruft **ConfigTranslator** in das Konvertierungsprogramm setup-DLL.  
  
 Der Setup-Treiber wird vom Treiber Entwickler DLL geschrieben. Kann es Teil der Treiber-DLL oder eine separate DLL.
