---
title: ParentCatalog-Eigenschaft (ADOX) | Microsoft Docs
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
- _User::get_ParentCatalog
- _Column::ParentCatalog
- _Table::put_ParentCatalog
- _Group::put_ParentCatalog
- _Column::get_ParentCatalog
- _Table::PutParentCatalog
- _Group::putref_ParentCatalog
- _Group::ParentCatalog
- _Column::PutParentCatalog
- _Column::put_ParentCatalog
- _Group::get_ParentCatalog
- _User::put_ParentCatalog
- _User::putref_ParentCatalog
- _Table::get_ParentCatalog
- _Group::PutParentCatalog
- _Table::ParentCatalog
- _Column::GetParentCatalog
- _Table::PutRefParentCatalog
- _User::GetParentCatalog
- _Table::GetParentCatalog
- _Table::putref_ParentCatalog
- _User::PutParentCatalog
- _User::ParentCatalog
- _User::PutRefParentCatalog
- _Group::GetParentCatalog
- _Group::PutRefParentCatalog
helpviewer_keywords:
- ParentCatalog property [ADOX]
ms.assetid: a0bb2ed8-d4cb-4f92-8de7-769bbe0e6273
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: c255beddbc240f30f51642a0e8fe4fd785cf88bb
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="parentcatalog-property-adox"></a>ParentCatalog-Eigenschaft (ADOX)
Gibt den übergeordneten Katalog eines Objekts Tabellen, Benutzer oder Spalten zum Zugriff auf die anbieterspezifischen Eigenschaften bereitstellen.  
  
## <a name="settings-and-return-values"></a>Einstellungen und Rückgabewerte  
 Legt fest, und gibt eine [Katalog](../../../ado/reference/adox-api/catalog-object-adox.md) Objekt. Festlegen von **ParentCatalog** auf ein offenes **Katalog** ermöglicht den Zugriff auf die anbieterspezifischen Eigenschaften vor dem Anfügen einer Tabelle oder Spalte um eine **Katalog** Auflistung.  
  
## <a name="remarks"></a>Hinweise  
 Einige Datenanbieter ermöglicht-anbieterspezifische Datenquelleneigenschaft-Werte nur zum Erstellungszeitpunkt geschrieben werden: d. h. wenn eine Tabelle oder Spalte um angefügt wird seine **Katalog** Auflistung. Zugriff auf diese Eigenschaften vor dem Anfügen der Objekte auf einer **Katalog**, geben Sie die **Katalog** in der **ParentCatalog** Eigenschaft erste.  
  
 Ein Fehler auftritt, wenn die Tabelle oder Spalte, auf einen anderen angefügt wird **Katalog** als die **ParentCatalog**.  
  
## <a name="applies-to"></a>Gilt für  
  
|||  
|-|-|  
|[Column-Objekt (ADOX)](../../../ado/reference/adox-api/column-object-adox.md)|[Table-Objekt (ADOX)](../../../ado/reference/adox-api/table-object-adox.md)|  
|[User-Objekt (ADOX)](../../../ado/reference/adox-api/user-object-adox.md)||  
  
## <a name="see-also"></a>Siehe auch  
 [ParentCatalog-Eigenschaft – Beispiel (VB)](../../../ado/reference/adox-api/parentcatalog-property-example-vb.md)
