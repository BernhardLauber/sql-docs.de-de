---
title: SetNCharacterStream-Methode auf Leserobjekt - Int | Microsoft Docs
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
ms.assetid: 7732746b-eda5-469e-8567-e8546c4d81cd
caps.latest.revision: "22"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: a06f22774bfedf22f02d4daf3cb613aeac64db51
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="setncharacterstream-method-int-javaioreader"></a>setNCharacterStream-Methode (int, java.io.Reader)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Legt den angegebenen Parameter mit dem angegebenen Reader-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
public final void setNCharacterStream(int parameterIndex,  
                                                 java.io.Reader value)  
```  
  
#### <a name="parameters"></a>Parameter  
 *parameterIndex*  
  
 Ein **Int** , der die Indexnummer des Parameters angibt.  
  
 *value*  
  
 Ein Readerobjekt, das den Parameterwert enthält.  
  
## <a name="exceptions"></a>Ausnahmen  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Hinweise  
 Diese SetNCharacterStream-Methode wird von der SetNCharacterStream-Methode in der java.sql.PreparedStatement-Schnittstelle angegeben.  
  
 Diese Methode sollte verwendet werden, für die **NCHAR**, **NVARCHAR**, **NTEXT**, und **XML** -Datentypen.  
  
## <a name="see-also"></a>Siehe auch  
 [SetNCharacterStream-Methode &#40; SQLServerPreparedStatement &#41;](../../../connect/jdbc/reference/setncharacterstream-method-sqlserverpreparedstatement.md)   
 [SQLServerPreparedStatement-Elemente](../../../connect/jdbc/reference/sqlserverpreparedstatement-members.md)  
  
  
