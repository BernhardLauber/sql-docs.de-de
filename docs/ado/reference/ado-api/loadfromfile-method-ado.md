---
title: LoadFromFile-Methode (ADO) | Microsoft Docs
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
- _Stream::raw_LoadFromFile
helpviewer_keywords:
- LoadFromFile method [ADO]
ms.assetid: b18d8d38-7354-4a94-b637-6ac035faa433
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 071ba2d6a2aa5af96af07274455a7495a9650dea
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="loadfromfile-method-ado"></a>LoadFromFile-Methode (ADO)
Lädt den Inhalt einer vorhandenen Datei in eine [Stream](../../../ado/reference/ado-api/stream-object-ado.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
Stream.LoadFromFileFileName  
```  
  
#### <a name="parameters"></a>Parameter  
 *FileName*  
 Ein **Zeichenfolge** -Wert, der den Namen einer Datei geladen werden enthält die **Stream**. *FileName* können alle gültigen Pfad und Namen im UNC-Format enthalten. Wenn die angegebene Datei nicht vorhanden ist, tritt ein Laufzeitfehler auf.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode kann verwendet werden, beim Laden des Inhalts einer lokalen Datei in eine **Stream** Objekt. Dies kann verwendet werden, um den Inhalt einer lokalen Datei auf einen Server hochladen.  
  
 Die **Stream** Objekt muss geöffnet sein, bereits vor dem Aufruf **LoadFromFile**. Diese Methode ändert nicht die Bindung der **Stream** Objekt; wird weiterhin auf das Objekt, das die URL gebunden werden oder **Datensatz** mit dem der **Stream** ursprünglich war geöffnet.  
  
 **LoadFromFile** überschreibt den aktuellen Inhalt der **Stream** Objekt mit Daten aus der Datei gelesen. Alle vorhandenen Bytes in der **Stream** werden durch den Inhalt der Datei überschrieben. Alle zuvor vorhandenen und verbleibenden Bytes, die nach der [EOS](../../../ado/reference/ado-api/eos-property.md) erstellt, indem **LoadFromFile**, werden abgeschnitten.  
  
 Nach einem Aufruf von **LoadFromFile**, die aktuelle Position festgelegt ist, an den Anfang der **Stream** ([Position](../../../ado/reference/ado-api/position-property-ado.md) ist 0).  
  
 Da 2 Bytes auf den Anfang des Datenstroms für die Codierung hinzugefügt werden kann, kann die Größe des Datenstroms nicht genau der Größe der Datei entsprechen, an dem es geladen wurde.  
  
## <a name="applies-to"></a>Gilt für  
 [Stream-Objekt (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)
