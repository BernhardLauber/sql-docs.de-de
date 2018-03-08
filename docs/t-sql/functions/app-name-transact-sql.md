---
title: App_name (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/24/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- APP_NAME_TSQL
- APP_NAME
dev_langs:
- TSQL
helpviewer_keywords:
- name checking for current session [SQL Server]
- sessions [SQL Server], application names
- applications [SQL Server], names
- current session application names
- APP_NAME function
ms.assetid: e491e192-9b30-4243-bc19-33c133fe08a8
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: b2b65f2380cc52c7a1d084dedad5fdb744d377bf
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="appname-transact-sql"></a>APP_NAME (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Gibt den Anwendungsnamen der aktuellen Sitzung zurück, falls von der Anwendung ein Name festgelegt wurde.
  
> [!IMPORTANT]  
>  Der Name der Anwendung wird vom Client bereitgestellt und auf keinerlei Weise überprüft. Verwenden Sie keine **APP_NAME** als Teil einer sicherheitsprüfung.  
  
![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntax  
  
```sql
  
APP_NAME  ( )  
```  
  
## <a name="return-types"></a>Rückgabetypen  
**vom Datentyp nvarchar(128)**
  
## <a name="remarks"></a>Hinweise  
Verwendung **APP_NAME** Wenn Sie verschiedene Aktionen für unterschiedliche Anwendungen durchführen möchten. Beispielsweise können Sie ein Daten für verschiedene Anwendungen unterschiedlich formatieren oder eine informative Meldung an bestimmte Anwendungen zurückgeben.
  
Zum Festlegen eines Anwendungsnamens [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]in der **Verbindung mit Datenbankmodul herstellen** (Dialogfeld), klicken Sie auf **Optionen**. Auf der **zusätzliche Verbindungsparameter** Registerkarte, geben Sie eine **app** Attribut im Format`;app='application_name'`
  
## <a name="examples"></a>Beispiele  
Im folgenden Beispiel wird überprüft, ob die Clientanwendung, die diesen Prozess initiiert hat, eine `SQL Server Management Studio`-Sitzung ist und ein Datum im US- oder ANSI-Format bereitstellt.
  
```sql
USE AdventureWorks2012;  
GO  
IF APP_NAME() = 'Microsoft SQL Server Management Studio - Query'  
PRINT 'This process was started by ' + APP_NAME() + '. The date is ' + CONVERT ( varchar(100) , GETDATE(), 101) + '.';  
ELSE   
PRINT 'This process was started by ' + APP_NAME() + '. The date is ' + CONVERT ( varchar(100) , GETDATE(), 102) + '.';  
GO  
```  
  
## <a name="see-also"></a>Siehe auch
[Systemfunktionen &#40; Transact-SQL &#41;](../../relational-databases/system-functions/system-functions-for-transact-sql.md)  
[Funktionen](../../t-sql/functions/functions.md)
  
  
