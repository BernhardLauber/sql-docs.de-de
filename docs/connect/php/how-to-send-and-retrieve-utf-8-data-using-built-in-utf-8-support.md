---
title: "Vorgehensweise: Senden und Abrufen von UTF-8-Daten mithilfe der eingebauten UTF-8-Unterstützung | Microsoft Docs"
ms.custom: 
ms.date: 01/16/2018
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: php
ms.reviewer: 
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retrieving data, UTF-8 encoded data
- converting data types
- updating data
ms.assetid: 366c57cf-352f-4202-8074-6ddce44880d1
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 2d2763ec8906cc3100c1259aa25473ae7e8d8b22
ms.sourcegitcommit: 6b1618aa3b24bf6759b00a820e09c52c4996ca10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="how-to-send-and-retrieve-utf-8-data-using-built-in-utf-8-support"></a>Vorgehensweise: Senden und Abrufen von UTF-8-Daten mithilfe der eingebauten UTF-8-Unterstützung.
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Wenn Sie den PDO_SQLSRV-Treiber verwenden, können Sie die Codierung mit dem Attribut „PDO::SQLSRV_ATTR_ENCODING“ festlegen. Weitere Informationen finden Sie unter [Konstanten &#40;Microsoft-Treiber für PHP für SQL Server&#41;](../../connect/php/constants-microsoft-drivers-for-php-for-sql-server.md).  
  
Im weiteren Verlauf dieses Themas wird die Codierung mit dem SQLSRV-Treiber erläutert.  
  
Gehen Sie zum Senden/Abrufen von UTF-8-codierten Daten an den/vom Server wie folgt vor:  
  
1.  Stellen Sie sicher, dass die Quell- oder Ziel-Spalte den Typ **nchar** oder **nvarchar**aufweist.  
  
2.  Geben Sie im Parameterarray `SQLSRV_PHPTYPE_STRING('UTF-8')` als PHP-Typ an. Oder legen Sie `"CharacterSet" => "UTF-8"` als eine Verbindungsoption fest.  
  
    Wenn Sie einen Zeichensatz als Teil der Verbindungsoptionen angeben, geht der Treiber davon aus, dass auch die anderen Optionszeichenfolgen der Verbindung den gleichen Zeichensatz verwenden. Auch beim Servernamen und den Abfragezeichenfolgen geht er vom selben Zeichensatz aus.  
  
Sie können übergeben, UTF-8 oder "sqlsrv_enc_char" an **CharacterSet** (Sie können keine SQLSRV_ENC_BINARY übergeben). Die Standardcodierung ist „SQLSRV_ENC_CHAR“.  
  
## <a name="example"></a>Beispiel  
Im folgenden Beispiel wird veranschaulicht, wie Sie bei der Herstellung der Verbindung, durch die Festlegung auf den UTF-8 Zeichensatz, das Senden und Empfangen von UTF-8-codierten Daten ermöglichen. Das Beispiel aktualisiert die Spalte „Kommentare“ der Tabelle „Produktion.ProduktReview“ auf eine angegebene Review-ID. Das Beispiel ruft auch die neuen, aktualisierten Daten auf und zeigt sie an. Die Kommentare-Spalte ist vom Typ **nvarchar(3850).** Beachten Sie, dass sie vor dem Senden von Daten an den Server in UTF-8-Codierung mit der PHP konvertiert wird **utf8_encode** Funktion. Dieser Schritt erfolgt nur zu Demonstrationszwecken. In einem realen Anwendungsszenario würden Sie mit UTF-8-codierten Daten beginnen.  
  
Das Beispiel setzt voraus, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] und die [AdventureWorks](http://go.microsoft.com/fwlink/?LinkID=67739) -Datenbank auf dem lokalen Computer installiert sind. Wenn das Beispiel über den Browser ausgeführt wird, werden alle Ausgaben im Browser geschrieben.  
  
```  
<?php  
  
// Connect to the local server using Windows Authentication and  
// specify the AdventureWorks database as the database in use.   
//   
$serverName = "MyServer";  
$connectionInfo = array( "Database"=>"AdventureWorks", "CharacterSet" => "UTF-8");  
$conn = sqlsrv_connect( $serverName, $connectionInfo);  
  
if ( $conn === false ) {  
   echo "Could not connect.<br>";  
   die( print_r( sqlsrv_errors(), true));  
}  
  
// Set up the Transact-SQL query.  
//   
$tsql1 = "UPDATE Production.ProductReview  
          SET Comments = ?  
          WHERE ProductReviewID = ?";  
  
// Set the parameter values and put them in an array. Note that  
// $comments is converted to UTF-8 encoding with the PHP function  
// utf8_encode to simulate an application that uses UTF-8 encoded data.   
//   
$reviewID = 3;  
$comments = utf8_encode("testing 1, 2, 3, 4.  Testing.");  
$params1 = array(  
                  array( $comments, null ),  
                  array( $reviewID, null )  
                );  
  
// Execute the query.  
//   
$stmt1 = sqlsrv_query($conn, $tsql1, $params1);  
  
if ( $stmt1 === false ) {  
   echo "Error in statement execution.<br>";  
   die( print_r( sqlsrv_errors(), true));  
}  
else {  
   echo "The update was successfully executed.<br>";  
}  
  
// Retrieve the newly updated data.  
//   
$tsql2 = "SELECT Comments   
          FROM Production.ProductReview   
          WHERE ProductReviewID = ?";  
  
// Set up the parameter array.  
//   
$params2 = array($reviewID);  
  
// Execute the query.  
//   
$stmt2 = sqlsrv_query($conn, $tsql2, $params2);  
if ( $stmt2 === false ) {  
   echo "Error in statement execution.<br>";  
   die( print_r( sqlsrv_errors(), true));  
}  
  
// Retrieve and display the data.   
//   
if ( sqlsrv_fetch($stmt2) ) {  
   echo "Comments: ";  
   $data = sqlsrv_get_field( $stmt2, 0 );  
   echo $data."<br>";  
}  
else {  
   echo "Error in fetching data.<br>";  
   die( print_r( sqlsrv_errors(), true));  
}  
  
// Free statement and connection resources.  
//   
sqlsrv_free_stmt( $stmt1 );  
sqlsrv_free_stmt( $stmt2 );  
sqlsrv_close( $conn);  
?>  
```  
  
Informationen zum Speichern von Unicode-Daten finden Sie unter [Arbeiten mit Unicode-Daten](http://go.microsoft.com/fwlink/?LinkId=128236).  
  
## <a name="example"></a>Beispiel  
Das folgende Beispiel ähnelt dem ersten Beispiel, aber statt der Festlegung des UTF-8-Zeichensatzes für die Verbindung, veranschaulicht dieses Beispiel die Festlegung des UTF-8-Zeichensatzes für die Spalte.  
  
```  
<?php  
  
// Connect to the local server using Windows Authentication and  
// specify the AdventureWorks database as the database in use.   
//   
$serverName = "MyServer";  
$connectionInfo = array( "Database"=>"AdventureWorks");  
$conn = sqlsrv_connect( $serverName, $connectionInfo);  
  
if ( $conn === false ) {  
   echo "Could not connect.<br>";  
   die( print_r( sqlsrv_errors(), true));  
}  
  
// Set up the Transact-SQL query.  
//   
$tsql1 = "UPDATE Production.ProductReview  
          SET Comments = ?  
          WHERE ProductReviewID = ?";  
  
// Set the parameter values and put them in an array. Note that  
// $comments is converted to UTF-8 encoding with the PHP function  
// utf8_encode to simulate an application that uses UTF-8 encoded data.   
//   
$reviewID = 3;  
$comments = utf8_encode("testing");  
$params1 = array(  
                  array($comments,  
                        SQLSRV_PARAM_IN,  
                        SQLSRV_PHPTYPE_STRING('UTF-8')  
                  ),  
                  array($reviewID)  
                );  
  
// Execute the query.  
//   
$stmt1 = sqlsrv_query($conn, $tsql1, $params1);  
  
if ( $stmt1 === false ) {  
   echo "Error in statement execution.<br>";  
   die( print_r( sqlsrv_errors(), true));  
}  
else {  
   echo "The update was successfully executed.<br>";  
}  
  
// Retrieve the newly updated data.  
//   
$tsql2 = "SELECT Comments   
          FROM Production.ProductReview   
          WHERE ProductReviewID = ?";  
  
// Set up the parameter array.  
//   
$params2 = array($reviewID);  
  
// Execute the query.  
//   
$stmt2 = sqlsrv_query($conn, $tsql2, $params2);  
if ( $stmt2 === false ) {  
   echo "Error in statement execution.<br>";  
   die( print_r( sqlsrv_errors(), true));  
}  
  
// Retrieve and display the data.   
//   
if ( sqlsrv_fetch($stmt2) ) {  
   echo "Comments: ";  
   $data = sqlsrv_get_field($stmt2,   
                            0,   
                            SQLSRV_PHPTYPE_STRING('UTF-8')  
                           );  
   echo $data."<br>";  
}  
else {  
   echo "Error in fetching data.<br>";  
   die( print_r( sqlsrv_errors(), true));  
}  
  
// Free statement and connection resources.  
//   
sqlsrv_free_stmt( $stmt1 );  
sqlsrv_free_stmt( $stmt2 );  
sqlsrv_close( $conn);  
?>  
```  
  
## <a name="see-also"></a>Siehe auch  
[Abrufen von Daten](../../connect/php/retrieving-data.md)  
[Arbeiten mit ASCII-Daten in nicht-Windows](../../connect/php/how-to-send-and-retrieve-ascii-data-in-linux-mac.md)
[Aktualisieren von Daten &#40;Microsoft Drivers for PHP for SQL Server&#41;](../../connect/php/updating-data-microsoft-drivers-for-php-for-sql-server.md)  
[API-Referenz für den SQLSRV-Treiber](../../connect/php/sqlsrv-driver-api-reference.md)  
[Konstanten &#40;Microsoft-Treiber für PHP für SQL Server&#41;](../../connect/php/constants-microsoft-drivers-for-php-for-sql-server.md)  
[Beispielanwendung &#40;SQLSRV-Treiber&#41;](../../connect/php/example-application-sqlsrv-driver.md)  
  
