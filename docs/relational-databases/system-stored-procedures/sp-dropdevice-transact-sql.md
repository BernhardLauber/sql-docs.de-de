---
title: Sp_dropdevice (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 08/09/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_dropdevice_TSQL
- sp_dropdevice
dev_langs:
- TSQL
helpviewer_keywords:
- backup devices [SQL Server], deleting
- sp_dropdevice
ms.assetid: c8b07189-7c35-414b-acc1-45bd6e7e17c3
caps.latest.revision: 
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 1286184ef82308ed12c8c8209b14eeb2a83f86a9
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2018
---
# <a name="spdropdevice-transact-sql"></a>sp_dropdevice (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Löscht ein Datenbank- oder Sicherungsmedium aus einer Instanz von der [!INCLUDE[ssDEversion2005](../../includes/ssdeversion2005-md.md)], durch das Löschen des Eintrags in **master.dbo.sysdevices**.  
   
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
sp_dropdevice [ @logicalname = ] 'device'   
    [ , [ @delfile = ] 'delfile' ]  
```  
  
## <a name="arguments"></a>Argumente  
 [ **@logicalname=** ] **'***device***'**  
 Ist der logische Name des Datenbank- oder Sicherungsmediums gemäß **master.dbo.sysdevices.name**. *Gerät* ist **Sysname**, hat keinen Standardwert.  
  
 [ **@delfile=** ] **'***delfile***'**  
 Gibt an, ob die physische Sicherungsmediumsdatei gelöscht werden soll. *Delfile* ist **vom Datentyp varchar(7)**. Bei Angabe als **DELFILE**, die Datenträgerdatei physische Sicherungsmedium wird gelöscht.  
  
## <a name="return-code-values"></a>Rückgabecodewerte  
 0 (Erfolg) oder 1 (Fehler)  
  
## <a name="result-sets"></a>Resultsets  
 Keine  
  
## <a name="remarks"></a>Hinweise  
 **Sp_dropdevice** kann nicht innerhalb einer Transaktion verwendet werden.  
  
## <a name="permissions"></a>Berechtigungen  
 Erfordert die Mitgliedschaft in der festen Serverrolle **diskadmin** .  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird das `tapedump1`-Bandsicherungsmedium aus [!INCLUDE[ssDE](../../includes/ssde-md.md)] gelöscht.  
  
```  
EXEC sp_dropdevice 'tapedump1';  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Sicherungsmedien &#40;SQL Server&#41;](../../relational-databases/backup-restore/backup-devices-sql-server.md)   
 [Löschen eines Sicherungsmediums &#40; SQLServer &#41;](../../relational-databases/backup-restore/delete-a-backup-device-sql-server.md)   
 [sp_addumpdevice &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql.md)   
 [sp_helpdb &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-helpdb-transact-sql.md)   
 [sp_helpdevice &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-helpdevice-transact-sql.md)   
 [Gespeicherte Systemprozeduren &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
