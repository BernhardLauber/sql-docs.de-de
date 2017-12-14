---
title: Zusammenfassung der PolyBase-Funktionen mit Versionsangabe | Microsoft-Dokumentation
ms.custom: 
ms.date: 08/29/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.service: 
ms.component: polybase
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6591994d-6109-4285-9c5b-ecb355f8a111
caps.latest.revision: "10"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 70725ec64b79f538b4129993de83dfd97772a667
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="polybase-versioned-feature-summary"></a>Zusammenfassung der PolyBase-Funktionen mit Versionsangabe
[!INCLUDE[appliesto-ss-xxxx-asdw-pdw-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)] Zusammenfassung der PolyBase-Funktionen, die für SQL Server-Produkte und -Dienste verfügbar sind.  
  
## <a name="feature-summary-for-product-releases"></a>Zusammenfassung der Funktionen für Produktversionen  
 In dieser Tabelle sind die wichtigsten Funktionen für PolyBase sowie die Produkte zusammengefasst, in denen sie verfügbar sind.  
  
||||||
|-|-|-|-|-|   
|**Funktion**|**SQL Server 2016**|**Azure SQL-Datenbank**|**Azure SQL Data Warehouse**|**Parallel Data Warehouse**| 
|Hadoop-Daten abfragen mit [!INCLUDE[tsql](../../includes/tsql-md.md)]|ja|Nein|Nein|ja|
|Daten aus Hadoop importieren|ja|Nein|Nein|ja|
|Daten für Hadoop exportieren  |ja|Nein|Nein| Ja|
|Abfragen, Importieren aus und Exportieren in HDInsights |Nein|Nein|Nein|Nein
|Abfrageberechnungen auf Hadoop verlagern|ja|Nein|Nein|ja|  
|Daten aus Azure-BLOB-Speicher importieren|ja|Nein|Ja|ja| 
|Daten für Azure-BLOB-Speicher exportieren|ja|Nein|Ja|Ja|  
|Daten aus Azure Data Lake Store importieren|Nein|Nein|ja|Nein|    
|Daten aus Azure Data Lake Store exportieren|Nein|Nein|ja|Nein|
|PolyBase-Abfragen über Microsoft BI-Tools ausführen|ja|Nein|Ja|Ja|   


## <a name="pushdown-computation-supported-t-sql-operators"></a>Von der Weitergabeberechnung unterstützte T-SQL-Operatoren
In SQL Server und APS können nicht alle T-SQL-Operatoren an den Hadoop-Cluster weitergegeben werden. Die folgende Tabelle listet alle unterstützten und eine Teilmenge der nicht unterstützten Operatoren auf. 

||||
|-|-|-| 
|**Operatortyp**|**Weitergabe an Hadoop möglich**|**Weitergabe an Blob Storage möglich**|
|Spaltenprojektionen|Ja|Nein|
|Prädikate|Ja|Nein|
|Aggregate|Teilweise|Nein|
|Joins zwischen externen Tabellen|Nein|Nein|
|Joins zwischen externen und lokale Tabellen|Nein|Nein|
|Sortierungen|Nein|Nein|

Partielle Aggregation bedeutet, dass eine endgültige Aggregation erfolgen muss, sobald die Daten SQL Server erreichen, aber ein Teil der Aggregation in Hadoop erfolgt. Dies ist eine häufig verwendete Methode zum Berechnen von Aggregationen in MPP-Systemen (Massively Parallel Processing).  
## <a name="see-also"></a>Siehe auch  
 [PolyBase-Leitfaden](../../relational-databases/polybase/polybase-guide.md)  
  
  
