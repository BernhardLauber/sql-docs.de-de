---
title: DISCOVER_LOCATIONS-Rowset | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: schema-rowsets
ms.reviewer: 
ms.suite: sql
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to: SQL Server 2016 Preview
ms.assetid: 6d3a1171-8e4d-4022-ade0-b785cf795d70
caps.latest.revision: "7"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 898a8f95438f4b3fd749de72b4213af0acd9e3d0
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="discoverlocations-rowset"></a>DISCOVER_LOCATIONS-Rowset
  Gibt Informationen zum Inhalt einer Sicherungsdatei zurück. Sie müssen über die Berechtigung zum Zugreifen auf den Speicherort der Sicherungsdatei verfügen.  
  
## <a name="rowset-columns"></a>Rowsetspalten  
 Das **DISCOVER_LOCATIONS** -Rowset enthält die folgenden Spalten.  
  
|Spaltenname|Typindikator|Einschränkung|Description|  
|-----------------|--------------------|-----------------|-----------------|  
|**LOCATION_BACKUP_FILE_PATHNAME**|**DBTYPE_WSTR**|Erforderlich, siehe unten.|Der Speicherort der Sicherungsdatei.|  
|**LOCATION_PARTITION_OBJECTPATH**|**DBTYPE_WSTR**||Der Partitionspfad relativ zum Datenordner.|  
|**LOCATION_PARTITION_DATASOURCEID**|**DBTYPE_WSTR**||Die für die Verarbeitung der Partition verwendete Datenquellen-ID.|  
|**LOCATION_PARTITION_DATASOURCENAME**|**DBTYPE_WSTR**||Der Name der für die Verarbeitung verwendeten Datenquelle.|  
|**LOCATION_PARTITION_NAME**|**DBTYPE_WSTR**||Der Name der Partition.|  
|**LOCATION_PARTITION_SIZE**|**DBTYPE_WSTR**||Die ungefähre Größe der Partition.|  
|**LOCATION_CONNECTION_STRING**|**DBTYPE_WSTR**||Die Verbindungszeichenfolge der für die Verarbeitung verwendeten Datenquelle.|  
|**LOCATION_PARTITION_FOLDER**|**DBTYPE_WSTR**||Der ursprüngliche Speicherort dieser Partition, als die Sicherungsdatei erstellt wurde.|  
  
 Dieses Schemarowset ist nicht sortiert.  
  
## <a name="restriction-columns"></a>Einschränkungsspalten  
 Das **DISCOVER_LOCATIONS** -Rowset kann auf die in der folgenden Tabelle aufgeführten Spalten eingeschränkt werden.  
  
|Spaltenname|Typindikator|Einschränkungsstatus|  
|-----------------|--------------------|-----------------------|  
|**LOCATION_BACKUP_FILE_PATHNAME**|**DBTYPE_WSTR**|Required|  
|**LOCATION_PASSWORD PF_DBTYPE**|**DBTYPE_WSTR**|Erforderlich, falls während der Sicherung angegeben. Diese Einschränkung wird nicht verwendet, um die zurückgegebenen Zeilen einzuschränken. Wird verwendet, um das Kennwort bereitzustellen, damit auf den Speicherort zugegriffen werden kann.|  
  
## <a name="using-adomdnet-to-return-the-rowset"></a>Verwenden von ADOMD.NET zum Zurückgeben des Rowsets  
 Wenn Sie Metadaten mithilfe von ADOMD.NET und des Schemarowsets abrufen, können Sie entweder die GUID verwenden oder eine Referenz für ein Schemarowsetobjekt in der GetSchemaDataSet-Methode herstellen. Weitere Informationen finden Sie unter [Working with Schema Rowsets in ADOMD.NET](../../../analysis-services/multidimensional-models-adomd-net-client/retrieving-metadata-working-with-schema-rowsets.md).  
  
 Die folgende Tabelle enthält die GUID und die Zeichenfolgenwerte, die dieses Rowset identifizieren.  
  
|Argument|Wert|  
|--------------|-----------|  
|GUID|a07ccd92-8148-11d0-87bb-00c04fc33942|  
|ADOMDNAME|Speicherorte|  
  
## <a name="see-also"></a>Siehe auch  
 [XML for Analysis – Schemarowsets](../../../analysis-services/schema-rowsets/xml/xml-for-analysis-schema-rowsets.md)  
  
  
