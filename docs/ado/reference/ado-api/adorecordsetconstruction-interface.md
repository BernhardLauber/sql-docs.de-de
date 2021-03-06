---
title: ADORecordsetConstruction Schnittstelle | Microsoft Docs
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
- ADORecordsetConstruction
helpviewer_keywords:
- ADORecordsetConstruction interface [ADO]
ms.assetid: 08386eba-f1f7-4879-8ffd-8733930ecb2f
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: be4c36c5bd69fe6657b57d74e8808259fe602db0
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="adorecordsetconstruction-interface"></a>ADORecordsetConstruction-Schnittstelle
Die **ADORecordsetConstruction** Schnittstelle wird verwendet, um eine ADO erstellen **Recordset** Objekt aus einer OLE DB- **Rowset** Objekt in einer C-/C++-Anwendung.  
  
 Diese Schnittstelle unterstützt die folgenden Eigenschaften:  
  
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|[Chapter](../../../ado/reference/ado-api/chapter-property-ado.md)|Lese-/Schreibzugriff.<br />Ruft ab oder legt ihn fest, einen OLE DB- **Kapitel** Objekt vom bzw. auf diesen ADO **Recordset** Objekt.|  
|[RowPosition](../../../ado/reference/ado-api/rowposition-property-ado.md)|Lese-/Schreibzugriff.<br />Ruft ab oder legt ihn fest, einen OLE DB- **RowPosition** Objekt vom bzw. auf diesen ADO **Recordset** Objekt.|  
|[Rowset](../../../ado/reference/ado-api/rowset-property-ado.md)|Lese-/Schreibzugriff.<br />Ruft ab oder legt ihn fest, einen OLE DB- **Rowset** Objekt vom bzw. auf diesen ADO **Recordset** Objekt.|  
  
## <a name="methods"></a>Methoden  
 Keine.  
  
## <a name="events"></a>Ereignisse  
 Keine.  
  
## <a name="remarks"></a>Hinweise  
 Erhält einen OLE DB- **Rowset** Objekt (`pRowset`), die zur Erstellung eines ADO **Recordset** Objekt (`adoRs`) läuft auf die folgenden drei grundlegende Vorgänge:  
  
1.  Erstellen Sie ein ADO **Recordset** Objekt:  
  
    ```  
    Recordset20Ptr adoRs;  
    adoRs.CreateInstance(__uuidof(Recordset));  
    ```  
  
2.  Abfrage der **IADORecordsetConstruction** -Schnittstelle für die **Recordset** Objekt:  
  
    ```  
    adoRecordsetConstructionPtr adoRsConstruct=NULL;  
    adoRs->QueryInterface(__uuidof(ADORecordsetConstruction),  
                         (void**)&adoRsConstruct);  
    ```  
  
3.  Rufen Sie die `IADORecordsetConstruction::put_Rowset` Property-Methode legen Sie den OLE DB- `Rowset` das ADO-Objekt `Recordset` Objekt:  
  
    ```  
    IUnknown *pUnk=NULL;  
    pRowset->QueryInterface(IID_IUnknown, (void**)&pUnk);  
    adoRsConstruct->put_Rowset(pUnk);  
    ```  
  
 Die resultierenden `adoRs` Objekt stellt nun das ADO **Recordset** Objekte aus der OLE DB- **Rowset** Objekt.  
  
 Sie können auch eine ADO erstellen **Recordset** Objekt aus einer OLE DB- **Kapitel** oder **RowPosition** Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Version:** ADO 2.0 und höher  
  
 **Bibliothek:** "MSADO15.dll"  
  
 **UUID:** 00000283-0000-0010-8000-00AA006D2EA4  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset-Objekt (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)   
 [Rowset-Eigenschaft (ADO)](../../../ado/reference/ado-api/rowset-property-ado.md)
