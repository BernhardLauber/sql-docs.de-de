---
title: Bcp_columns | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: ''
ms.component: native-client-odbc-extensions-bulk-copy-functions
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- bcp_columns
apilocation:
- sqlncli11.dll
apitype: DLLExport
helpviewer_keywords:
- bcp_columns function
ms.assetid: 5376f6fe-9508-439a-8c66-778d77f19ac3
caps.latest.revision: 31
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
monikerRange: '>= aps-pdw-2016 || = azuresqldb-current || = azure-sqldw-latest || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: c5a151e55b45c57a461868dcfd603e7af5d490c7
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="bcpcolumns"></a>bcp_columns
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  Legt die Gesamtanzahl der Spalten fest, die in der Benutzerdatei gefunden wurden und mit einem Massenkopiervorgang in oder aus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendet werden sollen. [Bcp_setbulkmode](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-setbulkmode.md) anstelle Bcp_columns verwendet werden können und [Bcp_colfmt](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
RETCODE bcp_columns (  
        HDBC hdbc,  
        INT nColumns);  
```  
  
## <a name="arguments"></a>Argumente  
 *HDBC*  
 Das für den Massenkopiervorgang aktivierte ODBC-Verbindungshandle.  
  
 *nColumns*  
 Die Gesamtzahl der Spalten in der Benutzerdatei. Auch wenn Sie zum Massenkopieren von Daten aus der Benutzerdatei zum Vorbereiten einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Tabelle und nicht alle Spalten in der Benutzerdatei kopieren möchten, müssen Sie immer noch festlegen *nColumns* auf die Gesamtzahl der benutzerdateispalten.  
  
## <a name="returns"></a>Rückgabewert  
 SUCCEED oder FAIL.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion kann aufgerufen werden, erst nach dem [Bcp_init](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) mit einem gültigen Dateinamen aufgerufen wurde.  
  
 Sie sollten diese Funktion nur aufrufen, wenn Sie ein Benutzerdateiformat verwenden möchten, das sich vom Standardformat unterscheidet. Weitere Informationen über eine Beschreibung des Benutzer-Standardformats für finden Sie unter **Bcp_init**.  
  
 Nach dem Aufruf **Bcp_columns**, rufen Sie [Bcp_colfmt](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) für jede Spalte in der Benutzerdatei, um benutzerdefinierte Dateiformat vollständig zu definieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen zum Massenkopieren](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
