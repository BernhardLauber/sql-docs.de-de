---
title: FrameWindowVisible | Microsoft-Dokumentation
ms.custom: 
ms.date: 03/17/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9091d714-98bc-43ec-b8d1-9c892cb57f19
caps.latest.revision: 6
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: f09e83d79a913bb56042a5a48b832a940e0f9ea9
ms.lasthandoff: 04/11/2017

---
# <a name="sqltoolsvsnativehelpers---framewindowvisible"></a>SqlToolsVSNativeHelpers – FrameWindowVisible
  Eigenschaft, die angibt, ob ein angegebener Fensterrahmen sichtbar ist. Die Hilfsmethode wird in verwaltetem Code verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
BOOL WINAPI IsFrameWindowVisible(IVsWindowFrame* frame)  
{  
    if (NULL == frame)  
    {  
        return FALSE;  
    }  
  
    return S_OK == frame->IsVisible();  
}  
```  
  
#### <a name="parameters"></a>Parameter  
 *frame*  
  
 IVsWindowFrame*-Zeiger auf Visual Studio WindowFrame.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 Boolescher Wert, der angibt, ob der Fensterrahmen, der durch *frame* angegeben wird, sichtbar ist.  
  
## <a name="see-also"></a>Siehe auch  
 [SqlToolsVSNativeHelpers](../relational-databases/sqltoolsvsnativehelpers.md)  
  
  