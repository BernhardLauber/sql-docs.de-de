---
title: "Einschränkungen des gregorianischen Kalenders | Microsoft Docs"
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
- data types [ODBC], Gregorian calendar
- Gregorian calendar [ODBC]
ms.assetid: 70667410-c582-4369-8e06-9d98e21cd2bf
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 7ac773945c5c138ab6834aa7914d4028d1d5e156
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="constraints-of-the-gregorian-calendar"></a>Einschränkungen des gregorianischen Kalenders
Date und Datetime-Datentypen und die nachfolgende Felder von Interval-Datentypen, müssen den Einschränkungen des gregorianischen Kalenders entsprechen. Diese Einschränkungen lauten wie folgt:  
  
-   Der Wert des Felds Monat muss zwischen 1 und 12 einschließlich sein.  
  
-   Der Wert des Felds Tag muss im Bereich von 1 bis zur Anzahl der Tage im Monat. Die Anzahl der Tage im Monat richtet sich die Werte der Felder Jahr und Monaten und 28, 29, 30 und 31 sein kann. (Die Anzahl der Tage im Monat kann auch davon abhängen, ob es sich um ein Schaltjahr handelt.)  
  
-   Der Wert des Felds Stunden muss zwischen 0 und 23 sein.  
  
-   Der Wert des Felds für die Minuten muss zwischen 0 und 59.  
  
-   Für die nachfolgende Sekundenfeld der Interval-Datentypen, muss der Wert im Sekundenfeld zwischen 0 und einen Anteil von 59,9 (*n*), einschließlich, in denen  *n*  ist die Anzahl der Ziffern in der Genauigkeit in Sekundenbruchteilen.  
  
-   Für die nachfolgende Sekundenfeld der Datetime-Datentyp, der Wert im Sekundenfeld muss zwischen 0 und 61.9 sein (*n*) (einschließlich), wobei  *n*  gibt die Anzahl der "9" Ziffern und den Wert der  *n*  ist die Genauigkeit der Sekundenbruchteile. (Der Bereich von Sekunden kann bis zu zwei Schaltsekunden Synchronisierung siderischen Zeit beibehalten.)
