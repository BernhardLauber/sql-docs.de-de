---
title: "WIE Prädikat Escapezeichen | Microsoft Docs"
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
- LIKE predicate [ODBC]
- escape sequences [ODBC], LIKE predicate
ms.assetid: 185d6109-48cf-4981-bc40-ec2a4a90cafc
caps.latest.revision: "8"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 3946b81210ce439579464fa7e10e8fad63bfd225
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="like-predicate-escape-character"></a>WIE Prädikat Escape-Zeichen
In einem **wie** Prädikat, das Prozentzeichen (%)-entspricht null oder mehr beliebige Zeichen und der Unterstrich (_) entspricht einem einzelnen Zeichen. Um eine tatsächliche Prozentzeichen übereinstimmen oder Unterstrich einer **wie** Prädikat ist, muss ein Escapezeichen vor dem Prozentzeichen oder Unterstrich stammen. Escape-Zeichenfolge, die definiert die **wie** Prädikat Escape-Zeichen ist:  
  
 **{Escape '** *Escape-Zeichen* **'}**  
  
 wobei *Escapezeichen* ist ein beliebiges Zeichen, die von der Datenquelle unterstützt.  
  
 Weitere Informationen zu der LIKE-Escapesequenz, finden Sie unter [wie Escapesequenz](../../../odbc/reference/appendixes/like-escape-sequence.md) in Anhang C: SQL-Grammatik.  
  
 Beispielsweise erstellen die folgenden SQL-Anweisungen des gleichen Ergebnissatzes des Kunden, mit dem Zeichen "% AAA" beginnt. Die erste Anweisung verwendet die Syntax der Escapesequenz. Die zweite Anweisung verwendet die systemeigene Syntax für Microsoft® Access und ist nicht interoperabel. Beachten Sie, das das zweite in jedem Prozentzeichen **wie** Prädikat ist ein Platzhalterzeichen, das 0 (null) oder mehr beliebige Zeichen entspricht.  
  
```  
SELECT Name FROM Customers WHERE Name LIKE '\%AAA%' {escape '\'}  
  
SELECT Name FROM Customers WHERE Name LIKE '[%]AAA%'  
```  
  
 Um zu bestimmen, ob die **wie** Prädikat Escape-Zeichen von einer Datenquelle unterstützt wird, werden Aufrufe von einer Anwendung **SQLGetInfo** mit der Option SQL_LIKE_ESCAPE_CLAUSE.
