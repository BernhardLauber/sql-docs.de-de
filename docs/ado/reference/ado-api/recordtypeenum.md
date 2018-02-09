---
title: RecordTypeEnum | Microsoft Docs
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- RecordTypeEnum
helpviewer_keywords:
- RecordTypeEnum enumeration [ADO]
ms.assetid: f557e537-015d-4ba7-8a41-a6f00b366a91
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: bad37453f9bd6c4ca0f76c610c2f5f328f8f87ac
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="recordtypeenum"></a>RecordTypeEnum
Gibt den Typ des [Datensatz](../../../ado/reference/ado-api/record-object-ado.md) Objekt.  
  
|Konstante|Wert|Description|  
|--------------|-----------|-----------------|  
|**adSimpleRecord**|0|Gibt eine *einfache* Datensatz (enthält keine untergeordneten Knoten).|  
|**adCollectionRecord**|1|Gibt eine *Auflistung* Datensatz (enthält untergeordnete Knoten).|  
|**adRecordUnknown**|-1|Gibt an, dass der Typ dieses **Datensatz** ist unbekannt.|  
|**adStructDoc**|2|Gibt an, eine spezielle Art von *Auflistung* Datensatz, der COM-strukturierte Dokumente.|  
  
## <a name="adowfc-equivalent"></a>ADO/WFC-Entsprechung  
 Diese Konstanten keine ADO/WFC-Entsprechungen.  
  
## <a name="applies-to"></a>Gilt für  
 [RecordType-Eigenschaft (ADO)](../../../ado/reference/ado-api/recordtype-property-ado.md)
