---
title: srv_alloc (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: extended-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- srv_alloc
apilocation:
- opends60.dll
apitype: DLLExport
dev_langs:
- C++
helpviewer_keywords:
- srv_alloc
ms.assetid: 91505c59-a273-452f-b71d-5e8205c21863
caps.latest.revision: 32
author: rothja
ms.author: jroth
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: ac3fbad92825ceab731e21bb4b345c6182278ac3
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="srvalloc-extended-stored-procedure-api"></a>srv_alloc (API für erweiterte gespeicherte Prozeduren)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Verwenden Sie stattdessen die CLR-Integration.  
  
 Weist dynamisch Arbeitsspeicher zu.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
void * srv_alloc ( DBINT  
size  
);  
```  
  
## <a name="arguments"></a>Argumente  
 *size*  
 Legt die Anzahl der zuzuweisenden Bytes fest.  
  
## <a name="returns"></a>Rückgabewert  
 Ein Zeiger auf den neu zugeordneten Speicherplatz. Wenn *size*-Bytes nicht zugeordnet werden können, wird ein NULL-Zeiger zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die **srv_alloc**-Funktion entspricht der **GlobalAlloc**-Funktion der [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-API. Normale C-Laufzeitspeicher-Verwaltungsfunktionen der Windows API können in einer Anwendung mit der API für erweiterte gespeicherte Prozeduren verwendet werden.  
  
> [!IMPORTANT]  
>  Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren. Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](http://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409http://msdn.microsoft.com/security/).  
  
  
