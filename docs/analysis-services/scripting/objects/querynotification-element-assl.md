---
title: QueryNotification-Element (ASSL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: analysis-services
ms.service: 
ms.component: scripting
ms.reviewer: 
ms.suite: sql
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname: QueryNotification Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
helpviewer_keywords: QueryNotification element
ms.assetid: 0ee06730-81ff-4913-96e6-f39b6f181650
caps.latest.revision: "14"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: ca66700cbe7be59397679201160ee7031ed02330
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="querynotification-element-assl"></a>QueryNotification-Element (ASSL)
  Enthält Informationen für das [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md)-Element über die Abfrage, die ausgeführt werden muss, um zu bestimmen, ob eine Datenquelle geändert worden ist.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<QueryNotifications>  
   <QueryNotification>  
      <Query>...</Query>  
...</QueryNotification>  
</QueryNotifications>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Beschreibung|  
|--------------------|-----------------|  
|Datentyp und -länge|Keine|  
|Standardwert|Keine|  
|Kardinalität|1-n: Erforderliches Element, das mehr als einmal auftreten kann.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|[QueryNotifications](../../../analysis-services/scripting/collections/querynotifications-element-assl.md)|  
|Untergeordnete Elemente|[Abfrage](../../../analysis-services/scripting/properties/query-element-assl.md)|  
  
## <a name="remarks"></a>Hinweise  
 Das entsprechende Element im Objektmodell von Analysis Management Objects (AMO) ist <xref:Microsoft.AnalysisServices.QueryNotification>.  
  
## <a name="see-also"></a>Siehe auch  
 [ProactiveCachingQueryBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/proactivecachingquerybinding-data-type-assl.md)   
 [Objekte &#40; ASSL &#41;](../../../analysis-services/scripting/objects/objects-assl.md)  
  
  
