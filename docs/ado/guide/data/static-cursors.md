---
title: Statische Cursor | Microsoft Docs
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- cursors [ADO], static
- static cursors [ADO]
ms.assetid: cce93ace-c4ed-4c6c-940c-28a50ff2fd12
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 41af8e500710f3944f43f2408f00f24184204718
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="static-cursors"></a>Statische Cursor
Der statische Cursor zeigt immer das Resultset, wie dem ersten Öffnen des Cursors wurde. Statische Cursor je nach Implementierung, sind entweder nur-Lese oder Lese-/Schreibzugriff, und geben Sie einen Bildlauf vorwärts und rückwärts. Der statische Cursor erkennt in der Regel keine Änderungen an der Mitgliedschaft, Reihenfolge oder Werte des Resultsets nach dem Öffnen des Cursors. Statische Cursor erkennt möglicherweise eigene Updates, löschungen und einfügungen, obwohl sie nicht dazu erforderlich sind.  
  
 Statische Cursor erkennen nie andere aktualisiert, gelöscht und fügt ein. Nehmen wir beispielsweise an ein statischer Cursor abruft, eine Zeile und einer anderen Anwendung wird diese Zeile aktualisiert. Wenn die Anwendung die Zeile aus der statische Cursor refetches, sind die Werte, die er angezeigt wird trotz der Änderungen, die von der anderen Anwendung unverändert. Alle Typen von Durchführen eines Bildlaufs werden unterstützt, aber Anbieter möglicherweise Lesezeichen möglicherweise nicht unterstützt.  
  
 Wenn Ihre Anwendung nicht erkennen, Daten geändert und erfordern, Durchführen eines Bildlaufs muss, ist der statische Cursor die beste Wahl. Verwenden Sie die **AdOpenStatic CursorTypeEnum** um anzugeben, dass Sie einen statischen Cursor in ADO verwenden möchten.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorwärtscursor](../../../ado/guide/data/forward-only-cursors.md)   
 [KEYSET-Cursor](../../../ado/guide/data/keyset-cursors.md)   
 [Dynamische Cursor](../../../ado/guide/data/dynamic-cursors.md)
