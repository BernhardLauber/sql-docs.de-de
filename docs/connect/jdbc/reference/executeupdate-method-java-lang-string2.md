---
title: ExecuteUpdate-Methode (java.lang.String) | Microsoft Docs
ms.custom: 
ms.date: 02/07/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: jdbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname: SQLServerPreparedStatement.executeUpdate (java.lang.String)
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 91ecb1cd-001d-4ac9-9ae8-5db05c3c2959
caps.latest.revision: "11"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 7a78fe10c14c54b5e2bea1cc4030a4f5d8d83fa1
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="executeupdate-method-javalangstring"></a>executeUpdate-Methode (java.lang.String)

Führt die angegebene SQL-Anweisung aus. Hierbei kann es sich um eine Anweisung vom Typ "INSERT", "UPDATE", "MERGE" oder "DELETE" oder um eine SQL-Anweisung handeln, von der nichts zurückgegeben wird (beispielsweise eine SQL-DDL-Anweisung).

## <a name="syntax"></a>Syntax

```
public final int executeUpdate(java.lang.String sql)
```

#### <a name="parameters"></a>Parameter
*SQL*

Ein **Zeichenfolge** , die die SQL-Anweisung enthält.

## <a name="return-value"></a>Rückgabewert
Ein **Int** , der die Anzahl der betroffenen Zeilen, oder 0 bei Verwendung einer DDL-Anweisung angibt.

## <a name="exceptions"></a>Ausnahmen
[SQLServerException](./sqlserverexception-class.md)

## <a name="remarks"></a>Hinweise
Diese ExecuteUpdate-Methode wird von der ExecuteUpdate-Methode in der java.sql.PreparedStatement-Schnittstelle angegeben.

Beim Aufrufen dieser Methode führt eine Ausnahme ausgelöst, da die SQL-Anweisung für die SQLServerPreparedStatement-Objekt angegeben wird, wenn das Objekt erstellt wird.

## <a name="see-also"></a>Siehe auch

[ExecuteUpdate-Methode &#40; SQLServerPreparedStatement &#41;](./executeupdate-method-sqlserverpreparedstatement.md)

[SQLServerPreparedStatement-Elemente](./sqlserverpreparedstatement-members.md)

[SQLServerPreparedStatement-Klasse](./sqlserverpreparedstatement-class.md)
