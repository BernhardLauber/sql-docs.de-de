---
title: Property-Objekt (ADOX) | Microsoft Docs
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
helpviewer_keywords:
- Property object [ADOX]
ms.assetid: 6a56def6-dbe6-4ccc-a491-8d076889f019
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: c9d13366eb3554738fbd50da2ed09db8bceb6f5d
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="property-object-adox"></a>Property-Objekt (ADOX)
Stellt ein Merkmal eines ADOX-Objekts dar.  
  
## <a name="remarks"></a>Hinweise  
 ADOX-Objekte verfügen über zwei Arten von Eigenschaften: integrierte und dynamische.  
  
 Integrierte Eigenschaften sind die Eigenschaften, die für jedes neue Objekt, mit der Syntax MyObject.Property sofort verfügbar. Sie erscheinen nicht als Property-Objekte in einem Objekt ["Properties"-Sammlung](../../../ado/reference/ado-api/properties-collection-ado.md), sodass Sie ihre Werte können jedoch ändern, können Sie ihre Merkmale nicht ändern.  
  
 Dynamische Eigenschaften werden von der zugrunde liegende Datenanbieter definiert und in der Properties-Auflistung für die entsprechenden ADOX-Objekt angezeigt.  Dynamische Eigenschaften können nur über die Auflistung, die mit der Syntax MyObject.Properties(0) oder MyObject.Properties("Name") verwiesen werden.  
  
 Beide Arten der Eigenschaft kann nicht gelöscht werden.  
  
 Ein dynamisches Objekt verfügt über vier integrierte Eigenschaften einen eigenen:  
  
 Die [Namen](../../../ado/reference/ado-api/name-property-ado.md) Eigenschaft ist eine Zeichenfolge, die die Eigenschaft identifiziert.  
  
 Die [Typ](../../../ado/reference/ado-api/type-property-ado.md) Eigenschaft ist eine ganze Zahl, die den Datentyp der Eigenschaft angibt.  
  
 Die [Wert](../../../ado/reference/ado-api/value-property-ado.md) Eigenschaft ist eine Variante, die die Einstellung der Eigenschaft enthält. Wert ist die Standardeigenschaft für ein Eigenschaftenobjekt.  
  
 Die [Attribute](../../../ado/reference/ado-api/attributes-property-ado.md) Eigenschaft ist ein long-Wert, der die Eigenschaften, die spezifisch für den Datenanbieter angibt.  
  
 Dieser Abschnitt enthält das folgende Thema.  
  
-   [ADOX-Objekt – Eigenschaften, Methoden und Ereignisse](../../../ado/reference/adox-api/adox-property-object-properties-methods-and-events.md)
