---
title: "FOR XML-Unterstützung für die benutzerdefinierten Datentypen (User-Defined Data Types, UDT) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: xml
ms.reviewer: 
ms.suite: sql
ms.technology:
- dbe-xml
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UDTs [SQL Server], XML
- user-defined types [SQL Server], XML
ms.assetid: 354e2150-fa2a-4583-b1aa-6b78ae4378b6
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 5c6b0369742c6432dfdf51f008eb95182518992a
ms.sourcegitcommit: 37f0b59e648251be673389fa486b0a984ce22c81
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2018
---
# <a name="for-xml-support-for-the-user-defined-data-types-udt"></a>FOR XML-Unterstützung für die benutzerdefinierten Datentypen (User-Defined Data Types, UDT)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]
FOR XML unterstützt keine benutzerdefinierten Datentypen (UDT) in Common Language Runtime (CLR).  
  
 Um FOR XML mit benutzerdefinierten Datentypen in CLR verwenden zu können, stellen Sie sicher, dass der Datentyp eine XML-Serialisierung besitzt und in der FOR XML-Auswahlklausel explizit in XML umgewandelt wird.  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [FOR XML-Unterstützung für verschiedene SQL Server-Datentypen](../../relational-databases/xml/for-xml-support-for-various-sql-server-data-types.md)  
  
  
