---
title: State-Eigenschaft (SqlService-Klasse) | Microsoft Docs
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: wmi
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- State Property (SqlService Class)
apilocation:
- sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords:
- State property
ms.assetid: 9e09f419-947c-4d4b-9a49-2d3396c847cd
caps.latest.revision: 
author: JennieHubbard
ms.author: jhubbard
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 3ba996af300626a03b61ea367791b27fbf1134e9
ms.sourcegitcommit: 37f0b59e648251be673389fa486b0a984ce22c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2018
---
# <a name="state-property-sqlservice-class"></a>State-Eigenschaft (SqlService-Klasse)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]
Ruft den aktuellen Zustand des Diensts ab oder legt diesen fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
object.State [= value]  
```  
  
## <a name="parts"></a>Bestandteile  
 *Objekt*  
 Ein [SqlService-Klassenobjekt](../../../relational-databases/wmi-provider-configuration-classes/sqlservice-class/sqlservice-class.md) , das den Dienst darstellt.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 Ein uint32-Wert, der den Zustand des Diensts angibt.  
  
 Folgende Werte sind möglich:  
  
 1  
 Beendet. Der -Dienst wurde beendet.  
  
 2  
 Start steht aus. Der Dienst wartet darauf, gestartet zu werden.  
  
 3  
 Beenden steht aus. Der Dienst wartet darauf, beendet zu werden.  
  
 4  
 Wird ausgeführt. Der Dienst wird ausgeführt.  
  
 5  
 Fortsetzung steht aus. Der Dienst wartet darauf, fortgesetzt zu werden.  
  
 6  
 Anhalten steht aus. Der Dienst wartet darauf, angehalten zu werden.  
  
 7  
 Angehalten. Der Dienst wurde angehalten.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Starten und Beenden von Diensten](http://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
