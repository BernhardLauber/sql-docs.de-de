---
title: GetDisableStatementPooling-Methode (SQLServerConnection) | Microsoft Docs
ms.custom: 
ms.date: 01/19/2018
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: jdbc
ms.reviewer: 
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- SQLServerConnection.getDisableStatementPooling
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: e4b682c858c72c8560013a578513a7661bb1c570
ms.sourcegitcommit: 9d0467265e052b925547aafaca51e5a5e93b7e38
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2018
---
# <a name="getdisablestatementpooling-method-sqlserverconnection"></a>GetDisableStatementPooling-Methode (SQLServerConnection)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

 Gibt den Wert der **"disablestatementpooling":** Connection-Eigenschaft. Diese Einstellung steuert, ob anweisungspools aktiviert ist oder nicht für diese Verbindung.

## <a name="syntax"></a>Syntax  
  
```  
  
public boolean getDisableStatementPooling()  
```  

## <a name="return-value"></a>Rückgabewert
 Ein **booleschen** , enthält den Wert der **"disablestatementpooling":** Connection-Eigenschaft.

## <a name="exceptions"></a>Ausnahmen  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
 
## <a name="remarks"></a>Hinweise  
 Diese Methode wird von JDBC Driver, Version 6.4 verfügbar und Weitergabe.
 
## <a name="see-also"></a>Siehe auch  
 [SQLServerConnection-Elemente](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection-Klasse](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
