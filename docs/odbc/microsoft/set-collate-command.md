---
title: SET COLLATE-Befehl | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql-non-specified
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
- set collate command [ODBC]
ms.assetid: 00efbcd4-fea8-4061-86a5-82de413cb753
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 735e28da49e0c8a9dc3a12d9a29d107209ec99dd
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="set-collate-command"></a>SET COLLATE-Befehl
Gibt eine Sortierreihenfolge für Zeichenfelder in nachfolgenden Indizierung und Sortieroperationen an.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
SET COLLATE TO cSequenceName  
```  
  
## <a name="arguments"></a>Argumente  
 *cSequenceName*  
 Gibt eine Sortierreihenfolge an. In der folgenden Tabelle werden die verfügbaren Sortierungsoptionen für die Sequenz beschrieben.  
  
|Tastatur|Sprache|  
|-------------|--------------|  
|HOLLÄNDISCH|Niederländisch|  
|GENERAL|Englisch, Französisch, Deutsch, Modern Spanisch, Portugiesisch und andere westeuropäische Sprachen|  
|DEUTSCH|Deutsch Telefonbuch Order (DIN)|  
|ISLAND|Isländisch|  
|COMPUTER|Maschine (die Standardsortierreihenfolge für frühere Versionen von FoxPro)|  
|NORDAN|Norwegisch, Dänisch|  
|SPANISCH|Spanisch (traditionell)|  
|SWEFIN|Schwedisch, Finnisch|  
|UNIQWT|Eindeutige Gewichtung|  
  
> [!NOTE]  
>  Bei der Angabe der SPANISCHEN Option *ch* ist aus ein einzelnen Buchstaben, die zwischen sortiert *c* und *d*, und *ll* zwischen sortiert  *l* und *m*.  
  
 Wenn Sie eine Sequenz Sortierungsoption als Literalzeichen Zeichenfolge angeben, achten Sie darauf, dass Sie die Option in Anführungszeichen setzen:  
  
```  
SET COLLATE TO "SWEFIN"  
```  
  
 Computer ist die Standardoption für Sortierung Sequenz und, dass die Sequenz Xbase-Benutzer mit vertraut sind. Zeichen sind sortiert, wie sie in der aktuellen Codepage angezeigt werden.  
  
 Allgemeine möglicherweise für die USA und Westeuropäisch Benutzer vorzuziehen. Zeichen sind sortiert, wie sie in der aktuellen Codepage angezeigt werden. In FoxPro Versionen älter als 2.5 Indizes wurde u. u. mit der **oberen**() oder **niedrigeren**()-Funktionen für Zeichenfelder in einem konsistenten Fall zu konvertieren. In Versionen höher als 2.5 FoxPro, Sie können stattdessen Geben Sie die allgemeine Sequenz Sortierungsoption und weglassen der **oberen**()-Konvertierung.  
  
 Bei Angabe einer Sequenz Sortierungsoption als Computer, und wenn Sie eine IDX-Datei erstellen, wird immer eine compact IDX erstellt.  
  
 Verwenden Sie SET("COLLATE"), um die aktuelle Sortierreihenfolge zurückzugeben.  
  
 Sie können eine Sortierreihenfolge für eine Datenquelle angeben, mit der [ODBC Visual FoxPro-Setupdialogfeld](../../odbc/microsoft/odbc-visual-foxpro-setup-dialog-box.md) oder mithilfe der Collate-Schlüsselworts in der Verbindungszeichenfolge mit [SQLDriverConnect](../../odbc/microsoft/sqldriverconnect-visual-foxpro-odbc-driver.md). Dies ist identisch mit den folgenden Befehl ausgeben:  
  
```  
SET COLLATE TO cSequenceName  
```  
  
## <a name="remarks"></a>Hinweise  
 COLLATE festlegen können Sie Tabellen, die Zeichen mit Akzent für alle unterstützten Sprachen enthält. Ändern der Einstellung der COLLATE-festgelegt wirkt sich nicht auf die Sortierreihenfolge von Indizes zuvor geöffneten aus. Visual FoxPro verwaltet automatisch vorhandene Indizes bieten die Flexibilität, um viele verschiedene Arten von Indizes, dies gilt auch für das gleiche Feld zu erstellen.  
  
 Wenn ein Index mit festlegen COLLATE mit allgemeinen festgelegt erstellt wird, und die Einstellung COLLATE festgelegt auf Spanisch später geändert wird, behält der Index die allgemeine Sortierreihenfolge.  
  
## <a name="see-also"></a>Siehe auch  
 [Einrichten von ODBC-Visual FoxPro (Dialogfeld)](../../odbc/microsoft/odbc-visual-foxpro-setup-dialog-box.md)
