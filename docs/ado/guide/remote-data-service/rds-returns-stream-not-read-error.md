---
title: RDS gibt &quot;Stream nicht lesen&quot; Fehler | Microsoft Docs
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- stream not read error in RDS [ADO]
ms.assetid: cb5a68f8-dba4-41da-bafd-04efe53706b7
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a14606f5ac503494159a70129e13b53b51758e72
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="rds-returns-quotstream-not-readquot-error"></a>RDS gibt &quot;Stream nicht lesen&quot; Fehler
"Das Datenstromobjekt konnte nicht gelesen werden, da er leer ist oder die aktuelle Position am Ende des Streams ist. Legen Sie für nicht leere Datenströme die aktuelle Position mit der Position-Eigenschaft. Um festzustellen, ob ein Stream leer ist, überprüfen Sie die Größeneigenschaft."  
  
 Wenn Sie diese Fehlermeldung angezeigt wird, haben Sie sich möglicherweise versucht, eine parametrisierte hierarchische Abfrage über http verwenden. RDS lässt nicht zu, dass Sie remote parametrisierte Hierarchien zu verwenden.  
  
> [!IMPORTANT]
>  Ab Windows 8 und Windows Server 2012, sind nicht mehr RDS-Server-Komponenten in Windows-Betriebssystems enthalten (finden Sie unter Windows 8 und [Windows Server 2012 Compatibility Cookbook](https://www.microsoft.com/en-us/download/details.aspx?id=27416) detailliertere). RDS-Clientkomponenten werden in einer zukünftigen Version von Windows entfernt werden. Verwenden Sie diese Funktion beim Entwickeln neuer Anwendungen nicht, und planen Sie das Ändern von Anwendungen, in denen es zurzeit verwendet wird. Anwendungen, die RDS verwenden sollten migrieren [WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlegendes zu RDS](../../../ado/guide/remote-data-service/rds-fundamentals.md)


