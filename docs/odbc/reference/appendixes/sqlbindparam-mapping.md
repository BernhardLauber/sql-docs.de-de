---
title: SQLBindParam Zuordnung | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: odbc
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQLBindparam function [ODBC], mapping
- mapping deprecated functions [ODBC], SQLBindParam
ms.assetid: 375f8f24-36de-4946-916e-c75abc6f070d
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 1a2c78cd97b6577be8d11d07325165d6d82cd895
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="sqlbindparam-mapping"></a>SQLBindParam-Zuordnung
**SQLBindParam** nicht tatsächlich aufgerufen werden als veraltet markierte da war nie es ODBC; allerdings es weiterhin duplizierte Funktionalität dar – der Treiber-Manager muss exportiert werden, da ISO "und" Open Group-kompatible Anwendungen verwendet werden werden. Da **SQLBindParameter** enthält die gesamte Funktionalität des **SQLBindParam**, **SQLBindParam** werden zugeordnet sein, auf der Basis von **SQLBindParameter** (wenn die zugrunde liegenden Treiber ist ein ODBC 3.*.x* Treiber). Eine ODBC 3.*.x* Treiber muss nicht implementieren **SQLBindParam**.  
  
## <a name="remarks"></a>Hinweise  
 Wenn beim folgenden Aufruf **SQLBindParam** erfolgt:  
  
```  
SQLBindParam(   StatementHandle,    ParameterNumber,    ValueType,    ParameterType,    ColumnSize,    DecimalDigits,    ParameterValuePtr,    StrLen_or_IndPtr)  
```  
  
 der Treiber-Manager ruft **SQLBindParameter** im Treiber wie folgt:  
  
```  
SQLBindParameter(   StatementHandle,    ParameterNumber,    SQL_PARAM_INPUT,    ValueType,    ParameterType,    ColumnSize,    DecimalDigits,    ParameterValuePtr,    BufferLength,    StrLen_or_IndPtr)  
```  
  
 Finden Sie unter [ODBC-64-Bit-Informationen](../../../odbc/reference/odbc-64-bit-information.md), wenn die Anwendung auf einem 64-Bit-Betriebssystem ausgeführt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Zuordnung veralteter Funktionen](../../../odbc/reference/appendixes/mapping-deprecated-functions.md)
