---
title: 64-Bit-Ganzzahl-Strukturen | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: odbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- C data types [ODBC], 64-bit integer structures
- data types [ODBC], C data types
- 64-bit integer structures [ODBC]
ms.assetid: ac80c798-d9b2-4430-85ed-bd2461db0ac7
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 15176629e0154b59c1dfadd9d58f755eb2c423ed
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="64-bit-integer-structures"></a>64-Bit-Ganzzahl-Strukturen
Der C-Typ für die SQL_C_SBIGINT und SQL_C_UBIGINT-Datentypbezeichner auf Microsoft C-Compiler ist _int64. Wenn ein Compiler als ein Microsoft® C-Compiler verwendet wird, kann die C-Typ unterscheiden. Wenn der Compiler die 64-Bit-Ganzzahlen systemeigene Unterstützung bietet, sollten den Treiber oder die Anwendung ODBCINT64 werden von den systemeigenen 64-Bit-Ganzzahl-Typ definieren. Wenn der Compiler 64-Bit-Ganzzahlen nicht systemintern unterstützt wird, kann eine Anwendung oder Treiber definieren die folgenden Strukturen aus, um sicherzustellen, dass sie Zugriff auf diese Daten hat:  
  
```  
typedef struct{  
SQLUINTEGER dwLowWord;  
SQLUINTEGER dwHighWord;  
} SQLUBIGINT  
  
typedef struct{  
SQLUINTEGER dwLowWord;  
SQLINTEGER sdwHighWord;  
} SQLBIGINT  
```  
  
 Diese Strukturen sollten eine 8-Byte-Grenze ausgerichtet sein, da eine 64-Bit-Ganzzahl, die 8-Byte-Grenze ausgerichtet ist.
