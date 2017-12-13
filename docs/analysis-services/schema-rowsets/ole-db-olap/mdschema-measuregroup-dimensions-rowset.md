---
title: MDSCHEMA_MEASUREGROUP_DIMENSIONS-Rowset | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname: MDSCHEMA_MEASUREGROUP_DIMENSIONS
apitype: NA
applies_to: SQL Server 2016 Preview
helpviewer_keywords: MDSCHEMA_MEASUREGROUP_DIMENSIONS rowset
ms.assetid: c731c06a-7382-4e50-ba0e-d8cee3ab4f28
caps.latest.revision: "14"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 421ed99b405deadd404d6e68138a6a29a9d757fc
ms.sourcegitcommit: f1a6944f95dd015d3774a25c14a919421b09151b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2017
---
# <a name="mdschemameasuregroupdimensions-rowset"></a>MDSCHEMA_MEASUREGROUP_DIMENSIONS-Rowset
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Listet die Dimensionen der Measuregruppe an.  
  
## <a name="rowset-columns"></a>Rowsetspalten  
 Das **MDSCHEMA_MEASUREGROUP_DIMENSIONS** -Rowset enthält die folgenden Spalten.  
  
|Spaltenname|Typindikator|Länge|Description|  
|-----------------|--------------------|------------|-----------------|  
|**CATALOG_NAME**|**DBTYPE_WSTR**||Der Name des Katalogs, zu dem diese Measuregruppe gehört. **NULL** , wenn der Anbieter keine Kataloge unterstützt.|  
|**SCHEMA_NAME**|**DBTYPE_WSTR**||Nicht unterstützt.|  
|**CUBE_NAME**|**DBTYPE_WSTR**||Der Name des Cubes, zu dem diese Measuregruppe gehört.|  
|**MEASUREGROUP_NAME**|**DBTYPE_WSTR**||Der Name der Measuregruppe.|  
|**MEASUREGROUP_CARDINALITY**|**DBTYPE_WSTR**||Die Anzahl der Instanzen, die ein Measure in der Measuregruppe für ein einzelnes Dimensionselement haben kann. Zulässige Werte:<br /><br /> **EINE**<br /><br /> **VIELE**|  
|**DIMENSION_UNIQUE_NAME**|**DBTYPE_WSTR**||Der eindeutige Name für die Dimension.|  
|**DIMENSION_CARDINALITY**|**DBTYPE_WSTR**||Die Anzahl der Instanzen, die ein Dimensionselement für eine einzelne Instanz eines Measures der Measuregruppe haben kann. Zulässige Werte:<br /><br /> **EINE**<br /><br /> **VIELE**|  
|**DIMENSION_IS_VISIBLE**|**DBTYPE_BOOL**||Ein boolescher Wert, der angibt, ob die Hierarchien in der Dimension sichtbar sind.<br /><br /> Gibt **TRUE** zurück, wenn eine oder mehrere Hierarchien in der Dimension sichtbar sind; andernfalls wird **FALSE**zurückgegeben.|  
|**DIMENSION_IS_FACT_DIMENSION**|**DBTYPE_BOOL**||Ein boolescher Wert, der angibt, ob die Dimension eine Faktendimension ist.<br /><br /> Gibt **TRUE** zurück, wenn die Dimension eine Faktendimension ist; andernfalls wird **FALSE**zurückgegeben.|  
|**DIMENSION_PATH**|**DBTYPE_HCHAPTER**||Eine Liste der Dimensionen für die Referenzdimension.|  
|**DIMENSION_GRANULARITY**|**DBTYPE_WSTR**||Der eindeutige Name der Granularitätshierarchie.|  
  
 Das Rowset unterstützt die Sortierung nach **CATALOG_NAME**, **SCHEMA_NAME**, **CUBE_NAME**, **MEASUREGROUP_NAME**und **DIMENSION_UNIQUE_NAME**.  
  
## <a name="restriction-columns"></a>Einschränkungsspalten  
 Das **MDSCHEMA_MEASUREGROUP_DIMENSIONS** -Rowset kann auf die in der folgenden Tabelle aufgeführten Spalten eingeschränkt werden.  
  
|Spaltenname|Typindikator|Einschränkungsstatus|  
|-----------------|--------------------|-----------------------|  
|**CATALOG_NAME**|**DBTYPE_WSTR**|Optional.|  
|**SCHEMA_NAME**|**DBTYPE_WSTR**|Optional.|  
|**CUBE_NAME**|**DBTYPE_WSTR**|Optional.|  
|**MEASUREGROUP_NAME**|**DBTYPE_WSTR**|Optional.|  
|**DIMENSION_UNIQUE_NAME**|**DBTYPE_WSTR**|Optional.|  
|**DIMENSION_VISIBILITY**|**DBTYPE_UI2**|(Optional) Eine Bitmap mit einem der folgenden gültigen Werte:<br /><br /> 1 Sichtbar<br /><br /> 2 Nicht sichtbar<br /><br /> Die Standardeinschränkung besitzt den Wert 1.|  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB für OLAP-Schemarowsets](../../../analysis-services/schema-rowsets/ole-db-olap/ole-db-for-olap-schema-rowsets.md)  
  
  
