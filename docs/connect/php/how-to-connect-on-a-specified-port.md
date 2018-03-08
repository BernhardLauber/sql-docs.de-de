---
title: "Vorgehensweise: Verbinden über einen angegebenen Port | Microsoft Docs"
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
helpviewer_keywords: connecting to the server, specifying a port
ms.assetid: 65a154d1-375c-439b-a653-7815c9d70ff3
caps.latest.revision: "20"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: c8f5fcabd257f602c9ceba97806b031e95142a76
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-connect-on-a-specified-port"></a>Vorgehensweise: Verbinden über einen angegebenen Port
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

In diesem Thema wird beschrieben, wie über einen angegebenen Port mit der [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)]eine Verbindung zu SQL Server hergestellt wird.  
  
### <a name="to-connect-on-a-specified-port"></a>Verbinden über einen angegebenen Port  
  
1.  Stellen Sie sicher, dass der Port, auf den der Server konfiguriert ist, Verbindungen akzeptiert. Informationen zum Konfigurieren eines Servers zum Akzeptieren von Verbindungen über einen angegebenen Port finden Sie unter [Vorgehensweise: konfigurieren ein Servers zur Überwachung eines bestimmten TCP-Ports (SQL Server-Konfigurations-Manager)](http://go.microsoft.com/fwlink/?LinkId=121865).  
  
2.  Fügen Sie den gewünschten Port dem *$serverName* Parameter von der [Sqlsrv_connect](../../connect/php/sqlsrv-connect.md) Funktion. Trennen Sie den Servernamen und den Port durch ein Komma. Beispielsweise verwenden die folgenden Codezeilen die SQLSRV-Treiber, um zu veranschaulichen, wie die Verbindung mit einem Server namens *myServer* über Port 1521 hergestellt wird:  
  
    ```  
    $serverName = "myServer, 1521";  
    sqlsrv_connect( $serverName );  
    ```  
  
    Die folgenden Codezeilen verwenden den PDO_SQLSRV-Treiber zu um zeigen, wie die Verbindung mit einem Server mit dem Namen *"EigenerServer"* über Port 1521 hergestellt:  
  
    ```  
    $serverName = "(local), 1521";  
    $database = "AdventureWorks";  
    $conn = new PDO( "sqlsrv:server=$serverName;Database=$database", "", "");  
    ```  
  
## <a name="see-also"></a>Siehe auch  
[Verbinden mit dem Server](../../connect/php/connecting-to-the-server.md)  
[Programmierhandbuch für den PHP-SQL-Treiber](../../connect/php/programming-guide-for-php-sql-driver.md)
[Erste Schritte mit dem PHP-SQL-Treiber](../../connect/php/getting-started-with-the-php-sql-driver.md) 
[SQLSRV-Treiber – API-Referenz](../../connect/php/sqlsrv-driver-api-reference.md)  
[Referenz zum Treiber PDO_SQLSRV](../../connect/php/pdo-sqlsrv-driver-reference.md)  
  
