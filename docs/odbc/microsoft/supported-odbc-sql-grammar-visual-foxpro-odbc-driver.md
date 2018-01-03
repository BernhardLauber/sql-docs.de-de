---
title: "Unterstützt ODBC SQL-Grammatik (Visual FoxPro-ODBC-Treiber) | Microsoft Docs"
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
- native Visual FoxPro language syntax [ODBC]
- FoxPro ODBC driver [ODBC], SQL grammar
- SQL grammar [ODBC], Visual FoxPro ODBC driver
- Visual FoxPro ODBC driver [ODBC], SQL grammar
- grammar support in Visual FoxPro ODBC driver [ODBC]
- Visual FoxPro ODBC driver [ODBC], native Visual FoxPro language syntax
- FoxPro ODBC driver [ODBC], native Visual FoxPro language syntax
ms.assetid: f41a38c2-e22e-4c65-a32e-9a6777435160
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 877a358d9cd4d9e1863320d4444212c82fed644a
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="supported-odbc-sql-grammar-visual-foxpro-odbc-driver"></a>Unterstützte ODBC-SQL-Grammatik (Visual FoxPro-ODBC-Treiber)
Microsoft Visual FoxPro-ODBC-Treiber unterstützt Folgendes:  
  
-   Alle SQL-Anweisungen und Klauseln in die minimale ODBC-SQL-Grammatik  
  
-   Eine zusätzliche SQL-Anweisung vom Kern ODBC SQL-Grammatik  
  
 Die folgende Tabelle enthält die Elemente, die vom Treiber, Version des ODBC SQL-Grammatik unterstützt.  
  
|Ebene|Elemente|Element|  
|-----------|--------------|----------|  
|Minimum|Datendefinitionssprache (DDL)|CREATE TABLE und DROP TABLE|  
||Datenbearbeitungssprache (DML)|AUSWÄHLEN, einfügen, aktualisieren und löschen|  
||Ausdrücke|Einfache (z. B. ein > B + C)|  
||Datentypen|CHAR, VARCHAR oder LONG VARCHAR|  
  
 Zusätzlich zu den unterstützten ODBC SQL-Grammatik unterstützt der Visual FoxPro-ODBC-Treiber die vollständige systemeigene Visual FoxPro-Sprachsyntax für die folgenden Visual FoxPro-Befehle:  
  
 [ALTER TABLE-ANWEISUNG](../../odbc/microsoft/alter-table-sql-command.md)  
  
 [CREATE TABLE](../../odbc/microsoft/create-table-sql-command.md)  
  
 [DELETE](../../odbc/microsoft/delete-sql-command.md)  
  
 [TAG LÖSCHEN](../../odbc/microsoft/delete-tag-command.md)  
  
 [DROP TABLE](../../odbc/microsoft/drop-table-command.md)  
  
 [INDEX](../../odbc/microsoft/index-command.md)  
  
 [INSERT](../../odbc/microsoft/insert-sql-command.md)  
  
 [SELECT](../../odbc/microsoft/select-sql-command.md)  
  
 [UPDATE](../../odbc/microsoft/update-sql-command.md)
