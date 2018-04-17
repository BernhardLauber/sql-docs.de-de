---
title: Ausgeführten Batches | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
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
- batches [ODBC], executing
- SQL statements [ODBC], batches
ms.assetid: f082c717-4f82-4820-a2fa-ba607d8fd872
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 0ebbba1ef4141ed71a80afa91c28d9b12a6dbacc
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="executing-batches"></a>Ausführen von Batches
Bevor eine Anwendung einen Batch von Anweisungen ausgeführt wird, müssen sie zuerst überprüfen, ob sie unterstützt werden. Ruft die Anwendung dazu **SQLGetInfo** mit den Optionen SQL_BATCH_SUPPORT SQL_PARAM_ARRAY_ROW_COUNTS und SQL_PARAM_ARRAY_SELECTS. Die erste Möglichkeit gibt, ob die Zeile Count – generieren und Ergebnis Satz – Generieren von Anweisungen werden in explizite Batches und Prozeduren, während die letzten beiden Optionen, die Informationen über die Verfügbarkeit der Zeilenanzahl und Resultset zurück in legt unterstützt parametrisiert die Ausführung.  
  
 Batches von Anweisungen ausgeführt werden, über **SQLExecute** oder **SQLExecDirect**. Der folgende Aufruf führt z. B. einen expliziten Batch von Anweisungen, um einen neuen Verkaufsauftrag zu öffnen.  
  
```  
SQLCHAR *BatchStmt =  
   "INSERT INTO Orders (OrderID, CustID, OpenDate, SalesPerson, Status)"  
      "VALUES (2002, 1001, {fn CURDATE()}, 'Garcia', 'OPEN');"  
   "INSERT INTO Lines (OrderID, Line, PartID, Quantity) VALUES (2002, 1, 1234, 10);"  
   "INSERT INTO Lines (OrderID, Line, PartID, Quantity) VALUES (2002, 2, 987, 8);"  
   "INSERT INTO Lines (OrderID, Line, PartID, Quantity) VALUES (2002, 3, 566, 17);"  
   "INSERT INTO Lines (OrderID, Line, PartID, Quantity) VALUES (2002, 4, 412, 500)";  
  
SQLExecDirect(hstmt, BatchStmt, SQL_NTS);  
```  
  
 Wenn ein Batch von Ergebnis Generieren von Anweisungen ausgeführt wird, gibt einen oder mehr Zeilenanzahl oder Ergebnis legt diese fest. Weitere Informationen dazu, wie diese abrufen, finden Sie unter [mehrere Ergebnisse](../../../odbc/reference/develop-app/multiple-results.md).  
  
 Wenn ein Batch von Anweisungen Parametermarker enthält, werden diese nummeriert in aufsteigender Reihenfolge der Parameter, wie in jeder anderen-Anweisung angegeben werden. Der folgende Batch von Anweisungen verfügt z. B. von 1 bis 21 nummerierte Parameter; die in der ersten **einfügen** -Anweisung lauten nummerierten 1 bis 5 und die in den letzten **einfügen** -Anweisung lauten nummerierten 18 bis 21.  
  
```  
INSERT INTO Orders (OrderID, CustID, OpenDate, SalesPerson, Status)  
   VALUES (?, ?, ?, ?, ?);  
INSERT INTO Lines (OrderID, Line, PartID, Quantity) VALUES (?, ?, ?, ?);  
INSERT INTO Lines (OrderID, Line, PartID, Quantity) VALUES (?, ?, ?, ?);  
INSERT INTO Lines (OrderID, Line, PartID, Quantity) VALUES (?, ?, ?, ?);  
INSERT INTO Lines (OrderID, Line, PartID, Quantity) VALUES (?, ?, ?, ?);  
```  
  
 Weitere Informationen zu Parametern finden Sie unter [Anweisungsparametern](../../../odbc/reference/develop-app/statement-parameters.md)weiter unten in diesem Abschnitt.
