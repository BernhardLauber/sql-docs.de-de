---
title: Dynamische Cursor | Microsoft Docs
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
- cursors [ADO], dynamic
- dynamic cursors [ADO]
ms.assetid: 00460f30-8cf7-494e-82df-41012f40ae51
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: dbeb8f40cf6d1ad91a59fa9719410f26386953d4
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="dynamic-cursors"></a>Dynamische Cursor
Dynamische Cursor erkennen alle Änderungen auf die Zeilen im Resultset, unabhängig davon, ob die Änderungen aus, innerhalb des Cursors oder von anderen Benutzern außerhalb des Cursors auftreten. Alle INSERT-, Update- und Delete-Anweisungen, die von allen Benutzern vorgenommen werden über den Cursor sichtbar. Dynamische Cursor erkennen alle Änderungen an den Zeilen, die Reihenfolge und die Werte im Resultset nach dem Öffnen des Cursors. Updates, die außerhalb des Cursors sind nicht sichtbar, bis ein Commit ausgeführt werden (es sei denn, die Transaktionsisolationsstufe des Cursors "Commit" festgelegt ist).  
  
 Nehmen wir beispielsweise an ein dynamischer Cursor ruft zwei Zeilen und eine andere Anwendung, und klicken Sie dann eine dieser Zeilen aktualisiert und löscht die andere. Wenn der dynamische Cursor dann die Zeilen abruft, wird die gelöschte Zeile nicht gefunden, aber es werden die neuen Werte für die aktualisierte Zeile angezeigt.  
  
 Dynamische Cursor ist eine gute Wahl, wenn die Anwendung alle gleichzeitigen Updates, die von anderen Benutzern vorgenommene erkennen muss. Verwenden Sie die **AdOpenDynamic CursorTypeEnum** um anzugeben, dass Sie einen dynamischen Cursor in ADO verwenden möchten.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorwärtscursor](../../../ado/guide/data/forward-only-cursors.md)   
 [Statische Cursor](../../../ado/guide/data/static-cursors.md)   
 [KEYSET-Cursor](../../../ado/guide/data/keyset-cursors.md)
