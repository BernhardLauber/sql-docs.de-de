---
title: PropertyAttributesEnum | Microsoft Docs
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
- PropertyAttributesEnum
helpviewer_keywords:
- PropertyAttributesEnum enumeration [ADO]
ms.assetid: 96a01955-a6b4-4cbf-9c73-52bcd1e9fb25
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 57c232c27dc538cbbdc8203855a27ee2ff56b7f8
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="propertyattributesenum"></a>PropertyAttributesEnum
Gibt die Attribute einer [Eigenschaft](../../../ado/reference/ado-api/property-object-ado.md) Objekt.  
  
|Konstante|Wert|Description|  
|--------------|-----------|-----------------|  
|**adPropNotSupported**|0|Gibt an, dass die Eigenschaft nicht vom Anbieter unterstützt wird.|  
|**adPropRequired**|1|Gibt an, dass der Benutzer einen Wert für diese Eigenschaft angeben muss, vor der Initialisierung der Datenquelle.|  
|**adPropOptional**|2|Gibt an, dass der Benutzer nicht auf einen Wert für diese Eigenschaft angeben, vor der Initialisierung der Datenquelle.|  
|**adPropRead**|512|Gibt an, dass der Benutzer die Eigenschaft gelesen werden kann.|  
|**adPropWrite**|1024|Gibt an, dass der Benutzer die Eigenschaft festlegen kann.|  
  
## <a name="adowfc-equivalent"></a>ADO/WFC-Entsprechung  
 Paket: **com.ms.wfc.data**  
  
|Konstante|  
|--------------|  
|AdoEnums.PropertyAttributes.NOTSUPPORTED|  
|AdoEnums.PropertyAttributes.REQUIRED|  
|AdoEnums.PropertyAttributes.OPTIONAL|  
|AdoEnums.PropertyAttributes.READ|  
|AdoEnums.PropertyAttributes.WRITE|  
  
## <a name="applies-to"></a>Gilt für  
 [Attributes-Eigenschaft (ADO)](../../../ado/reference/ado-api/attributes-property-ado.md)
