---
title: Escapesequenz Skalarfunktion | Microsoft Docs
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
- escape sequences [ODBC], scalar function
- scalar functions [ODBC], escape sequences
- ODBC escape sequences [ODBC], scalar function
ms.assetid: aaf5d516-e090-445f-8839-9e39581c69c7
caps.latest.revision: "6"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 6792312d9b82b54460a35dd6f614c206c7bdfe3d
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="scalar-function-escape-sequence"></a>Escapesequenz Skalarfunktion
Verwendung von ODBC Escapesequenzen für Skalarfunktionen. Die Syntax für diese Escapesequenz lautet wie folgt:  
  
```  
{fn scalar-function}  
```  
  
## <a name="remarks"></a>Hinweise  
 In BNF-Schreibweise ist die Syntax folgendermaßen:  
  
 *ODBC-Skalar-Funktion-Escape* :: =  
  
 *Initiator der ODBC-esc* fn *Skalarfunktion ODBC-esc-Abschlusszeichen*  
  
 *Skalare Funktion* :: = *Funktionsnamen* (*Argumentliste*)  
  
 (Die Definitionen für die Nichtterminale *Funktionsnamen* und *Funktionsnamen* (*Argumentliste*) abgeleitet werden, aus der Liste von Skalarfunktionen in [ Anhang E: Skalarfunktionen](../../../odbc/reference/appendixes/appendix-e-scalar-functions.md).)  
  
 *Initiator der ODBC-esc* :: = {}  
  
 *ODBC-esc-Terminator* :: =}  
  
 Um zu bestimmen, ob die Datenquelle, Prozeduren unterstützt und der Treiber die Aufrufsyntax für die ODBC-Prozedur unterstützt, eine Anwendung aufrufen kann **SQLGetInfo**. Weitere Informationen finden Sie unter [Anhang E: Skalarfunktionen](../../../odbc/reference/appendixes/appendix-e-scalar-functions.md).
