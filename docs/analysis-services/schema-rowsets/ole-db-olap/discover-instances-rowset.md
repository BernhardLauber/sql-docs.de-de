---
title: DISCOVER_INSTANCES-Rowset | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- DISCOVER_INSTANCES
apitype: NA
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- DISCOVER_INSTANCES rowset
ms.assetid: e0842e63-089d-468d-869f-634da343d9fb
caps.latest.revision: 30
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 39705d4efdcec8ed190bc58e2ac1888b3aeef7fe
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2018
---
# <a name="discoverinstances-rowset"></a>DISCOVER_INSTANCES-Rowset
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Beschreibt die Instanzen auf dem Server.  
  
## <a name="rowset-columns"></a>Rowsetspalten  
 Das **DISCOVER_INSTANCES** -Rowset enthält die folgenden Spalten.  
  
|Spaltenname|Typindikator|Länge|Description|  
|-----------------|--------------------|------------|-----------------|  
|**INSTANZNAME**|**DBTYPE_WSTR**||Der Name der Instanz.|  
|**INSTANCE_PORT_NUMBER**|**DBTYPE_I4**||Die Portnummer, die die Instanz überwacht.|  
|**INSTANCE_STATE**|**DBTYPE_I4**||Der Status der Serverinstanz.<br /><br /> **Schritte**<br /><br /> **Beendet**<br /><br /> **Starten**<br /><br /> **Beenden**<br /><br /> **Angehalten**|  
  
 Dieses Schemarowset ist nicht sortiert.  
  
## <a name="restriction-columns"></a>Einschränkungsspalten  
 Das **DISCOVER_INSTANCES** -Rowset kann auf die in der folgenden Tabelle aufgeführten Spalten eingeschränkt werden.  
  
|Spaltenname|Typindikator|Einschränkungsstatus|  
|-----------------|--------------------|-----------------------|  
|**INSTANZNAME**|**DBTYPE_WSTR**|Optional.|  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB für OLAP-Schemarowsets](../../../analysis-services/schema-rowsets/ole-db-olap/ole-db-for-olap-schema-rowsets.md)  
  
  
