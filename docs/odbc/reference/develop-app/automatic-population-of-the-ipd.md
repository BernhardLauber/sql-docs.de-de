---
title: "Automatische Auffüllung der die IPD | Microsoft Docs"
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
- automatically populating ipd [ODBC]
- descriptors [ODBC], automatically populating ipd
- descriptors [ODBC], allocating and freeing
- ipd [ODBC]
- allocating and freeing descriptors [ODBC]
ms.assetid: 1184a7d8-d557-4140-843b-6633ae6deacc
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: be483c04101007383a4672701ac2cdfefbade862
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="automatic-population-of-the-ipd"></a>Automatische Auffüllung der die IPD
Einige Treiber können mit der die Felder von der IPD festlegen, nachdem eine parametrisierte Abfrage vorbereitet wurde. Descriptor-Felder werden automatisch mit Informationen über den Parameter, einschließlich der Datentyp, Genauigkeit, Dezimalstellen und andere Eigenschaften aufgefüllt. Dies entspricht dem unterstützen **SQLDescribeParam**. Diese Informationen können besonders nützlich für eine Anwendung sein, wenn es keine andere Möglichkeit zum Ermitteln, z. B. wenn eine ad-hoc-Abfrage mit Parametern ausgeführt wird, die die Anwendung nicht kennt aufweist.  
  
 Eine Anwendung bestimmt, ob der Treiber durch den Aufruf automatischen Auffüllung unterstützt **SQLGetConnectAttr** mit einem *Attribut* des SQL_ATTR_AUTO_IPD. SQL_TRUE zurückgegeben wird, wird der Treiber unterstützt es, und die Anwendung kann durch Festlegen der SQL_ATTR_ENABLE_AUTO_IPD-Anweisungsattribut auf SQL_TRUE aktivieren.  
  
 Wenn automatischer Auffüllung unterstützt und aktiviert ist, füllt der Treiber die Felder von der IPD an, nachdem eine SQL-Anweisung, die parametermarkierungen, durch einen Aufruf von vorbereitet wurde **SQLPrepare**. Eine Anwendung kann diese Informationen abrufen, durch den Aufruf **SQLGetDescField** oder **SQLGetDescRec**, oder **SQLDescribeParam**. Die Anwendung kann die Informationen verwenden, um den am besten geeigneten Anwendungspuffer für einen Parameter zu binden oder eine Datenkonvertierung dafür anzugeben.  
  
 Automatischer Auffüllung der die IPD kann zu Leistungseinbußen führen. Eine Anwendung kann es deaktivieren, indem das SQL_ATTR_ENABLE_AUTO_IPD-Anweisungsattribut auf SQL_FALSE (Standardwert) zurückzusetzen.
