---
title: Verwenden ein Verbindungsobjekt | Microsoft Docs
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connections [ADO]
ms.assetid: 4b34f971-5699-43e7-9b15-137d334fa66e
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: e27a3da94c2699e2281d331e6aa1fff4b9a62001
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="using-a-connection-object"></a>Verwenden ein Verbindungsobjekt
Vor dem Öffnen einer **Verbindung** -Objekt, müssen Sie bestimmte Informationen über die Datenquelle und die Art der Verbindung definieren. Die meisten dieser Informationen wird aufrechterhalten, indem die *"ConnectionString"* Parameter von der [Open-Methode](../../../ado/reference/ado-api/open-method-ado-connection.md) auf die **Verbindung** -Objekt, oder durch die ["ConnectionString" Eigenschaft](../../../ado/reference/ado-api/connectionstring-property-ado.md) auf die **Verbindung** Objekt. Eine Verbindungszeichenfolge besteht aus einer Liste von Argument-Wert-Paaren, die durch Semikolons voneinander getrennt werden, mit den Werten, die in einfache Anführungszeichen eingeschlossen. Beispiel:  
  
```  
Dim sConn As String  
sConn = "Provider='SQLOLEDB';Data Source='MySqlServer';" & _  
             "Initial Catalog='Northwind';Integrated Security='SSPI';"  
```  
  
> [!NOTE]
>  Sie können auch einen ODBC-Daten Datenquellennamen (DSN) oder eine Data Link (UDL)-Datei in einer Verbindungszeichenfolge angeben. Weitere Informationen zu DSNs, finden Sie unter [Datenquellen verwalten](../../../odbc/admin/managing-data-sources.md) in der ODBC Programmer's Reference. Weitere Informationen zu UDLs, finden Sie unter [Data Link API Overview](http://msdn.microsoft.com/en-us/95c180ea-bd4f-4dca-b95a-576afd135bbc) in der OLE DB Programmer's Reference.  
  
 In der Regel herstellen eine Verbindung durch Aufrufen der **Connection.Open** Methode mit einem entsprechenden eine *Verbindungszeichenfolge* als Parameter. Im folgenden Visual Basic-Codeausschnitt ist ein Beispiel gezeigt:  
  
```  
Dim oConn As ADODB.Connection  
Dim oRs As ADODB.Recordset  
Dim sConn As String  
Dim sSQL as String  
  
' Open a connection.  
Set oConn = New ADODB.Connection  
.Open   
  
' Make a query over the connection.  
sSQL = "SELECT ProductID, ProductName, CategoryID, UnitPrice " & _  
             "FROM Products"  
Set oRs = New ADODB.Recordset  
oRs.Open sSQL, , adOpenStatic, adLockBatchOptimistic, adCmdText  
  
MsgBox oRs.RecordCount  
  
' Close the connection.  
oConn.Close  
Set oConn = Nothing  
  
```  
  
 Hier **oRs.Open** nimmt eine **Verbindung** Objekt (*oConn*) als Wert der Variable seine *ActiveConnection* Parameter. Darüber hinaus die **Connection.CursorLocation** Eigenschaft geht davon aus, der Standardwert von **AdUseServer**. Vergleichen Sie diese Option, um die [HelloData](../../../ado/guide/data/hellodata-a-simple-ado-application.md) Beispiel im vorherigen Abschnitt. Die folgende Anweisung führt zu Laufzeitfehlern führen.  
  
```  
oRs.MarshalOptions = adMarshalModifiedOnly  
' Disconnect the Recordset.  
Set oRs.ActiveConnection = Nothing  
```
