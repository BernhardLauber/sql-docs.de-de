---
title: GetBinaryStream-Methode (Int) | Microsoft Docs
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
apiname: SQLServerResultSet.getBinaryStream (int)
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: de22a6c4-1ba3-4ed0-91a2-bf235c2ceec3
caps.latest.revision: "10"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 7ff5be6d0a47439f1226ff098c747cd73bb4c991
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="getbinarystream-method-int"></a>getBinaryStream-Methode (int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Ruft den Wert des angegebenen Spaltenindexes in der aktuellen Zeile dieses [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) Objekts als Binärdatenstrom nicht interpretierter Bytes.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
public java.io.InputStream getBinaryStream(int columnIndex)  
```  
  
#### <a name="parameters"></a>Parameter  
 *columnIndex*  
  
 Ein **Int** , der den Spaltenindex angibt.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein InputStream-Objekt.  
  
## <a name="exceptions"></a>Ausnahmen  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Hinweise  
 Diese GetBinaryStream-Methode wird von der GetBinaryStream-Methode in der java.sql.ResultSet-Schnittstelle angegeben.  
  
 Diese Methode kann verwendet werden, nur mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] Binary, Varbinary, varbinary(max) und Image-Datentypen. Bei Verwendung dieser Methode mit anderen Datentypen wird eine Ausnahme ausgelöst.  
  
 Nachdem der Wert von der Methode als Datenstrom empfangen wurde, kann der Wert in Ausschnitten aus dem Strom gelesen werden. Diese Methode ist besonders zum Abrufen umfangreicher LONGVARBINARY-Werte geeignet.  
  
> [!NOTE]  
>  Alle Daten im zurückgegebenen Datenstrom müssen vor dem Abrufen des Werts aus einer anderen Spalte gelesen werden. Der nächste Aufruf einer Getter-Methode schließt den Datenstrom implizit. Darüber hinaus kann ein Datenstrom 0 zurückgeben, wenn die InputStream.available-Methode aufgerufen wird, ob Daten verfügbar oder nicht.  
  
## <a name="see-also"></a>Siehe auch  
 [GetBinaryStream-Methode &#40; SQLServerResultSet &#41;](../../../connect/jdbc/reference/getbinarystream-method-sqlserverresultset.md)   
 [SQLServerResultSet-Elemente](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet-Klasse](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
