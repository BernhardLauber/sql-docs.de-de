---
title: SQLTables (Excel-Treiber) | Microsoft Docs
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
- Excel driver [ODBC], SQLTables
- SQLTables function [ODBC], Excel Driver
ms.assetid: 9410b686-4b5b-4b51-b5ef-f9d2e7a48faa
caps.latest.revision: "6"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 083f0813418dc366f14acc11be79c9eb68f5550d
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="sqltables-excel-driver"></a>SQLTables (Excel-Treiber)
> [!NOTE]  
>  Dieses Thema enthält die Excel-Treiber-spezifische Informationen. Allgemeine Informationen zu dieser Funktion finden Sie unter den entsprechenden Themen unter [ODBC API Reference](../../odbc/reference/syntax/odbc-api-reference.md).  
  
|Argument|Kommentare|  
|--------------|--------------|  
|*szTableOwner*|Der einzige gültige Argument für *SzTableOwner* NULL ist, da keines der Treiber Besitzernamens unterstützt. Mit *SzTableOwner* auf NULL festgelegt, werden alle Tabellen zurückgegeben. In der Spalte TABLE_OWNER wird NULL zurückgegeben.|  
|*szTableQualifier*|Wenn der Microsoft Excel-Version 3.0 oder 4.0-Treiber verwendet wird, beim Aufrufen **SQLTables** mit einem Wert für *SzTableQualifier* nicht den Namen einer vorhandenen Tabelle ist, erstellt der Treiber eine Tabelle mit diesem Namen.<br /><br /> In der Spalte TABLE_QUALIFIER **SQLTables** gibt den Pfad zu einem Verzeichnis zurück.|  
|*SzTableType*|Für Microsoft Excel 3.0 oder 4.0 ist "TABLE" der einzige Tabelle unterstützt.<br /><br /> Informationen zu höheren Versionen von Microsoft Excel-Dateien ist "SYSTEMTABELLE" wird zurückgegeben, für Arbeitsblattnamen (Tabellen mit "$" auf der Seite), und "TABLE" für Tabellen in Arbeitsblättern.|
