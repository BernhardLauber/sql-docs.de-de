---
title: Unwrap-Methode (SQLServerPreparedStatement) | Microsoft Docs
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
ms.assetid: 8e3ec950-3ac1-4c28-9e97-ddce3bd46578
caps.latest.revision: "14"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: e78cd05244991952001f1dfc71785160227a528f
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="unwrap-method-sqlserverpreparedstatement"></a>unwrap-Methode (SQLServerPreparedStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Gibt ein Objekt, das für den Zugriff auf die angegebene Schnittstelle implementiert die [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]-spezifischen Methoden.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
public <T> T unwrap(Class<T> iface)  
```  
  
#### <a name="parameters"></a>Parameter  
 *iface*  
  
 Eine Klasse des Typs **T** zum Definieren einer Schnittstelle.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Objekt, von dem die angegebene Schnittstelle implementiert wird.  
  
## <a name="exceptions"></a>Ausnahmen  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Hinweise  
 Die [unwrap](../../../connect/jdbc/reference/unwrap-method-sqlserverpreparedstatement.md) Methode definiert ist, von der java.sql.Wrapper-Schnittstelle, die in der JDBC 4.0-Spezifikationen eingeführt wird.  
  
 Der JDBC-API-Erweiterungen, die für spezifisch sind, den Zugriff auf Anwendungen müssen möglicherweise die [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]. Die Unwrap-Methode unterstützt das Entpacken öffentlichen Klassen, die dieses Objekt erweitert, wenn es sich bei den Klassen herstellererweiterungen verfügbar gemacht.  
  
 Wenn diese Methode aufgerufen wird, wird das Objekt in der folgenden Klassen entpackt: [SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md) und [SQLServerPreparedStatement](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md).  
  
 Beispielcode hierzu finden Sie unter [unwrap-Methode &#40; SQLServerCallableStatement &#41; ](../../../connect/jdbc/reference/unwrap-method-sqlservercallablestatement.md).  
  
 Weitere Informationen finden Sie unter [Wrapper und Schnittstellen](../../../connect/jdbc/wrappers-and-interfaces.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IsWrapperFor-Methode &#40; SQLServerPreparedStatement &#41;](../../../connect/jdbc/reference/iswrapperfor-method-sqlserverpreparedstatement.md)   
 [SQLServerPreparedStatement-Elemente](../../../connect/jdbc/reference/sqlserverpreparedstatement-members.md)   
 [SQLServerPreparedStatement-Klasse](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md)  
  
  
