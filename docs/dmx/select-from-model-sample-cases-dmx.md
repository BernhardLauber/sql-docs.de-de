---
title: SELECT FROM &lt;Modell&gt;. SAMPLE_CASES (DMX) | Microsoft Docs
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SAMPLE_CASES
- SELECT
- FROM
dev_langs:
- DMX
helpviewer_keywords:
- SELECT FROM <model>.SAMPLE_CASES statement
- mining models [Analysis Services], sample cases
- sample cases [DMX]
- training mining models
ms.assetid: e7a34b9b-3562-4503-bfa7-dd9b12db480a
caps.latest.revision: 39
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 3c1e90c2d4fd6b7dab565550bc4b08a4a33192ee
ms.contentlocale: de-de
ms.lasthandoff: 08/02/2017

---
# <a name="select-from-ltmodelgtsamplecases-dmx"></a>SELECT FROM &lt;Modell&gt;. SAMPLE_CASES (DMX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Gibt Beispielfälle zurück, die repräsentativ für die Fälle sind, die zum Trainieren des Data Mining-Modells verwendet werden.  
  
 Damit Sie diese Anweisung verwenden können, müssen Sie Drillthrough aktivieren, wenn Sie das Miningmodell erstellen. Weitere Informationen zum Aktivieren von Drillthrough finden Sie unter [CREATE MINING MODEL &#40; DMX &#41;](../dmx/create-mining-model-dmx.md), [SELECT INTO &#40; DMX &#41;](../dmx/select-into-dmx.md), und [ALTER MINING STRUCTURE &#40; DMX &#41;](../dmx/alter-mining-structure-dmx.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
SELECT [FLATTENED] [TOP <n>] <expression list> FROM <model>.SAMPLE_CASES  
[WHERE <condition list>] ORDER BY <expression> [DESC|ASC]]  
```  
  
## <a name="arguments"></a>Argumente  
 *n*  
 Optional. Eine ganze Zahl, die angibt, wie viele Zeilen zurückgegeben werden sollen.  
  
 *Liste der Ausdrücke*  
 Eine durch Trennzeichen getrennte Liste mit Bezeichnern verbundener Spalten.  
  
 *model*  
 Ein Modellbezeichner.  
  
 *Liste der Bedingungen*  
 Optional. Bedingungen, die die Werte einschränken, die für die Spaltenliste zurückgegeben werden.  
  
 *expression*  
 Optional. Ein Ausdruck, der einen Skalarwert zurückgibt.  
  
## <a name="remarks"></a>Hinweise  
 Beispielfälle können generiert werden und sind in den Trainingsdaten möglicherweise nicht tatsächlich vorhanden. Der zurückgegebene Fall ist repräsentativ für den angegebenen Inhaltsknoten.  
  
 Obwohl die [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering-Algorithmus ist der einzige [!INCLUDE[msCoName](../includes/msconame-md.md)] Algorithmus, der unterstützt die Verwendung von SELECT FROM \<Modell >. SAMPLE_CASES, möglicherweise drittanbieteralgorithmen ebenfalls unterstützt.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel werden Beispielfälle zurückgegeben, mit denen das Target Mail-Miningmodell trainiert wird. Mithilfe der [IsInNode &#40; DMX &#41;](../dmx/isinnode-dmx.md) -Funktion in der **, in denen** -Klausel nur Fälle zurückgegeben, die den Knoten '000000003' zugeordnet sind. Die Knotenzeichenfolge ist in der NODE_UNIQUE_NAME-Spalte des Schemarowsets zu finden.  
  
```  
Select * from [Sequence Clustering].SAMPLE_Cases  
WHERE IsInNode('000000003')  
```  
  
## <a name="see-also"></a>Siehe auch  
 [SELECT &#40; DMX &#41;](../dmx/select-dmx.md)   
 [Datamining-Erweiterungen &#40; DMX &#41; Datendefinitionsanweisungen](../dmx/dmx-statements-data-definition.md)   
 [Datamining-Erweiterungen &#40; DMX &#41; Datenbearbeitungsanweisungen](../dmx/dmx-statements-data-manipulation.md)   
 [Datamining-Erweiterungen &#40; DMX &#41; -Anweisungsreferenz](../dmx/data-mining-extensions-dmx-statements.md)  
  
  
