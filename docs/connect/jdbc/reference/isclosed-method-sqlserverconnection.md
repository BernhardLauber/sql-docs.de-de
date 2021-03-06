---
title: IsClosed-Methode (SQLServerConnection) | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: jdbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname: SQLServerConnection.isClosed
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 3560ab18-4350-4d02-9716-439f0c2f7142
caps.latest.revision: "9"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 2f8c264171a4e91c4dd449f1ea8fa19830fb4ca1
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="isclosed-method-sqlserverconnection"></a>IsClosed-Methode (SQLServerConnection)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Gibt an, ob dies [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) Objekt geschlossen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
public boolean isClosed()  
```  
  
## <a name="return-value"></a>Rückgabewert  
 **"true"** ist die Verbindung schließen, **"false"** wird jedoch nicht.  
  
## <a name="exceptions"></a>Ausnahmen  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Hinweise  
 Diese IsClosed-Methode wird von der IsClosed-Methode in der java.sql.Connection-Schnittstelle angegeben.  
  
 Überprüft den Status des aufgerufenen SQLServerConnection-Objekts. Eine Verbindung wird geschlossen, wenn die [schließen](../../../connect/jdbc/reference/close-method-sqlserverconnection.md) Methode, die davon aufgerufen wurde oder bestimmte schwerwiegende Fehler aufgetreten sind. Von dieser Methode zurückgegeben **"true"** nur wenn sie aufgerufen wird, nachdem der close-Methode aufgerufen wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [SQLServerConnection-Elemente](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection-Klasse](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
