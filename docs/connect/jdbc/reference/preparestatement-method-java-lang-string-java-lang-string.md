---
title: PrepareStatement-Methode (java.lang.String, java.lang.String) | Microsoft Docs
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
apiname: SQLServerConnection.prepareStatement
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: e0db2871-3a5f-4fcc-af61-92333042dcd1
caps.latest.revision: "9"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 2ba4e82c2e37807b886e50fa0613cc3990203a0e
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="preparestatement-method-javalangstring-javalangstring"></a>PrepareStatement-Methode (java.lang.String, java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Erstellt eine [SQLServerPreparedStatement](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md) Objekt zum Senden parametrisierter SQL-Anweisungen in der Datenbank.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
public java.sql.PreparedStatement prepareStatement(java.lang.String sql,  
                                                   java.lang.String[] columnNames)  
```  
  
#### <a name="parameters"></a>Parameter  
 *SQL*  
  
 Ein **Zeichenfolge** , die eine SQL-Anweisung enthält.  
  
 *"ColumnNames"*  
  
 Ein **Zeichenfolge** Array von Spaltennamen.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein PreparedStatement-Objekt.  
  
## <a name="exceptions"></a>Ausnahmen  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Hinweise  
 Diese PrepareStatement-Methode wird von der PrepareStatement-Methode in der java.sql.Connection-Schnittstelle angegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [PrepareStatement-Methode &#40; SQLServerConnection &#41;](../../../connect/jdbc/reference/preparestatement-method-sqlserverconnection.md)   
 [SQLServerConnection-Elemente](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection-Klasse](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
