---
title: SUSER_NAME (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: sql-data-warehouse, sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SUSER_NAME
- SUSER_NAME_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- security identification names [SQL Server]
- logins [SQL Server], users
- identification names for logins [SQL Server]
- users [SQL Server], logins
- SUSER_NAME function
- logins [SQL Server], names
- names [SQL Server], logins
ms.assetid: ae598d9f-9baa-49b8-b1c1-042854206de4
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: cb236dc3ae7f74ad77ba398e328d4a0bf93a079b
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="susername-transact-sql"></a>SUSER_NAME (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-asdw-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-asdw-xxx-md.md)]

  Gibt den Anmeldenamen des Benutzers zurück.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
SUSER_NAME ( [ server_user_id ] )   
```  
  
## <a name="arguments"></a>Argumente  
 *server_user_id*  
 Die numerische Anmelde-ID des Benutzers. *Server_user_id*, ist optional und wird **Int**. *Server_user_id* kann der numerischen Anmelde-ID eines beliebigen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Anmeldung oder [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Benutzer oder eine Gruppe mit der Berechtigung zur Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Wenn *Server_user_id* ist nicht angegeben wird, der Anmeldenamen für den aktuellen Benutzer zurückgegeben. Wenn der Parameter das Wort NULL enthalten ist, wird NULL zurückgegeben.  
  
## <a name="return-types"></a>Rückgabetypen  
 **vom Datentyp nvarchar(128)**  
  
## <a name="remarks"></a>Hinweise  
 In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 ersetzt die Sicherheits-ID (SID, Security Identification Number) die ID des Serverbenutzers (SUID, Server User Identification Number).  
  
 SUSER_NAME gibt einen Anmeldenamen nur für eine Anmeldung, das einen Eintrag in der **Syslogins** -Systemtabelle.  
  
 SUSER_NAME kann in einer Auswahlliste, in einer WHERE-Klausel und überall dort, wo ein Ausdruck zulässig ist, verwendet werden. Auf den Funktionsnamen müssen immer Klammern folgen, auch wenn kein Parameter angegeben wird.  
  
## <a name="examples"></a>Beispiele  
 Das folgende Beispiel gibt die Anmelde-ID des Benutzers mit der numerischen Anmelde-ID `1` zurück.  
  
```  
SELECT SUSER_NAME(1);  
```  
  
## <a name="see-also"></a>Siehe auch  
 [SUSER_ID &#40; Transact-SQL &#41;](../../t-sql/functions/suser-id-transact-sql.md)   
 [Prinzipale &#40;Datenbankmodul&#41;](../../relational-databases/security/authentication-access/principals-database-engine.md)  
  
  
