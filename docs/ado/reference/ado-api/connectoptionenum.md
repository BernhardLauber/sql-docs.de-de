---
title: ConnectOptionEnum | Microsoft Docs
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology: drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords: ConnectOptionEnum
helpviewer_keywords: ConnectOptionEnum enumeration [ADO]
ms.assetid: bff07eeb-dee3-4e4e-9b2d-d56061ea744d
caps.latest.revision: "11"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 78293f465e1b8a8bfb0195c048bc0e0145c17abc
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="connectoptionenum"></a>ConnectOptionEnum
Gibt an, ob die [öffnen](../../../ado/reference/ado-api/open-method-ado-connection.md) Methode von einer [Verbindung](../../../ado/reference/ado-api/connection-object-ado.md) Objekt sollte nach dem Herstellen der Verbindung (synchron) oder vor dem zurückgeben (asynchron).  
  
|Konstante|value|Description|  
|--------------|-----------|-----------------|  
|**adAsyncConnect**|16|Öffnet die Verbindung asynchron aus. Die [ConnectComplete](../../../ado/reference/ado-api/connectcomplete-and-disconnect-events-ado.md) Ereignis kann verwendet werden, um zu bestimmen, wann die Verbindung verfügbar ist.|  
|**adConnectUnspecified**|-1|Standard. Öffnet die Verbindung synchron an.|  
  
## <a name="adowfc-equivalent"></a>ADO/WFC-Entsprechung  
 Paket: **com.ms.wfc.data**  
  
|Konstante|  
|--------------|  
|AdoEnums.ConnectOption.ASYNCCONNECT|  
|AdoEnums.ConnectOption.CONNECTUNSPECIFIED|  
  
## <a name="applies-to"></a>Gilt für  
 [Open-Methode (ADO Connection)](../../../ado/reference/ado-api/open-method-ado-connection.md)
