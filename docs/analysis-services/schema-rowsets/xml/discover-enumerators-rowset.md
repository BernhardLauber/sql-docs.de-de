---
title: DISCOVER_ENUMERATORS-Rowset | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
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
apiname: DISCOVER_ENUMERATORS
apitype: NA
applies_to: SQL Server 2016 Preview
helpviewer_keywords: DISCOVER_ENUMERATORS rowset
ms.assetid: ddc7b13c-3135-4419-8166-eddd459167da
caps.latest.revision: "31"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: eda9b5a7563ff6d368d651f62c3ea6ab4a2d7630
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="discoverenumerators-rowset"></a>DISCOVER_ENUMERATORS-Rowset
  Gibt eine Liste mit Namen, Datentypen und Enumerationswerten von Enumeratoren zurück, die vom [!INCLUDE[msCoName](../../../includes/msconame-md.md)] XML for Analysis-Anbieter (XMLA) für eine bestimmte Datenquelle unterstützt werden. Der XMLA-Anbieter veröffentlicht alle Enumerationskonstanten, die er erkennt.  
  
 Beim Aufrufen der [Discover](../../../analysis-services/xmla/xml-elements-methods-discover.md) Methode mit der **DISCOVER_ENUMERATORS** Enumerationswert in der [RequestType](../../../analysis-services/xmla/xml-elements-properties/requesttype-element-xmla.md) Element, das **Discover** Methode gibt die **DISCOVER_ENUMERATORS** -Schemarowsets.  
  
## <a name="rowset-columns"></a>Rowsetspalten  
 Für jeden Enumerator gibt es mehrere Elemente, eines für jeden Wert in der Enumeration. Das Rowset, das jeden Enumerator repräsentiert, ist "flat", und der Name des Enumerators kann für Elemente, die zur selben Enumeration gehören, wiederholt werden.  
  
 Das **DISCOVER_ENUMERATORS** -Rowset enthält die folgenden Spalten.  
  
|Spaltenname|Typindikator|Länge|Description|  
|-----------------|--------------------|------------|-----------------|  
|**Enumerationsname**|**DBTYPE_WSTR**||Der Name des Enumerators, der eine Wertemenge enthält.|  
|**EnumDescription**|**DBTYPE_WSTR**||Eine lokalisierbare Beschreibung des Enumerators. Kann **NULL**sein.|  
|**EnumType**|**DBTYPE_WSTR**||Der Datentyp der Enumerationswerte.|  
|**ElementName**|**DBTYPE_WSTR**||Der Name eines der Wertelemente im Enumeratorsatz.<br /><br /> Beispiel: **TDP**|  
|**ElementDescription**|**DBTYPE_WSTR**||(Optional) Eine lokalisierbare Beschreibung des Elements. Kann **NULL**sein.|  
|**ElementValue**|**DBTYPE_WSTR**||Der Wert des Elements. Kann **NULL**sein.<br /><br /> Beispiel: **01**|  
  
 Dieses Schemarowset ist nicht sortiert.  
  
## <a name="restriction-columns"></a>Einschränkungsspalten  
 Das **DISCOVER_ENUMERATORS** -Rowset kann auf die in der folgenden Tabelle aufgeführten Spalten eingeschränkt werden.  
  
|Spaltenname|Typindikator|Einschränkungsstatus|  
|-----------------|--------------------|-----------------------|  
|**Enumerationsname**|**DBTYPE_WSTR**||  
  
## <a name="see-also"></a>Siehe auch  
 [XML for Analysis – Schemarowsets](../../../analysis-services/schema-rowsets/xml/xml-for-analysis-schema-rowsets.md)  
  
  
