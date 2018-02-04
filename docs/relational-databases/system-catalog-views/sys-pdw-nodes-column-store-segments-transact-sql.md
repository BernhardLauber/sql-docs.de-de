---
title: sys.pdw_nodes_column_store_segments (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
ms.prod: 
ms.prod_service: sql-data-warehouse, pdw
ms.service: sql-data-warehouse
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: e2fdf8e9-1b74-4682-b2d4-c62aca053d7f
caps.latest.revision: 
author: barbkess
ms.author: barbkess
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: c5982fa99effc211d23c7e92557d96e20d131ad4
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2018
---
# <a name="syspdwnodescolumnstoresegments-transact-sql"></a>sys.pdw_nodes_column_store_segments (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md.md)]

  Enthält eine Zeile für jede Spalte in einem columnstore-Index.  
  
|Spaltenname|Datentyp|Description|  
|-----------------|---------------|-----------------|  
|**partition_id**|**bigint**|Gibt die Partitions-ID an. Ist innerhalb einer Datenbank eindeutig.|  
|**hobt_id**|**bigint**|ID des Heaps oder B-Struktur-Indexes (hobt) für die Tabelle, die diesen columnstore-Index aufweist.|  
|**column_id**|**int**|ID der columnstore-Spalte.|  
|**segment_id**|**int**|Die ID des Spaltensegments.|  
|**version**|**int**|Die Version des Spaltensegmentformats.|  
|**encoding_type**|**int**|Der für dieses Segment verwendete Codierungstyp.|  
|**row_count**|**int**|Die Anzahl der Zeilen in der Zeilengruppe.|  
|**has_nulls**|**int**|1, wenn das Spaltensegment NULL-Werte enthält.|  
|**base_id**|**bigint**|Basiswert-Id, wenn der Codierungstyp 1 verwendet wird.  Wenn der Codierungstyp 1 nicht verwendet wird, wird Base_id auf 1 festgelegt.|  
|**magnitude**|**float**|Größe, wenn der Codierungstyp 1 verwendet wird.  Wenn der Codierungstyp 1 nicht verwendet wird, wird Magnitude auf 1 festgelegt.|  
|**primary__dictionary_id**|**int**|Die ID des primären Wörterbuchs.|  
|**secondary_dictionary_id**|**int**|Die ID des sekundären Wörterbuchs. Gibt -1 zurück, wenn kein sekundäres Wörterbuch vorhanden ist.|  
|**min_data_id**|**bigint**|Die minimale Daten-ID im Spaltensegment.|  
|**max_data_id**|**bigint**|Die maximale Daten-ID im Spaltensegment.|  
|**null_value**|**bigint**|Ein Wert, der zum Darstellen von NULL-Werten verwendet wird.|  
|**on_disk_size**|**bigint**|Die Größe des Segments in Byte.|  
|**pdw_node_id**|**int**|Der eindeutige Bezeichner einer [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] Hinweis.|  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Beispiele: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] und[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 Die folgende Abfrage gibt Informationen zu Segmenten eines columnstore-Indexes zurück.  
  
```sql  
SELECT i.name, p.object_id, p.index_id, i.type_desc,   
    COUNT(*) AS number_of_segments  
FROM sys.column_store_segments AS s   
INNER JOIN sys.partitions AS p   
    ON s.hobt_id = p.hobt_id   
INNER JOIN sys.indexes AS i   
    ON p.object_id = i.object_id  
WHERE i.type = 6  
GROUP BY i.name, p.object_id, p.index_id, i.type_desc ;  
```  
  
 Verknüpfen Sie sys.pdw_nodes_column_store_segments mit anderen Systemtabellen bestimmen, die Zeilenanzahl und Größe der Segmente, die auf dem Datenträger.  
  
```  
SELECT o.name, css.hobt_id, css. column_id, css.pdw_node_id, css.row_count, css.on_disk_size  
FROM sys.pdw_nodes_column_store_segments AS css  
JOIN sys.pdw_nodes_partitions AS pnp  
    ON css.partition_id = pnp.partition_id  
JOIN sys.pdw_nodes_tables AS part  
    ON pnp.object_id = part.object_id   
    AND pnp.pdw_node_id = part.pdw_node_id  
JOIN sys.pdw_table_mappings AS TMap  
    ON part.name = TMap.physical_name  
JOIN sys.objects AS o  
    ON TMap.object_id = o.object_id  
ORDER BY css.hobt_id, css.column_id;  
```  
  
## <a name="permissions"></a>Berechtigungen  
 Erfordert **VIEW SERVER STATE** Berechtigung.  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Datawarehouse und Parallel Datawarehouse-Katalogsichten](../../relational-databases/system-catalog-views/sql-data-warehouse-and-parallel-data-warehouse-catalog-views.md)   
 [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](../../t-sql/statements/create-columnstore-index-transact-sql.md)   
 [sys.pdw_nodes_column_store_row_groups &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-pdw-nodes-column-store-row-groups-transact-sql.md)   
 [sys.pdw_nodes_column_store_dictionaries &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-pdw-nodes-column-store-dictionaries-transact-sql.md)  
  
  

