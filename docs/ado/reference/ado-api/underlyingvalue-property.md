---
title: OriginalValue Eigenschaft | Microsoft Docs
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
- Field20::GetUnderlyingValue
- Field20::get_UnderlyingValue
- Field20::UnderlyingValue
helpviewer_keywords:
- UnderlyingValue property
ms.assetid: 00a0c8b8-8b63-433f-95b8-020ab05874a0
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 739852d4cbfa4aaf2cf45a59b81b60e23617597f
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="underlyingvalue-property"></a>OriginalValue-Eigenschaft
Gibt den aktuellen Wert einer [Feld](../../../ado/reference/ado-api/field-object.md) Objekt in der Datenbank.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt eine **Variant** -Wert, der der Wert gibt die **Feld**.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der **OriginalValue** Eigenschaft, um den aktuellen Feldwert aus der Datenbank zurückzugeben. Der Wert des Felds in der **OriginalValue** Eigenschaft ist der Wert, der für die Transaktion sichtbar ist, und ggf. das Ergebnis eines neuesten Updates von einer anderen Transaktion. Dies unterscheidet sich möglicherweise von den [OriginalValue](../../../ado/reference/ado-api/originalvalue-property-ado.md) -Eigenschaft, die den Wert angibt, die ursprünglich an zurückgegeben wurde die [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md).  
  
 Dies ist vergleichbar mit dem mithilfe der [Resync](../../../ado/reference/ado-api/resync-method.md) -Methode, aber die **OriginalValue** Eigenschaft gibt nur den Wert für ein bestimmtes Feld aus dem aktuellen Datensatz. Dies entspricht dem-Wert, der [Resync](../../../ado/reference/ado-api/resync-method.md) Methode verwendet zum Ersetzen der [Wert](../../../ado/reference/ado-api/value-property-ado.md) Eigenschaft.  
  
 Bei Verwendung dieser Eigenschaft mit dem **OriginalValue** -Eigenschaft, können Sie Konflikte von BatchUpdates beheben.  
  
## <a name="record"></a>Aufzeichnung (Record)  
 Für [Datensatz](../../../ado/reference/ado-api/record-object-ado.md) Objekte diese Eigenschaft ist für Felder hinzugefügt, bevor Sie leere, [Update](../../../ado/reference/ado-api/update-method.md) aufgerufen wird.  
  
## <a name="applies-to"></a>Gilt für  
 [Field-Objekt](../../../ado/reference/ado-api/field-object.md)  
  
## <a name="see-also"></a>Siehe auch  
 [OriginalValue und OriginalValue Eigenschaften Beispiel (VB)](../../../ado/reference/ado-api/originalvalue-and-underlyingvalue-properties-example-vb.md)   
 [OriginalValue und OriginalValue Eigenschaften (VC++-Beispiel)](../../../ado/reference/ado-api/originalvalue-and-underlyingvalue-properties-example-vc.md)   
 [OriginalValue-Eigenschaft (ADO)](../../../ado/reference/ado-api/originalvalue-property-ado.md)   
 [Resync-Methode](../../../ado/reference/ado-api/resync-method.md)
