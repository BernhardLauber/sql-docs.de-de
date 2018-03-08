---
title: Deskriptoren | Microsoft Docs
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
- descriptors [ODBC]
- descriptors [ODBC], about descriptors
- descriptor handles [ODBC]
- handles [ODBC], descriptor
ms.assetid: ef2cbb93-cd00-40f8-b1d2-5f5723a991aa
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 78f53c07a036719b669e3c14192eda5da3ead55e
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="descriptors"></a>Deskriptoren
Eine Deskriptorhandles bezieht sich auf eine Datenstruktur, die Informationen zu Spalten oder dynamische Parameter enthält.  
  
 ODBC-Funktionen, die implizit in Spalten und Parameter Daten aktiv festlegen und Abrufen von deskriptorfelder. Für die Instanz, wenn **SQLBindCol** wird aufgerufen, um Spaltendaten zu binden, deskriptorfelder, die vollständig, die Bindung beschreiben festgelegt. Wenn **SQLColAttribute** wird aufgerufen, um Spaltendaten zu beschreiben, werden die Daten in deskriptorfelder gespeicherten zurückgegeben.  
  
 Eine Anwendung Aufrufen von ODBC-Funktionen muss nicht selbst mit Deskriptoren betreffen. Keine Datenbankvorgang erfordert, dass die Anwendung direkt Deskriptoren zugreifen. Allerdings optimiert die direkten Zugriff auf Deskriptoren viele Vorgänge bei einigen Anwendungen ist. Beispielsweise Direkter Zugriff auf die Deskriptoren bietet eine Möglichkeit, Spaltendaten, binden u. effizienter als das aufrufen können **SQLBindCol** erneut aus.  
  
> [!NOTE]  
>  Die physikalische Darstellung des Deskriptors ist nicht definiert. Anwendungen erhalten direkten Zugriff auf ein Deskriptor, der nur durch ihre Felder durch Aufrufen von ODBC-Funktionen mit dem Deskriptorhandles bearbeiten.  
  
 Dieser Abschnitt enthält die folgenden Themen.  
  
-   [Typen von Deskriptoren](../../../odbc/reference/develop-app/types-of-descriptors.md)  
  
-   [Deskriptorfelder](../../../odbc/reference/develop-app/descriptor-fields.md)  
  
-   [Zuordnen und Freigeben von Deskriptoren](../../../odbc/reference/develop-app/allocating-and-freeing-descriptors.md)  
  
-   [Abrufen und Festlegen von Deskriptorfeldern](../../../odbc/reference/develop-app/getting-and-setting-descriptor-fields.md)
