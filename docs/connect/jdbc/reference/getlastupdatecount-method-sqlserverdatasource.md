---
title: GetLastUpdateCount-Methode (SQLServerDataSource) | Microsoft Docs
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
apiname: SQLServerDataSource.getLastUpdateCount
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 4c4fbb24-0b02-42da-928c-a903bb591cc7
caps.latest.revision: "17"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: db133035f7145c61fb856fcfa308550d9883da17
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="getlastupdatecount-method-sqlserverdatasource"></a>getLastUpdateCount-Methode (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Gibt eine **booleschen** -Wert, der angibt, ob die LastUpdateCount-Eigenschaft aktiviert ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
public boolean getLastUpdateCount()  
```  
  
## <a name="return-value"></a>Rückgabewert  
 **"true"** Wenn "lastupdatecount" aktiviert ist. Andernfalls lautet der Wert **false**.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die LastUpdateCount-Eigenschaft auf festgelegt ist **"true"**, die [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] zurück nur die letzte updatezählung aus einer SQL-Anweisung an den Server übergeben. Wenn die LastUpdateCount-Eigenschaft, um festgelegt wird **"false"**, der Treiber alle updatezählungen zurückgegeben, durch Trigger, die möglicherweise ausgelöst haben – einschließlich jener zurück. Wenn die LastUpdateCount-Eigenschaft nicht festgelegt ist, gibt die GetLastUpdateCount-Methode den Standardwert von **"true"**.  
  
## <a name="see-also"></a>Siehe auch  
 [SQLServerDataSource-Elemente](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource-Klasse](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
