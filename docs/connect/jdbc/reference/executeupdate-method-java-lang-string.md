---
title: ExecuteUpdate-Methode (java.lang.String, int[]) | Microsoft Docs
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
apiname: SQLServerStatement.executeUpdate (java.lang.String, int[])
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 7b3d5b60-4285-4047-b13e-106754ca0d98
caps.latest.revision: "13"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 7f821cb347157e7f6eb400ed8f530035ba81d494
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="executeupdate-method-javalangstring-int"></a>executeUpdate-Methode (java.lang.String, int[])
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Führt die angegebene SQL-Anweisung aus und signalisiert [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] , dass die automatisch generierten Schlüssel, die im angegebenen Array angegeben sind zum Abrufen verfügbar gemacht werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
public final int executeUpdate(java.lang.String sql,  
                               int[] columnIndexes)  
```  
  
#### <a name="parameters"></a>Parameter  
 *SQL*  
  
 Ein **Zeichenfolge** , die eine SQL-Anweisung enthält.  
  
 *columnIndexes*  
  
 Ein Array von int-Werten zum Angeben der Spaltenindizes der automatisch generierten Schlüssel, die verfügbar gemacht werden sollen.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein **Int** , der die Anzahl der betroffenen Zeilen, oder 0 bei Verwendung einer DDL-Anweisung angibt.  
  
## <a name="exceptions"></a>Ausnahmen  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Hinweise  
 Diese ExecuteUpdate-Methode wird von der ExecuteUpdate-Methode in der java.sql.Statement-Schnittstelle angegeben.  
  
 Wenn eine updatezählung eine gespeicherte Prozedur auszuführen führt, die größer als 1 ist, oder, generiert mehr als ein Resultset, verwenden, die [ausführen](../../../connect/jdbc/reference/execute-method-sqlserverstatement.md) Methode zum Ausführen der gespeicherten Prozedur.  
  
## <a name="see-also"></a>Siehe auch  
 [ExecuteUpdate-Methode &#40; SQLServerStatement &#41;](../../../connect/jdbc/reference/executeupdate-method-sqlserverstatement.md)   
 [SQLServerStatement-Elemente](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement-Klasse](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
