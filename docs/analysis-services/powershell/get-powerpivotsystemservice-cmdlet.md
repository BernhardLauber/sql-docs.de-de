---
title: Get-PowerPivotSystemService-Cmdlet | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: analysis-services
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 33231250-3880-4d75-936b-d70662a01855
caps.latest.revision: "9"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 7210a93db11f4cbabe4b8b574d1945f932c2f31c
ms.sourcegitcommit: f1a6944f95dd015d3774a25c14a919421b09151b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2017
---
# <a name="get-powerpivotsystemservice-cmdlet"></a>Get-PowerPivotSystemService-Cmdlet
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]Gibt die globalen Eigenschaften des der [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] System Service-Objekts in einer Farm. 

>[!NOTE] 
>In diesem Artikel möglicherweise veraltete Informationen und Beispiele enthalten. Verwenden Sie das Cmdlet "Get-Help", für die aktuelle.
  
 **Gilt für:** SharePoint 2010 und SharePoint 2013.  
  
## <a name="syntax"></a>Syntax  
  
```  
Get-PowerPivotSystemService [-Identity <PowerPivotMidTierServicePipeBind>] [<CommonParameters>]  
```  
  
## <a name="description"></a>Description  
 Das Get-PowerPivotSystemService-Cmdlet gibt die globalen Eigenschaften des [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] System Service-Objekts zurück. Es ist ein übergeordnetes Objekt pro Farm vorhanden, jede Farm kann jedoch über mehrere [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] -Systemdienstinstanzen verfügen, die auf den einzelnen Anwendungsservern in der Farm ausgeführt werden. Das übergeordnete Objekt zeigt Einstellungen auf Farmebene an, die nicht nach Instanz variieren. Wenn die Farm mehrere [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] für SharePoint-Installationen enthält, wird mit einer durch Trennzeichen getrennten Liste der Instanzen angegeben, wie viele [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] System Service-Instanzen in der Farm vorhanden sind.  
  
## <a name="parameters"></a>Parameter  
  
### <a name="-identity-powerpivotmidtierservicepipebind"></a>-Identity \<PowerPivotMidTierServicePipeBind >  
 Gibt das abzurufende übergeordnete Objekt an. Der Wert muss eine gültige GUID sein, die das Objekt in der Farm eindeutig identifiziert.  
  
|||  
|-|-|  
|Erforderlich?|false|  
|Position?|0|  
|Standardwert||  
|Pipelineeingabe akzeptieren?|true|  
|Platzhalterzeichen akzeptieren?|false|  
  
### <a name="commonparameters"></a>\<Allgemeine Parameter >  
 Dieses Cmdlet unterstützt die folgenden allgemeinen Parameter: Verbose, Debug, ErrorAction, ErrorVariable, WarningAction, WarningVariable, OutBuffer und OutVariable. Weitere Informationen finden Sie unter [about_CommonParameters](http://go.microsoft.com/fwlink/?linkID=227825).  
  
## <a name="inputs-and-outputs"></a>Eingaben und Ausgaben  
 Mit dem Eingabetyp wird festgelegt, welchen Typ von Objekten Sie über die Pipeline an das Cmdlet übergeben können. Der Rückgabetyp bezeichnet den Typ der vom Cmdlet zurückgegebenen Objekte.  
  
|||  
|-|-|  
|Eingaben|Keine.|  
|Ausgaben|Keine.|  
  
## <a name="example-1"></a>Beispiel 1  
  
```  
C:\PS>Get-PowerPivotSystemService  
```  
  
 In diesem Beispiel werden die globalen Eigenschaften des übergeordneten Objekts zurückgegeben. Dabei werden Eigenschaften angezeigt, die von allen [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] System Service-Instanzen in der Farm gemeinsam genutzt werden.  
  
  
