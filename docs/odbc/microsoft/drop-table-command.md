---
title: DROP TABLE-Befehl | Microsoft Docs
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
- drop table command [ODBC]
ms.assetid: bc50459b-8861-4889-84a9-129ae9065aa8
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: bd9798d5394f4291b0ff77abba55cb7c780aa4f1
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="drop-table-command"></a>DROP TABLE-Befehl
Entfernt eine Tabelle aus der Datenbank mit der Datenquelle angegeben, und vom Datenträger gelöscht.  
  
 Der Visual FoxPro-ODBC-Treiber unterstützt die systemeigene Visual FoxPro-Sprachsyntax für diesen Befehl an. Treiberspezifische Informationen finden Sie unter den Hinweisen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
DROP TABLE TableName | FileName | ?  
```  
  
## <a name="settings"></a>Einstellungen  
 *TableName*  
 Gibt die Tabelle So entfernen Sie aus der Datenbank mit der Datenquelle angegeben und vom Datenträger zu löschen.  
  
 *FileName*  
 Gibt eine kostenlose Tabelle vom Datenträger gelöscht.  
  
 ?  
 Zeigt das Dialogfeld "entfernen" in dem Sie eine Tabelle entfernen aus der Datenbank mit der Datenquelle angegeben und vom Datenträger löschen auswählen können.  
  
## <a name="remarks"></a>Hinweise  
 Wenn DROP TABLE ausgegeben wird, werden alle primären Indizes, Standardwerte und Regeln zur Überprüfung der Tabelle zugeordneten ebenfalls entfernt. DROP TABLE wirkt sich auch auf andere Tabellen in der Datenbank, die mit der Datenquelle angegeben werden, wenn diese Tabellen Regeln haben oder die Beziehungen der Tabelle entfernt wird. Die Regeln und Beziehungen sind nicht mehr gültig, wenn die Tabelle aus der Datenbank entfernt wird.  
  
## <a name="driver-remarks"></a>Treiber "Hinweise".  
 Wenn Ihre Anwendung die ODBC-SQL-Anweisung DROP TABLE an die Datenquelle gesendet wird, konvertiert der Visual FoxPro-ODBC-Treiber den Befehl in der Visual FoxProDROP TABLE-Befehl, die mit der Syntax in der folgenden Tabelle gezeigt.  
  
|ODBC-syntax|Datenquelle|Visual FoxPro-syntax|  
|-----------------|-----------------|--------------------------|  
|DROP TABLE *Base Tabellenname*|Datenbank (.dbc-Datei)|REMOVE-Tabelle *TableName* löschen|  
||Verzeichnis des freien Tabellen (DBF-Dateien)|ERASE- *DbfName*<br /><br /> ERASE- *CdxName*<br /><br /> ERASE- *FptName*|
