---
title: Sp_helpdbfixedrole (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_helpdbfixedrole
- sp_helpdbfixedrole_TSQL
dev_langs: TSQL
helpviewer_keywords: sp_helpdbfixedrole
ms.assetid: ad87e9a0-b901-4e37-9950-aa517d680fc3
caps.latest.revision: "24"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: f99ac579405fa4a02f2cfb560136d01f58a9cac6
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2017
---
# <a name="sphelpdbfixedrole-transact-sql"></a>sp_helpdbfixedrole (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Gibt eine Liste der festen Datenbankrollen zurück.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
sp_helpdbfixedrole [ [ @rolename = ] 'role' ]   
```  
  
## <a name="arguments"></a>Argumente  
 [  **@rolename =** ] **"***Rolle***"**  
 Der Name einer festen Datenbankrolle. *role* ist vom Datentyp **sysname**und hat den Standardwert NULL. Wenn *Rolle* wird angegeben, werden nur Informationen zu dieser Rolle zurückgegeben; andernfalls wird eine Liste und Beschreibung aller festen Datenbankrollen zurückgegeben.  
  
## <a name="return-code-values"></a>Rückgabecodewerte  
 0 (Erfolg) oder 1 (Fehler)  
  
## <a name="result-sets"></a>Resultsets  
  
|Spaltenname|Datentyp|Description|  
|-----------------|---------------|-----------------|  
|**DbFixedRole**|**sysname**|Name der festen Datenbankrolle.|  
|**Description**|**nvarchar(70)**|Beschreibung des **DbFixedRole.**|  
  
## <a name="remarks"></a>Hinweise  
 Feste Datenbankrollen werden, wie in der folgenden Tabelle dargestellt, auf Datenbankebene definiert und besitzen Berechtigungen, um spezifische Verwaltungsaktivitäten auf Datenbankebene auszuführen. Feste Datenbankrollen können nicht hinzugefügt oder entfernt werden. Die für eine feste Datenbankrolle erteilten Berechtigungen können nicht geändert werden.  
  
|Feste Datenbankrolle|Description|  
|-------------------------|-----------------|  
|**db_owner**|Datenbankbesitzer|  
|**db_accessadmin**|Administratoren für den Datenbankzugriff|  
|**db_securityadmin**|Administratoren für die Datenbanksicherheit|  
|**db_ddladmin**|Datenbank-DDL-Administratoren|  
|**db_backupoperator**|Datenbanksicherungs-Operatoren|  
|**db_datareader**|Datenbank-Datenleser|  
|**db_datawriter**|Datenbank-Datenschreiber|  
|**db_denydatareader**|Datenbank-Verweigerungsdatenleser|  
|**db_denydatawriter**|Datenbank-Verweigerungsdatenschreiber|  
  
 In der folgenden Tabelle werden die gespeicherten Prozeduren gezeigt, mit denen Datenbankrollen geändert werden.  
  
|Gespeicherte Prozedur|Aktion|  
|----------------------|------------|  
|**sp_addrolemember**|Fügt einer festen Datenbankrolle einen Datenbankbenutzer hinzu.|  
|**sp_helprole**|Zeigt eine Liste der Mitglieder einer festen Datenbankrolle an.|  
|**sp_droprolemember**|Entfernt ein Mitglied aus einer festen Datenbankrolle.|  
  
## <a name="permissions"></a>Berechtigungen  
 Erfordert die Mitgliedschaft in der **public** -Rolle.  
  
 Die zurückgegebenen Informationen unterliegen den Einschränkungen, die für den Zugriff auf Metadaten gelten. Entitäten, für die der Prinzipal keine Berechtigungen besitzt, werden nicht angezeigt. Weitere Informationen finden Sie unter [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird eine Liste aller festen Datenbankrollen angezeigt.  
  
```  
EXEC sp_helpdbfixedrole;  
GO  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Gespeicherte Systemprozeduren &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)   
 [sp_addrolemember &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addrolemember-transact-sql.md)   
 [Sp_dbfixedrolepermission &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-dbfixedrolepermission-transact-sql.md)   
 [Sp_droprolemember &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-droprolemember-transact-sql.md)   
 [Sp_helprole &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-helprole-transact-sql.md)   
 [Sp_helprolemember &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-helprolemember-transact-sql.md)   
 [Gespeicherte Systemprozeduren &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
