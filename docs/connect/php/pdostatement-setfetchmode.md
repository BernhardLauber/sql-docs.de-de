---
title: 'Pdostatement:: Setfetchmode | Microsoft Docs'
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: php
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f132b2af-0433-4fbe-b03f-69a7d631093a
caps.latest.revision: "10"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: c9a74cc4c0e84c2a236d6c78a1a7f315d7fed069
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="pdostatementsetfetchmode"></a>PDOStatement::setFetchMode
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Gibt den Fetch-Modus für das PDOStatement-Handle an.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
bool PDOStatement::setFetchMode( $mode );  
```  
  
#### <a name="parameters"></a>Parameter  
$*Modus*: alle Parameter, die Übergabe an gültig sind [pdostatement:: FETCH](../../connect/php/pdostatement-fetch.md).  
  
## <a name="return-value"></a>Rückgabewert  
„true“ bei Erfolg, andernfalls „false“.  
  
## <a name="remarks"></a>Hinweise  
Unterstützung für PDO wurde in Version 2.0 von [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)]hinzugefügt.  
  
## <a name="example"></a>Beispiel  
  
```  
<?php  
   $server = "(local)";  
   $database = "AdventureWorks";  
   $conn = new PDO( "sqlsrv:server=$server ; Database = $database", "", "");  
  
   $stmt1 = $conn->query( "select * from Person.ContactType where ContactTypeID < 5 " );  
   while ( $row = $stmt1->fetch()) {   
      print($row['Name'] . "\n");   
   }  
   print( "\n---------- PDO::FETCH_ASSOC -------------\n" );  
   $stmt = $conn->query( "select * from Person.ContactType where ContactTypeID < 5 " );  
   $stmt->setFetchMode(PDO::FETCH_ASSOC);  
   $result = $stmt->fetch();  
   print_r( $result );  
  
   print( "\n---------- PDO::FETCH_NUM -------------\n" );  
   $stmt = $conn->query( "select * from Person.ContactType where ContactTypeID < 5 " );  
   $stmt->setFetchMode(PDO::FETCH_NUM);  
   $result = $stmt->fetch();  
   print_r ($result );  
  
   print( "\n---------- PDO::FETCH_BOTH -------------\n" );  
   $stmt = $conn->query( "select * from Person.ContactType where ContactTypeID < 5 " );  
   $stmt->setFetchMode(PDO::FETCH_BOTH);  
   $result = $stmt->fetch();  
   print_r( $result );  
  
   print( "\n---------- PDO::FETCH_LAZY -------------\n" );  
   $stmt = $conn->query( "select * from Person.ContactType where ContactTypeID < 5 " );  
   $stmt->setFetchMode(PDO::FETCH_LAZY);  
   $result = $stmt->fetch();  
   print_r( $result );  
  
   print( "\n---------- PDO::FETCH_OBJ -------------\n" );  
   $stmt = $conn->query( "select * from Person.ContactType where ContactTypeID < 5 " );  
   $stmt->setFetchMode(PDO::FETCH_OBJ);  
   $result = $stmt->fetch();  
   print $result->Name;  
   print( "\n \n" );  
?>  
```  
  
## <a name="see-also"></a>Siehe auch  
[PDOStatement-Klasse](../../connect/php/pdostatement-class.md)  
[PDO](http://go.microsoft.com/fwlink/?LinkID=187441)  
  
