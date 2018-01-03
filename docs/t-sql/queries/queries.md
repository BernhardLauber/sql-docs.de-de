---
title: Abfragen | Microsoft Docs
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: t-sql|queries
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: TSQL
ms.assetid: 5ff02a32-e8d3-479c-ae8b-07581e41f5f8
caps.latest.revision: "8"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Active
ms.openlocfilehash: 8d7e4bf6357fe56f3c9b6a1e67e9e6aeb3675930
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="queries"></a>Abfragen
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  (Data Manipulation Language, DML) ist ein Vokabular zum Abrufen und Bearbeiten von Daten in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] und SQL-Datenbank. Die meisten funktionieren auch in SQL Data Warehouse und PDW (Überprüfen Sie jede einzelne Anweisung Einzelheiten). Verwenden Sie die Anweisungen zum Hinzufügen, ändern, abzufragen oder Entfernen von Daten aus einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datenbank.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 In der folgenden Tabelle sind die DML-Anweisungen aufgeführt, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendet.  
  
|||  
|-|-|  
|[BULK INSERT &#40;Transact-SQL&#41;](../../t-sql/statements/bulk-insert-transact-sql.md)|[SELECT &#40;Transact-SQL&#41;](../../t-sql/queries/select-transact-sql.md)|  
|[DELETE &#40;Transact-SQL&#41;](../../t-sql/statements/delete-transact-sql.md)|[UPDATE &#40;Transact-SQL&#41;](../../t-sql/queries/update-transact-sql.md)|  
|[INSERT &#40;Transact-SQL&#41;](../../t-sql/statements/insert-transact-sql.md)|[UPDATETEXT &#40; Transact-SQL &#41;](../../t-sql/queries/updatetext-transact-sql.md)|  
|[MERGE &#40;Transact-SQL&#41;](../../t-sql/statements/merge-transact-sql.md)|[WRITETEXT (Transact-SQL)](../../t-sql/queries/writetext-transact-sql.md)|  
|[READTEXT &#40; Transact-SQL &#41;](../../t-sql/queries/readtext-transact-sql.md)||  
  
 In der folgenden Tabelle sind die Klauseln aufgeführt, die in mehreren DML-Anweisungen oder -Klauseln verwendet werden.  
  
|Klausel|Kann in folgenden Anweisungen verwendet werden|  
|------------|-------------------------------------|  
|[FROM &#40;Transact-SQL&#41;](../../t-sql/queries/from-transact-sql.md)|DELETE, SELECT, UPDATE|  
|[Tabellenhinweise &#40; Transact-SQL &#41;](../../t-sql/queries/hints-transact-sql.md)|DELETE, INSERT, SELECT, UPDATE|  
|[OPTION-Klausel &#40; Transact-SQL &#41;](../../t-sql/queries/option-clause-transact-sql.md)|DELETE, SELECT, UPDATE|  
|[OUTPUT Clause &#40;Transact-SQL&#41;](../../t-sql/queries/output-clause-transact-sql.md)|DELETE, INSERT, MERGE, UPDATE|  
|[Suchbedingung &#40; Transact-SQL &#41;](../../t-sql/queries/search-condition-transact-sql.md)|DELETE, MERGE, SELECT, UPDATE|  
|[Tabellenwertkonstruktor &#40; Transact-SQL &#41;](../../t-sql/queries/table-value-constructor-transact-sql.md)|FROM, INSERT, MERGE|  
|[Nach oben &#40; Transact-SQL &#41;](../../t-sql/queries/top-transact-sql.md)|DELETE, INSERT, MERGE, SELECT, UPDATE|  
|[WOBEI &#40; Transact-SQL &#41;](../../t-sql/queries/where-transact-sql.md)|DELETE, SELECT, UPDATE, ÜBEREINSTIMMUNG|  
|[WITH Common_table_expression &#40; Transact-SQL &#41;](../../t-sql/queries/with-common-table-expression-transact-sql.md)|DELETE, INSERT, MERGE, SELECT, UPDATE|  
  
  
