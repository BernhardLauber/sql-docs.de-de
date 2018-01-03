---
title: SQLGetData und Blockcursor | Microsoft Docs
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
- cursors [ODBC], block
- SQLGetData function [ODBC], block cursors
- block cursors [ODBC]
- result sets [ODBC], block cursors
ms.assetid: 12599cdc-7725-4faf-bcae-e163ea0f5851
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 12b3c2dc5693f141f24b9209a12923b18a9859e5
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="sqlgetdata-and-block-cursors"></a>SQLGetData und Blockcursor
**SQLGetData** arbeitet mit einer einzelnen Spalte aus einer einzelnen Zeile und ein Array mit Daten aus mehreren Zeilen kann nicht abgerufen werden. Dies ist, da der Hauptverwendungszweck des **SQLGetData** wird zum Abrufen von long-Daten in Teilen, und es ist nur wenig oder gar keinen Grund dafür für mehr als eine Zeile zu einem Zeitpunkt.  
  
 Mit **SQLGetData** mit einem Blockcursor, ruft eine Anwendung zunächst **SQLSetPos** zur Positionierung des Cursors für eine einzelne Zeile. Er ruft dann **SQLGetData** für eine Spalte in dieser Zeile. Dieses Verhalten ist jedoch optional. Um festzustellen, ob ein Treiber die Verwendung von unterstützt **SQLGetData** mit Blockcursor, eine Anwendung ruft **SQLGetInfo** mit der Option SQL_GETDATA_EXTENSIONS.
