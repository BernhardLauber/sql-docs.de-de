---
title: SetFetchDirection-Methode (SQLServerStatement) | Microsoft Docs
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
apiname: SQLServerStatement.setFetchDirection
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 18176517-2fb3-4266-924d-0f01253083d2
caps.latest.revision: "13"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: c07f7d6bd56dd93ad524c04b7845ae1515581cff
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="setfetchdirection-method-sqlserverstatement"></a>setFetchDirection-Methode (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Bietet [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] die Richtung, in der die Resultsetzeilen verarbeitet werden soll.  
  
> [!NOTE]  
>  Die Angabe dieser Methode wird vom JDBC-Treiber derzeit ignoriert.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
public final void setFetchDirection(int nDir)  
```  
  
#### <a name="parameters"></a>Parameter  
 *nDir*  
  
 Ein **Int** steht, die für die Zeile, die Verarbeitung Richtung, die der folgenden Werte sind möglich:  
  
 FETCH_FORWARD  
  
 FETCH_REVERSE  
  
 FETCH_UNKNOWN  
  
## <a name="exceptions"></a>Ausnahmen  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Hinweise  
 Diese SetFetchDirection-Methode wird von der SetFetchDirection-Methode in der java.sql.Statement-Schnittstelle angegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [SQLServerStatement-Elemente](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement-Klasse](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
