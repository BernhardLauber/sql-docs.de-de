---
title: XML (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/26/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|xml
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- xml_TSQL
- xml
dev_langs: TSQL
helpviewer_keywords: xml data type [SQL Server], about xml data type
ms.assetid: 9198f671-8e61-4ca4-9c3a-859f84020e62
caps.latest.revision: "35"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: b738180bbf6b2f3f18bbd38ebfe7139736f33cee
ms.sourcegitcommit: 6c54e67818ec7b0a2e3c1f6e8aca0fdf65e6625f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="xml-transact-sql"></a>xml (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Der Datentyp, in dem XML-Daten gespeichert sind. Sie können speichern **Xml** Instanzen in einer Spalte oder eine Variable vom **Xml** Typ.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
xml ( [ CONTENT | DOCUMENT ] xml_schema_collection )  
```  
  
## <a name="arguments"></a>Argumente  
 CONTENT  
 Schränkt die **Xml** Instanz ein wohlgeformtes XML-Fragment ist. Die XML-Daten können keine oder auch mehrere Elemente auf der obersten Ebene enthalten. Textknoten sind auf der obersten Ebene ebenfalls zulässig.  
  
 Dies ist das Standardverhalten.  
  
 DOCUMENT  
 Schränkt die **Xml** Instanz ein wohlgeformtes XML-Dokument ist. Die XML-Daten müssen genau ein Stammelement aufweisen. Textknoten sind auf der obersten Ebene nicht zulässig.  
  
 *xml_schema_collection*  
 Der Name einer XML-Schemaauflistung. So erstellen eine typisierte **Xml** Spalte oder Variable ist, können Sie optional den Namen der XML-schemaauflistung angeben. Weitere Informationen zu typisierten und nicht typisiertes XML, finden Sie unter [Vergleichen von typisiertem XML mit nicht typisiertem XML](../../relational-databases/xml/compare-typed-xml-to-untyped-xml.md).  
  
## <a name="remarks"></a>Hinweise  
 Die gespeicherte Darstellung von **Xml** -datentypinstanzen darf 2 Gigabyte (GB) nicht überschreiten.  
  
 Die Facets CONTENT und DOCUMENT beziehen sich nur auf typisierte XML-Daten. Weitere Informationen finden Sie unter [Vergleichen von typisiertem XML mit nicht typisiertem XML](../../relational-databases/xml/compare-typed-xml-to-untyped-xml.md).  
  
## <a name="examples"></a>Beispiele  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @y xml (Sales.IndividualSurveySchemaCollection);  
SET @y =  (SELECT TOP 1 Demographics FROM Sales.Individual);  
SELECT @y;  
GO  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypkonvertierung &#40; Datenbankmodul &#41;](../../t-sql/data-types/data-type-conversion-database-engine.md)   
 [Datentypen &#40;Transact-SQL&#41;](../../t-sql/data-types/data-types-transact-sql.md)   
 [xml-Datentypmethoden](../../t-sql/xml/xml-data-type-methods.md)   
 [XQuery-Sprachreferenz &#40;SQL Server&#41;](../../xquery/xquery-language-reference-sql-server.md)  
  
  
