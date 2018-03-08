---
title: SCHEMA_ID (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SCHEMA_ID
- SCHEMA_ID_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- identification numbers [SQL Server], schemas
- schemas [SQL Server], IDs
- SCHEMA_ID function
- IDs [SQL Server], schemas
- default schema IDs
ms.assetid: c8e34df5-3eea-459f-ae40-050909ce9fda
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 8ff63abb8b74497b05045a2892067d7b4e49140a
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="schemaid-transact-sql"></a>SCHEMA_ID (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Gibt die Schema-ID zurück, die einem Schemanamen zugeordnet ist.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
SCHEMA_ID ( [ schema_name ] )   
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|----------|----------------|  
|*schema_name*|Der Name des Schemas. *Schema_name* ist ein **Sysname**. Wenn *Schema_name* nicht angegeben ist, SCHEMA_ID die ID des Standardschemas des Aufrufers zurück.|  
  
## <a name="return-types"></a>Rückgabetypen  
 **int**  
  
 NULL wird zurückgegeben, wenn *Schema_name* ist kein gültiges Schema.  
  
## <a name="remarks"></a>Hinweise  
 SCHEMA_ID gibt IDs von Systemschemas und benutzerdefinierten Schemas zurück. SCHEMA_ID kann in einer Auswahlliste, in einer WHERE-Klausel und überall dort aufgerufen werden, wo ein Ausdruck zulässig ist.  
  
## <a name="examples"></a>Beispiele  
  
### <a name="a-returning-the-default-schema-id-of-a-caller"></a>A. Zurückgeben der Standardschema-ID eines Aufrufers  
  
```  
SELECT SCHEMA_ID();  
```  
  
### <a name="b-returning-the-schema-id-of-a-named-schema"></a>B. Zurückgeben der Schema-ID eines benannten Schemas  
  
```  
SELECT SCHEMA_ID('dbo');  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenfunktionen &#40; Transact-SQL &#41;](../../t-sql/functions/metadata-functions-transact-sql.md)   
 [SCHEMA_NAME &#40; Transact-SQL &#41;](../../t-sql/functions/schema-name-transact-sql.md)   
 [Sys.Schemas &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/schemas-catalog-views-sys-schemas.md)  
  
  

