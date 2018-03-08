---
title: GetServerName-Methode (SQLServerDataSource) | Microsoft Docs
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
apiname: SQLServerDataSource.getServerName
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 3004ed22-5d69-4dd0-8761-d39f0b7dde13
caps.latest.revision: "9"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 2302fded14543647060ce8ddcff4b59e0911c942
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="getservername-method-sqlserverdatasource"></a>getServerName-Methode (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Gibt den Namen des der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] Instanz.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
public java.lang.String getServerName()  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein **Zeichenfolge** , den Servernamen oder Null enthält, wenn kein Wert festgelegt ist.  
  
## <a name="remarks"></a>Hinweise  
 Der Servername ist der Hostname des Zielcomputers, auf denen ausgeführt wird, ist [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)]. Wenn die GetServerName-Eigenschaft nicht festgelegt ist, von getServerName den Standardwert NULL.  
  
## <a name="see-also"></a>Siehe auch  
 [SQLServerDataSource-Elemente](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource-Klasse](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
