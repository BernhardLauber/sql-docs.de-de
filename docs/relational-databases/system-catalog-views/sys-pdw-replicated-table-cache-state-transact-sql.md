---
title: Sys.pdw_replicated_table_cache_state (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 07/03/2017
ms.prod: ''
ms.prod_service: sql-data-warehouse
ms.service: sql-data-warehouse
ms.component: system-catalog-views
ms.reviewer: barbkess
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- TSQL
author: ronortloff
ms.author: rortloff
manager: craigg
ms.workload: Inactive
monikerRange: = azure-sqldw-latest || = sqlallproducts-allversions
ms.openlocfilehash: 007c65e55302532e6dd3f4fbd5df701d33c11616
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="syspdwreplicatedtablecachestate-transact-sql"></a>Sys.pdw_replicated_table_cache_state (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-asdw-xxx-md](../../includes/tsql-appliesto-xxxxxx-xxxx-asdw-xxx-md.md)]

  Gibt den Status des Caches, die einer replizierten Tabelle nach zugeordneten **Object_id**.  
  
|Spaltenname|Datentyp|Description|Bereich|  
|-----------------|---------------|-----------------|-----------|  
|object_id|**int**|Die Objekt-ID für die Tabelle. Finden Sie unter [sys.objects &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md).<br /><br /> **Object_id** ist der Schlüssel für diese Ansicht.||  
|state|**nvarchar(40)**|Der Status der replizierten Tabelle Cache für diese Tabelle.|"NotReady", "Bereit"|  
  
## <a name="example"></a>Beispiel
In diesem Beispiel verknüpft sys.pdw_replicated_table_cache_state mit sys.tables zum Abrufen der Tabellenname und den Status des Caches replizierten Tabelle.

```sql
SELECT t.[name], p.[object_id], p.[state]
  FROM sys.pdw_replicated_table_cache_state p 
  JOIN sys.tables t ON t.object_id = p.object_id
```



## <a name="next-steps"></a>Nächste Schritte  
 Eine Übersicht über die Katalogsichten für SQL Data Warehouse und Parallel Data Warehouse finden Sie unter [SQL Data Warehouse und Parallel Data Warehouse-Katalogsichten](../../relational-databases/system-catalog-views/sql-data-warehouse-and-parallel-data-warehouse-catalog-views.md).   
  
