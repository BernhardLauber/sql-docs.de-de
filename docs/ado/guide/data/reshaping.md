---
title: Umformen | Microsoft Docs
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology: drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- reshaping previously shaped Recordset [ADO]
- data shaping [ADO], reshaping
ms.assetid: b1c965b7-3dad-4de6-9e0e-502ca8785be3
caps.latest.revision: "14"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: f00f6a724f4ab500b82d44e06e78ae0af1fe955d
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="reshaping"></a>Umformen
Ein **Recordset** erstellt eine-Klausel einer Form Befehl zugewiesen werden kann ein *Alias* Name (in der Regel mit dem AS-Schlüsselwort). Der Alias des eine geformten **Recordset** in einem ganz anderen Befehl verwiesen werden kann. D. h., Sie können wiederverwenden, oder *umformen*, eine zuvor geformten **Recordset** in einem neuen Shape-Befehl. Um dieses Feature zu unterstützen, stellt ADO eine Eigenschaft bereit, mit denen [umformen Namen](../../../ado/reference/ado-api/reshape-name-property-dynamic-ado.md).  
  
 Umformen hat zwei Hauptfunktionen. Der erste Schritt besteht im Zuordnen einer vorhandenen **Recordset** mit einem neuen übergeordneten **Recordset**.  
  
## <a name="example"></a>Beispiel  
  
```  
rs1.Open "SHAPE {select * from Customers} " & _  
         "APPEND ({select * from Orders} AS chapOrders " & _  
         "RELATE CustomerID to CustomerID)", cn  
  
rs2.Open "SHAPE {select * from Employees} " & _  
         "APPEND (chapOrders RELATE EmployeeID to EmployeeID)", cn  
```  
  
 Die zweite Funktion wird für nicht in Kapitel unterteilten den Zugriff auf vorhandene untergeordnete **Recordset** Objekte, mit der Syntax "Form" \<Recordset umformen Name > ".  
  
> [!NOTE]
>  Spalten kann nicht angefügt werden, um eine vorhandene **Recordset**, Neustrukturieren eine parametrisierte **Recordset** oder **Recordset** Objekte in alle Beteiligten COMPUTE-Klausel, oder führen Vorgänge für ein beliebiges aggregieren **Recordset** Nachfolger der **Recordset** Form wird. Die **Recordset** Form wird und die neue Form Befehl müssen beide die gleiche verwenden [Verbindung](../../../ado/reference/ado-api/connection-object-ado.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Data Shaping Example (Beispiele der Datenstrukturierung)](../../../ado/guide/data/data-shaping-example.md)
