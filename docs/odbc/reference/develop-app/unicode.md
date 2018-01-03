---
title: Unicode | Microsoft Docs
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
- Unicode [ODBC]
- Unicode [ODBC], about Unicode
ms.assetid: 113e1c9a-8333-4805-86f2-e4b57ab816a5
caps.latest.revision: "8"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: b66efb11afce77a878451b767c1a6db000185f41
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="unicode"></a>Unicode
Unicode definiert die Codierung für Zeichen in vielen Sprachen.  
  
 Weitere Informationen zu den Unicode-Standard, finden Sie unter [das Unicode Consortium](http://www.unicode.org).  
  
 Unicode definiert einen Satz von universellen Zeichennamen an. Eine Windows-ANSI-Codepage definiert einen Zeichensatz, der Zeichen für eine Sprache in der Regel enthält. Es ist möglicherweise schwieriger, eine Anwendung schreiben, die erforderlich ist, um unterschiedliche Codepages verwenden.  
  
 Unicode ist eine Codepage nicht erforderlich. Jeder Codepunkt wird in ein einzelnes Zeichen in einer Sprache zugeordnet.  
  
 Derzeit ist die Codierung, die ODBC unterstützt nur Unicode UCS-2, das eine 16-Bit-Ganzzahl (fester Länge) verwendet wird, um die Darstellung eines Zeichens. Unicode kann Anwendungen in verschiedenen Sprachen arbeiten.  
  
 Der ODBC 3.5 (oder höher)-Treiber-Manager ist die Unicode-aktiviert. Dies wirkt sich auf zwei Hauptbereichen: Funktionsaufrufe und string-Datentypen. Der Treiber-Manager Maps Zeichenfolge Funktionsargumente und die Zeichenfolgendaten nach Bedarf von der Anwendung und Treiber, können beide entweder Unicode oder ANSI-aktiviert sein. Diese zwei Bereiche werden in den Abschnitten im Detail besprochen [Unicode Funktionsargumente](../../../odbc/reference/develop-app/unicode-function-arguments.md) und [Unicode-Daten](../../../odbc/reference/develop-app/unicode-data.md).  
  
 Der ODBC 3.5 (oder höher)-Treiber-Manager unterstützt die Verwendung eines Unicode-Treibers mit einer Unicode-Anwendung und eine ANSI-Anwendung. Unterstützt auch die Verwendung eines ANSI-Treibers mit einer ANSI-Anwendung. Der Treiber-Manager bietet begrenzte Unicode in ANSI-Zuordnung für eine Unicode-Anwendung mit einem ANSI-Treiber verwenden.  
  
 Dieser Abschnitt enthält die folgenden Themen.  
  
-   [Unicode-Funktionsargumente](../../../odbc/reference/develop-app/unicode-function-arguments.md)  
  
-   [Unicode-Daten](../../../odbc/reference/develop-app/unicode-data.md)
