---
title: XQuery-Abfragen verarbeiten von relationalen Daten | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.prod_service: sql-non-specified
ms.service: 
ms.component: xquery
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- SQL Server
dev_langs:
- XML
helpviewer_keywords:
- relational data [XQuery]
- XQuery, relational data
ms.assetid: 9812b71a-52ec-48a0-92f3-016a93660229
caps.latest.revision: 
author: rothja
ms.author: jroth
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 420caf1620974293f279e72892f0da2cad6a140b
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="xqueries-handling-relational-data"></a>Behandlung relationaler Daten mit XQuery-Abfragen
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Sie XQuery dafür angeben einer **Xml** -Typspalte oder-Variable mithilfe eines der [XML-Datentypmethoden](../t-sql/xml/xml-data-type-methods.md). Dazu gehören **query()**, **value()**, **exist()**, oder **modify()**. Die XQuery wird für die XML-Instanz ausgeführt, die in der XML generierenden Abfrage angegeben ist.  
  
 XML, das durch Ausführen einer XQuery-Abfrage erzeugt wird, kann Werte enthalten, die aus anderen Transact-SQL-Variablen oder aus Rowsetspalten abgerufen werden. Um relationale Nicht-XML-Daten an das XML-Ergebnis zu binden, bietet SQL Server die folgenden Pseudofunktionen als XQuery-Erweiterungen:  
  
-   **sql:column()** function  
  
-   **sql:variable()** function  
  
 Diese XQuery-Erweiterungen können beim Angeben einer XQuery-Abfrage in der **query()** Methode der **Xml** -Datentyp. Daher die **query()** Methode kann XML, das Daten von XML- und nicht-kombiniert erzeugen-**Xml** -Datentypen.  
  
 Sie können diese Funktionen auch verwenden, bei der Verwendung der **Xml** -Datentypmethoden **modify()**, **value()**, **query()**, und  **EXIST()**zum Verfügbarmachen eines relationalen Werts in XML.  
  
 Weitere Informationen finden Sie unter [SQL:Column()-Funktion (XQuery)](../xquery/xquery-extension-functions-sql-column.md) und [SQL:Variable()-Funktion (XQuery)](../xquery/xquery-extension-functions-sql-variable.md).  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Daten &#40;SQL Server&#41;](../relational-databases/xml/xml-data-sql-server.md)   
 [XQuery-Sprachreferenz &#40;SQL Server&#41;](../xquery/xquery-language-reference-sql-server.md)   
 [XML-Konstruktion &#40; XQuery &#41;](../xquery/xml-construction-xquery.md)  
  
  
