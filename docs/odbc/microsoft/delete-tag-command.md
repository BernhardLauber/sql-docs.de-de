---
title: TAG-Befehl DELETE | Microsoft Docs
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
helpviewer_keywords: DELETE TAG command [ODBC]
ms.assetid: 4f4e1362-a5f3-4b15-8a3c-d4e96605f221
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: cf31107e21cee13d51046e43acc5c557cf20b9ee
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="delete-tag-command"></a>Löschen Sie die TAG-Befehl
Entfernt eine oder Tags aus einer zusammengesetzten (CDX)-Indexdatei.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
DELETE TAG TagName1 [OF CDXFileName1]  
   [, TagName2 [OF CDXFileName2]] ...  
  Or   
DELETE TAG ALL [OF CDXFileName]  
```  
  
## <a name="arguments"></a>Argumente  
 *TagName1*OF *CDXFileName1*[, *TagName2*[OF *CDXFileName2*]]...  
 Gibt ein Tag, um einen zusammengesetzten Indexdatei zu entfernen. Sie können mehrere Tags mit einem löschen TAG löschen, indem sowie eine Liste der Tag-Namen durch Kommas getrennt. Wenn zwei oder mehrere Tags mit dem gleichen Namen in der geöffneten Indexdateien vorhanden sind, können Sie ein Tag aus einem bestimmten Index-Datei entfernen, indem Sie einschließlich der *CDXFileName*.  
  
 ALLE [OF *CDXFileName*]  
 Entfernt alle Tags aus einer Indexdatei zusammengesetzten. Wenn die aktuelle Tabelle eine strukturelle zusammengesetzten Indexdatei enthält, alle Tags aus der Indexdatei entfernt werden, die Indexdatei wird vom Datenträger gelöscht und wird das Flag in den Tabellenkopf, der angibt, des Vorhandensein einer Datei zugeordneten strukturellen zusammengesetzten Index entfernt. Alle mithilfe von *CDXFileName* alle Tags aus einer Indexdatei öffnen zusammengesetzten, der strukturelle zusammengesetzten Index entfernt.  
  
## <a name="remarks"></a>Hinweise  
 Zusammengesetzten Indexdateien erstellt, die bei einem INDEX enthalten, Tags, Indexeinträge entspricht. TAG löschen wird verwendet, um eine oder Tags von offenen zusammengesetzten Indexdateien zu entfernen. Sie können nur Tags aus zusammengesetzten geöffneten Indexdateien im aktuellen Arbeitsbereich löschen. Wenn Sie alle Tags aus einer Indexdatei zusammengesetzten entfernen, wird die Datei vom Datenträger gelöscht.  
  
 Visual FoxPro sucht zuerst nach einem Tag in der Indexdatei strukturellen zusammengesetzten (falls keines geöffnet ist). Wenn das Tag in der Indexdatei strukturellen zusammengesetzten enthalten ist, sucht Visual FoxPro für den Transponder in anderen Indexdateien öffnen zusammengesetzten.  
  
## <a name="see-also"></a>Siehe auch  
 [Befehl INDEX](../../odbc/microsoft/index-command.md)
