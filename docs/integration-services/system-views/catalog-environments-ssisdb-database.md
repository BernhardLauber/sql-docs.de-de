---
title: catalog.environments (SSISDB-Datenbank) | Microsoft-Dokumentation
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: system-views
ms.reviewer: 
ms.suite: sql
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 7014c0e3-65dc-4a46-842e-4decf3737748
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: b76a46e4946bcdcfb9431df9799de6a1aeff6030
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="catalogenvironments-ssisdb-database"></a>catalog.environments (SSISDB-Datenbank)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Zeigt die Umgebungsdetails für alle Umgebungen im [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Katalog an. Umgebungen enthalten Variablen, auf die von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Projekten verwiesen werden kann.  
  
|Spaltenname|Datentyp|Description|  
|-----------------|---------------|-----------------|  
|environment_id|**bigint**|Der eindeutige Bezeichner (ID) der Umgebung.|  
|NAME|**sysname**|Der Name der Umgebung.|  
|folder_id|**bigint**|Die eindeutige ID des Ordners, in der sich die Umgebung befindet.|  
|description|**nvarchar(1024)**|Die Beschreibung der Umgebung. Dieser Wert ist optional.|  
|created_by_sid|**varbinary(85)**|Die Sicherheits-ID (SID) des Benutzers, der die Umgebung erstellt hat|  
|created_by_name|**nvarchar(128)**|Der Name des Benutzers, der die Umgebung erstellt hat.|  
|created_time|**datetimeoffset**|Datum und Uhrzeit der Umgebungserstellung.|  
  
## <a name="remarks"></a>Remarks  
 In dieser Sicht wird eine Zeile für jede Umgebung im Katalog angezeigt. Umgebungsnamen sind nur in Bezug auf den Ordner eindeutig, in dem sie sich befinden. Beispielsweise kann eine Umgebung mit dem Namen `E1` in mehreren Ordnern im Katalog vorhanden sein, jedoch kann jeder Ordner nur eine Umgebung mit dem Namen `E1`enthalten.  
  
## <a name="permissions"></a>Berechtigungen  
 Diese Sicht erfordert eine der folgenden Berechtigungen:  
  
-   READ-Berechtigung für die Umgebung  
  
-   Mitgliedschaft in der Datenbankrolle **ssis_admin**  
  
-   Mitgliedschaft in der Serverrolle **sysadmin**  
  
> [!NOTE]  
>  Sicherheit auf Zeilenebene wird erzwungen. Es werden nur Zeilen angezeigt, zu deren Anzeige Sie berechtigt sind.  
  
  
