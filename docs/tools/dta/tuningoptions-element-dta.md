---
title: TuningOptions-Element (DTA) | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: sql-non-specified
ms.service: 
ms.component: dta
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: XML
helpviewer_keywords: TuningOptions element
ms.assetid: 58a22ba1-8e03-411f-bd46-85e4540f217a
caps.latest.revision: "12"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 6a6c2e3ec727651f0470394e61241eeeffdc01e1
ms.sourcegitcommit: b2d8a2d95ffbb6f2f98692d7760cc5523151f99d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2017
---
# <a name="tuningoptions-element-dta"></a>TuningOptions-Element (DTA)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]Enthält die Optimierungsoptionen für eine bestimmte optimierungssitzung.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
<DTAInput>  
    <Server>  
...code removed...  
    <Workload>...</Workload>  
    <TuningOptions>...</TuningOptions>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Beschreibung|  
|--------------------|-----------------|  
|**Datentyp und -länge**|Keine.|  
|**Standardwert**|Keine.|  
|**Vorkommen**|Optional. Kann bei Verwendung nur einmalig pro **DTAInput** -Element verwendet werden.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Elemente|  
|------------------|--------------|  
|**Übergeordnetes Element**|[DTAInput-Element &#40;DTA&#41;](../../tools/dta/dtainput-element-dta.md)|  
|**Untergeordnete Elemente**|**ReportSet** -Element. Weitere Informationen finden Sie im [XML-Schema des Datenbankoptimierungsratgebers](http://go.microsoft.com/fwlink/?linkid=43100).<br /><br /> **TuningLogTable** -Element. Weitere Informationen finden Sie im [XML-Schema des Datenbankoptimierungsratgebers](http://go.microsoft.com/fwlink/?linkid=43100).<br /><br /> **NumberOfEvents** -Element. Weitere Informationen finden Sie im [XML-Schema des Datenbankoptimierungsratgebers](http://go.microsoft.com/fwlink/?linkid=43100).<br /><br /> [TuningTimeInMin-Element &#40;DTA&#41;](../../tools/dta/tuningtimeinmin-element-dta.md)<br /><br /> [StorageBoundInMB-Element &#40;DTA&#41;](../../tools/dta/storageboundinmb-element-dta.md)<br /><br /> **MaxKeyColumnsInIndex** -Element. Weitere Informationen finden Sie im [XML-Schema des Datenbankoptimierungsratgebers](http://go.microsoft.com/fwlink/?linkid=43100).<br /><br /> **MaxColumnsInIndex** -Element. Weitere Informationen finden Sie im [XML-Schema des Datenbankoptimierungsratgebers](http://go.microsoft.com/fwlink/?linkid=43100).<br /><br /> **MinPercentageImprovement** -Element. Weitere Informationen finden Sie im [XML-Schema des Datenbankoptimierungsratgebers](http://go.microsoft.com/fwlink/?linkid=43100).<br /><br /> [TestServer-Element &#40;DTA&#41;](../../tools/dta/testserver-element-dta.md)<br /><br /> [FeatureSet-Element &#40;DTA&#41;](../../tools/dta/featureset-element-dta.md)<br /><br /> [Partitioning-Element &#40;DTA&#41;](../../tools/dta/partitioning-element-dta.md)<br /><br /> [DropOnlyMode-Element &#40;DTA&#41;](../../tools/dta/droponlymode-element-dta.md)<br /><br /> [KeepExisting-Element &#40;DTA&#41;](../../tools/dta/keepexisting-element-dta.md)<br /><br /> [OnlineIndexOperation-Element &#40;DTA&#41;](../../tools/dta/onlineindexoperation-element-dta.md)<br /><br /> [DatabaseToConnect-Element &#40;DTA&#41;](../../tools/dta/databasetoconnect-element-dta.md)<br /><br /> **IgnoreConstantsInWorkload** -Element. Weitere Informationen finden Sie im [XML-Schema des Datenbankoptimierungsratgebers](http://go.microsoft.com/fwlink/?linkid=43100).<br /><br /> **RetainShellDB** -Element. Weitere Informationen finden Sie im [XML-Schema des Datenbankoptimierungsratgebers](http://go.microsoft.com/fwlink/?linkid=43100).|  
  
## <a name="example"></a>Beispiel  
 Beispiele für das **TuningOptions**-Element finden Sie unter [Beispiele für XML-Eingabedateien &#40;DTA&#41;](../../tools/dta/xml-input-file-samples-dta.md).  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;](../../tools/dta/xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
