---
title: "Visual C++-Erweiterungen für ADO | Microsoft Docs"
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
dev_langs:
- C++
helpviewer_keywords:
- ADO, Visual C++
- Visual C++ [ADO], VC++ extensions for ADO
ms.assetid: 2952ece0-7217-4448-bb09-f6b64f43b7e2
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: d2c48eff858219640bf58bcd9abd9b222e48619b
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="visual-c-extensions"></a>Visual C++-Erweiterungen
Die bevorzugte Methode für das Programmieren von ADO mit Visual C++ wird mithilfe der **#import** Richtlinie, wie beschrieben in [Microsoft Visual C++-ADO-Programmierung](../../../ado/guide/appendixes/visual-c-ado-programming.md). Frühere Versionen von ADO jedoch geliefert, mit der Programmierung mit Visual C++ eine alternative Methode: die Visual C++-Erweiterungen. In diesem Abschnitt werden diese Funktion für Benutzer, die Erweiterungen für Visual C++-Code verwaltet werden muss, aber neue ADO-Code geschrieben werden soll, verwenden #**importieren**.

 Einer der aufwändigsten Aufträge Visual C++-Programmierer Schriftart beim Abrufen von Daten mit ADO als einen VARIANT-Datentyp in einen C++-Datentyp zurückgegeben, und speichern die konvertierten Daten in einer Klasse oder Struktur konvertieren von Daten ist. Aufwändig, sondern beeinträchtigt Abrufen von C++-Daten über einen VARIANT-Datentyp Leistung aus.

 ADO stellt eine Schnittstelle, die Abrufen von Daten in systemeigene C/C++-Datentypen unterstützt werden, ohne eine Variante durchlaufen, und bietet außerdem Präprozessormakros, die mithilfe der Benutzeroberfläche zu vereinfachen. Das Ergebnis ist ein flexibles Tool, das einfacher zu verwenden und hervorragende Leistung hat.

 Ein häufiges Szenario der C/C++-Client ist, binden Sie einen Datensatz in einem [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) zu einer C/C++-Struktur oder Klasse, die systemeigene C/C++-Typen enthält. Bei Verwendung von VARIANTs umfasst dies das Schreiben von Code für die Konvertierung von VARIANT in systemeigene C/C++-Typen. Die Visual C++-Erweiterungen für ADO sind zu diesem Szenario sehr viel einfacher für die Visual C++-Programmierer ausgerichtet.

 Finden Sie unter den folgenden Themen Weitere Informationen zu den Visual C++-Erweiterungen für ADO.

-   [Verwenden von Visual C++-Erweiterungen für ADO](../../../ado/guide/appendixes/using-visual-c-extensions.md)

-   [Visual C++-Erweiterungsheader](../../../ado/guide/appendixes/visual-c-extensions-header.md)

-   [ADO mit Visual C++-Erweiterungen-Beispiel](../../../ado/guide/appendixes/visual-c-extensions-example.md)

## <a name="see-also"></a>Siehe auch
 [Für Visual C++-Syntax Index COM ADO](../../../ado/reference/ado-api/ado-for-visual-c-syntax-index-for-com.md) [Visual C++-Erweiterungen-Beispiel](../../../ado/guide/appendixes/visual-c-extensions-example.md) [mithilfe von Visual C++-Erweiterungen](../../../ado/guide/appendixes/using-visual-c-extensions.md) [Visual C++-Erweiterungen-Header](../../../ado/guide/appendixes/visual-c-extensions-header.md)
