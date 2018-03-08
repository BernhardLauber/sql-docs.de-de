---
title: GetChildren-Methode (ADO) | Microsoft Docs
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
- _Record::raw_GetChildren
- _Record::GetChildren
helpviewer_keywords:
- GetChildren method [ADO]
ms.assetid: b3f09bac-4f66-49f6-aa5a-6fbb4fb28338
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 1588a5a63acaa8876f753d765852926cc749c240
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="getchildren-method-ado"></a>GetChildren-Methode (ADO)
Gibt eine [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) , deren Zeilen darstellen, die untergeordneten Elemente einer Auflistung [Datensatz](../../../ado/reference/ado-api/record-object-ado.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
Set recordset = record.GetChildren  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein **Recordset** für die jede Zeile steht für ein untergeordnetes Element des aktuellen Objekts **Datensatz** Objekt. Angenommen, die untergeordneten Elemente des eine **Datensatz** stellt ein Verzeichnis die Dateien und Unterverzeichnisse innerhalb des übergeordneten Verzeichnisses enthalten wäre.  
  
## <a name="remarks"></a>Hinweise  
 Der Anbieter bestimmt, welche Spalten im zurückgegebenen vorhanden **Recordset**. Ein Anbieter gibt z. B. immer eine Ressource **Recordset**.  
  
## <a name="applies-to"></a>Gilt für  
  
|||  
|-|-|  
|[Record-Objekt (ADO)](../../../ado/reference/ado-api/record-object-ado.md)|[Recordset-Objekt (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)|
