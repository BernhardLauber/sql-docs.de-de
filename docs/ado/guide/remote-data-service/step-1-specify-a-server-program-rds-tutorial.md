---
title: 'Schritt 1: Geben Sie ein Serverprogramm (RDS-Lernprogramm) | Microsoft Docs'
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
- RDS tutorial [ADO], specifying server program
ms.assetid: d8bb35b1-c02a-4231-8d55-016e56e53b95
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 9eae6b17fc9277bd5e3c4cfe9259a026681252f0
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="step-1-specify-a-server-program-rds-tutorial"></a>Schritt 1: Geben Sie ein Serverprogramm (RDS-Lernprogramm)
In den allgemeinsten Fall verwenden die [RDS. DataSpace](../../../ado/reference/rds-api/dataspace-object-rds.md) Objekt [CreateObject](../../../ado/reference/rds-api/createobject-method-rds.md) Methode, um die Standardserverprogramm anzugeben [RDSServer.DataFactory](../../../ado/reference/rds-api/datafactory-object-rdsserver.md), oder eigene benutzerdefinierte Serverprogramm (Business-Objekt). Ein Serverprogramm auf dem Server und einem Verweis auf das Serverprogramm instanziiert wird oder *Proxy*, zurückgegeben.  
  
 Dieses Lernprogramm verwendet das Standardprogramm für den Server:  
  
```  
Sub RDSTutorial1()  
   Dim DS as New RDS.DataSpace  
   Dim DF as Object  
   Set DF = DS.("RDSServer.DataFactory", "http://yourServer")  
...  
```  
  
> [!IMPORTANT]
>  Ab Windows 8 und Windows Server 2012, sind nicht mehr RDS-Server-Komponenten in Windows-Betriebssystems enthalten (finden Sie unter Windows 8 und [Windows Server 2012 Compatibility Cookbook](https://www.microsoft.com/en-us/download/details.aspx?id=27416) detailliertere). RDS-Clientkomponenten werden in einer zukünftigen Version von Windows entfernt werden. Verwenden Sie diese Funktion beim Entwickeln neuer Anwendungen nicht, und planen Sie das Ändern von Anwendungen, in denen es zurzeit verwendet wird. Anwendungen, die RDS verwenden sollten migrieren [WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
## <a name="see-also"></a>Siehe auch  
 [Schritt 2: Aufrufen des Programms (RDS-Lernprogramm)](../../../ado/guide/remote-data-service/step-2-invoke-the-server-program-rds-tutorial.md)   
 [RDS-Tutorial (VBScript)](../../../ado/guide/remote-data-service/rds-tutorial-vbscript.md)   
