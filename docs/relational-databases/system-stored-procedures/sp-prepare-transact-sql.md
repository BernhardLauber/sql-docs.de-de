---
title: Sp_prepare (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2018
ms.prod: sql
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.service: ''
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_cursor_prepare_TSQL
- sp_cursor_prepare
dev_langs:
- TSQL
helpviewer_keywords:
- sp_prepare
ms.assetid: f328c9eb-8211-4863-bafa-347e1bf7bb3f
caps.latest.revision: 9
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
monikerRange: '>= aps-pdw-2016 || = azure-sqldw-latest || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: 363b1a822cc5fa748ee573c2dd613826f9359f1f
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="spprepare-transact-sql"></a>sp_prepare (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2008-xxxx-asdw-pdw-md.md)]

  Bereitet eine parametrisierte [!INCLUDE[tsql](../../includes/tsql-md.md)] Anweisung und gibt eine Anweisung *behandeln* für die Ausführung. Sp_prepare wird aufgerufen, indem ID = 11 in einem tabular Data Stream (TDS)-Paket.  
  
 ![Artikellinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL-Syntaxkonventionen](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
sp_prepare handle OUTPUT, params, stmt, options  
```  
  
## <a name="arguments"></a>Argumente  
 *Handle*  
 Ein SQL Server generierter *vorbereitete Handle* Bezeichner. *handle* ist ein erforderlicher Parameter mit einem **int** -Rückgabewert.  
  
 *params*  
 Identifiziert parametrisierte Anweisungen. Die *params* -Definition der Variablen wird in der Anweisung an die Stelle der Parametermarkierungen gesetzt. *params* ist ein erforderlicher Parameter, der einen Eingabewert vom Typ **ntext**, **nchar**,oder **nvarchar** erfordert. Geben Sie einen NULL-Wert ein, wenn die Anweisung nicht parametrisiert ist.  
  
 *stmt*  
 Definiert das Resultset des Cursors. Die *Stmt* -Parameter ist erforderlich und erfordert eine **Ntext**, **Nchar**, oder **Nvarchar** Eingabewert.  
  
 *options*  
 Ein optionaler Parameter, der eine Beschreibung der Spalten im Cursorresultset zurückgibt. *Optionen* den folgenden Int-Eingabewert erfordert:  
  
|Wert|Description|  
|-----------|-----------------|  
|0x0001|RETURN_METADATA|  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird eine einfache Anweisung vorbereitet und ausgeführt.  
  
```  
Declare @P1 int;  
Exec sp_prepare @P1 output,   
    N'@P1 nvarchar(128), @P2 nvarchar(100)',  
    N'SELECT database_id, name FROM sys.databases WHERE name=@P1 AND state_desc = @P2';  
Exec sp_execute @P1, N'tempdb', N'ONLINE';  
EXEC sp_unprepare @P1;  
```  

  
## <a name="see-also"></a>Siehe auch  
 [Gespeicherte Systemprozeduren &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  

