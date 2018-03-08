---
title: Festlegen der Data Datenquelleneigenschaften | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: jdbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f3363d05-07fc-4bf8-ae5e-2a7a968808ad
caps.latest.revision: "20"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 77550572f392ddce8c442106bda7456fda08dd53
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="setting-the-data-source-properties"></a>Festlegen der Datenquelleneigenschaften
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  Datenquellen bilden den bevorzugten Mechanismus, mit dem in einer Umgebung der Java-Plattform, Enterprise Edition (Java EE) JDBC-Verbindungen erstellt werden. Datenquellen ermöglichen Verbindungen, Poolverbindungen und verteilte Verbindungen, ohne die Verbindungseigenschaften fest im Java-Code codieren zu müssen. Alle [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] Datenquellen festlegen oder den Wert einer beliebigen Eigenschaft abrufen, indem Sie mit den entsprechenden Abruf-Abrufmethoden, bzw. können.  
  
 Java EE-Produkte wie Anwendungsserver und Servlet-/JSP-Module lassen normalerweise die Konfiguration von Datenquellen für den Datenbankzugriff zu. Jede Eigenschaft aufgeführt, die der [Festlegen der Verbindungseigenschaften](../../connect/jdbc/setting-the-connection-properties.md) Thema kann angegeben werden, immer, wenn die Konfiguration können Sie eine Eigenschaft als Eigenschaft geben Sie = Wert-Paar.  
  
 Weitere Informationen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] -Datenquellen finden Sie unter der [SQLServerDataSource](../../connect/jdbc/reference/sqlserverdatasource-class.md) Klasse. Ein Beispiel dafür, wie die SQLServerDataSource-Klasse verwendet wird, zum Herstellen einer Verbindung mit einem [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] finden Sie unter [-Datenquellenbeispiel](../../connect/jdbc/data-source-sample.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verbinden von SQL Server mit dem JDBC-Treiber](../../connect/jdbc/connecting-to-sql-server-with-the-jdbc-driver.md)  
  
  
