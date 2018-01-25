---
title: Erstellen der Datenbank (Parallel Datawarehouse) | Microsoft Docs
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: pdw
ms.service: 
ms.component: t-sql|statements
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40cacde4-ac72-45f7-9564-d76e2b4a741a
caps.latest.revision: "13"
author: barbkess
ms.author: barbkess
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 4e9ff76a4d260604a93f59baa3b61f5c37b4952f
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="create-database-parallel-data-warehouse"></a>CREATE DATABASE (Parallel Data Warehouse)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md.md)]

  Erstellt eine neue Datenbank auf einem [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] Appliance. Verwenden Sie diese Anweisung, um alle einer Anwendungsdatenbank zugeordneten Dateien erstellen und die maximale Größe und die automatische Vergrößerung-Optionen für die Datenbanktabellen und das Transaktionsprotokoll festzulegen.  
  
 ![Symbol für Themenlink](../../database-engine/configure-windows/media/topic-link.gif "Thema Linksymbol") [Transact-SQL-Syntaxkonventionen &#40; Transact-SQL &#41;](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
CREATE DATABASE database_name   
WITH (   
    [ AUTOGROW = ON | OFF , ]   
    REPLICATED_SIZE = replicated_size [ GB ] ,  
    DISTRIBUTED_SIZE = distributed_size [ GB ] ,  
    LOG_SIZE = log_size [ GB ] )  
[;]  
```  
  
## <a name="arguments"></a>Argumente  
 *database_name*  
 Der Name der neuen Datenbank. Weitere Informationen zu zulässigen Datenbanknamen verwendet, finden Sie unter "Reservierte Namen" und "Benennungsregeln für Objekt" in der [!INCLUDE[pdw-product-documentation](../../includes/pdw-product-documentation-md.md)].  
  
 AUTOMATISCHE VERGRÖSSERUNG = ON | **OFF**  
 Gibt an, ob die *Replicated_size*, *Distributed_size*, und *Log_size* Parameter für diese Datenbank werden automatisch vergrößert, hinter ihren angegebenen nach Bedarf Größen. Standardwert ist **OFF**.  
  
 Wenn die automatische VERGRÖßERUNG auf ON festgelegt ist *Replicated_size*, *Distributed_size*, und *Log_size* wächst als erforderlich (nicht in Blöcke mit der angegebenen Anfangsgröße) bei jeder dateneinfügung Update oder eine andere Aktion, die mehr Speicherplatz als benötigt wurde bereits zugeordnet.  
  
 Wenn die automatische VERGRÖßERUNG auf OFF festgelegt ist, werden die Größe nicht automatisch vergrößert. [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]Gibt einen Fehler zurück, wenn eine Aktion versucht wird, die erfordert *Replicated_size*, *Distributed_size*, oder *Log_size* , über den angegebenen Wert zu vergrößern.  
  
 Automatische VERGRÖßERUNG ist entweder für alle Größen ON oder OFF für alle Größen. Ist beispielsweise nicht möglich ist, legen Sie die automatische VERGRÖßERUNG ON *Log_size*, aber nicht für *Replicated_size*.  
  
 *replicated_size* [ GB ]  
 Eine positive Zahl. Legt die Größe (in Gigabyte für ganze Zahl oder einen Dezimalwert) für den gesamten Speicherplatz zugeordnet ist, replizierte Tabellen und die entsprechenden Daten *auf jedem Knoten Compute*. Für Minimum und Maximum *Replicated_size* Anforderungen, finden Sie unter "Minimale und Maximalwerte" in der [!INCLUDE[pdw-product-documentation](../../includes/pdw-product-documentation-md.md)].  
  
 Wenn automatische VERGRÖßERUNG aktiviert ist, werden replizierte Tabellen zulässig, die über diesen Grenzwert hinaus vergrößert.  
  
 Wenn automatische VERGRÖßERUNG auf OFF festgelegt ist, ein Fehler zurückgegeben, wenn ein Benutzer versucht, eine neue replizierte Tabelle erstellen, repliziert einfügen, Daten in einem vorhandenen repliziert-Tabelle ab, oder Aktualisieren einer vorhandenen, Tabelle in einer Weise, die die Größe erhöhen würde *Replicated_size*.  
  
 *distributed_size* [ GB ]  
 Eine positive Zahl. Die Größe in GB ganze Zahl oder einen Dezimalwert für den gesamten Speicherplatz zugeordnet ist, verteilte Tabellen (und die entsprechenden Daten) *über die Appliance*. Für Minimum und Maximum *Distributed_size* Anforderungen, finden Sie unter "Minimale und Maximalwerte" in der [!INCLUDE[pdw-product-documentation](../../includes/pdw-product-documentation-md.md)].  
  
 Wenn automatische VERGRÖßERUNG aktiviert ist, ist es verteilte Tabellen zulässig, die über diesen Grenzwert hinaus vergrößert.  
  
 Wenn die automatische VERGRÖßERUNG auf OFF festgelegt ist, wird ein Fehler zurückgegeben, wenn ein Benutzer versucht, eine neue verteilte Tabelle erstellen, Einfügen von Daten in einer vorhandenen distributed-Tabelle ab, oder aktualisieren eine vorhandene verteilte Tabelle in einer Weise, die die Größe erhöhen würde *Distributed_size* .  
  
 *log_size* [ GB ]  
 Eine positive Zahl. Die Größe (in Gigabyte für ganze Zahl oder einen Dezimalwert) für das Transaktionsprotokoll *über die Appliance*.  
  
 Für Minimum und Maximum *Log_size* Anforderungen, finden Sie unter "Minimale und Maximalwerte" in der [!INCLUDE[pdw-product-documentation](../../includes/pdw-product-documentation-md.md)].  
  
 Wenn automatische VERGRÖßERUNG aktiviert ist, ist die Protokolldatei zulässig, über diesen Grenzwert hinaus vergrößert. Verwenden der [DBCC SHRINKLOG (Azure SQL Data Warehouse)](../../t-sql/database-console-commands/dbcc-shrinklog-azure-sql-data-warehouse.md) Anweisung, um die Größe der Protokolldateien in ihrer ursprünglichen Größe zu verkleinern.  
  
 Wenn die automatische VERGRÖßERUNG auf OFF festgelegt ist, wird ein Fehler zurückgegeben an den Benutzer für alle Aktionen, die auf einem einzelnen Computeknoten außerhalb die Protokollgröße erhöhen würde *Log_size*.  
  
## <a name="permissions"></a>Berechtigungen  
 Erfordert die **CREATE ANY DATABASE** -Berechtigung für die master-Datenbank oder die Mitgliedschaft in der **Sysadmin** festen Serverrolle "".  
  
 Im folgenden Beispiel wird dem Datenbankbenutzer Fay die Berechtigung zum Erstellen einer Datenbank erteilt.  
  
```  
USE master;  
GO  
GRANT CREATE ANY DATABASE TO [Fay];  
GO  
```  
  
## <a name="general-remarks"></a>Allgemeine Hinweise  
 Datenbanken werden mit Datenbank-Kompatibilitätsgrad 120, also die Kompatibilität für Ebene erstellt [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]. Dadurch wird sichergestellt, dass die Datenbank wird in der Lage, alle verwenden die [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] Funktionalität, die PDW verwendet.  
  
## <a name="limitations-and-restrictions"></a>Einschränkungen  
 CREATE DATABASE-Anweisung ist in einer expliziten Transaktion nicht zulässig. Weitere Informationen finden Sie unter [Anweisungen](../../t-sql/statements/statements.md).  
  
 Informationen zu Einschränkungen von Mindest- und Höchstwerte für Datenbanken finden Sie unter "Minimale und Maximalwerte" in der [!INCLUDE[pdw-product-documentation](../../includes/pdw-product-documentation-md.md)].  
  
 Bei der Erstellung eine Datenbank ist, muss genügend freier Speicherplatz verfügbar *auf jedem Knoten Compute* zuweisen die kombinierte Summe der folgenden Größen:  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Bei Tabellen die Größe der Datenbank *Replicated_table_size*.  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Bei Tabellen die Größe der Datenbank (*Distributed_table_size* / Anzahl der Serverknoten).  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]die Größe der Protokolle (*Log_size* / Anzahl der Serverknoten).  
  
## <a name="locking"></a>Sperren  
 Akzeptiert eine gemeinsame Sperre für das Datenbankobjekt.  
  
## <a name="metadata"></a>Metadaten  
 Nachdem dieser Vorgang erfolgreich ist, einen Eintrag, für diese Datenbank angezeigt wird, in der [sys.databases &#40; Transact-SQL &#41; ](../../relational-databases/system-catalog-views/sys-databases-transact-sql.md) und [sys.objects &#40; Transact-SQL &#41; ](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md)Metadatenansichten.  
  
## <a name="examples-includesspdwincludessspdw-mdmd"></a>Beispiele:[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="a-basic-database-creation-examples"></a>A. Beispiele für die grundlegende Datenbank erstellen  
 Das folgende Beispiel erstellt die Datenbank `mytest` durch eine Zuweisung Speicher von 100 GB pro Serverknoten für replizierte Tabellen, 500 GB pro Einheit für verteilte Tabellen und 100 GB pro Einheit für das Transaktionsprotokoll. In diesem Beispiel ist standardmäßig automatische VERGRÖßERUNG deaktiviert.  
  
```  
CREATE DATABASE mytest  
   WITH   
   (REPLICATED_SIZE = 100 GB,  
   DISTRIBUTED_SIZE = 500 GB,  
   LOG_SIZE = 100 GB );  
```  
  
 Das folgende Beispiel erstellt die Datenbank `mytest` mit denselben Parametern wie oben beschrieben, mit Ausnahme von dieser automatische VERGRÖßERUNG aktiviert ist. Dadurch wird die Datenbank außerhalb der angegebenen Größenparameter vergrößert.  
  
```  
CREATE DATABASE mytest  
   WITH   
   (AUTOGROW = ON,  
   REPLICATED_SIZE = 100 GB,  
   DISTRIBUTED_SIZE = 500 GB,  
   LOG_SIZE = 100 GB);  
```  
  
### <a name="b-creating-a-database-with-partial-gigabyte-sizes"></a>B. Erstellen einer Datenbank mit der partiellen GB Größe  
 Das folgende Beispiel erstellt die Datenbank `mytest`, automatische VERGRÖßERUNG deaktiviert, eine Speicher-Zuweisung von 1,5 GB pro Serverknoten für replizierte Tabellen, 5,25 GB pro Einheit für verteilte Tabellen und 10 GB pro Einheit für das Transaktionsprotokoll.  
  
```  
CREATE DATABASE mytest  
   WITH   
   (REPLICATED_SIZE = 1.5 GB,  
   DISTRIBUTED_SIZE = 5.25 GB,  
   LOG_SIZE = 10 GB);  
```  
  
## <a name="see-also"></a>Siehe auch  
 [ALTER DATABASE &#40; Parallel Datawarehouse &#41;](../../t-sql/statements/alter-database-parallel-data-warehouse.md)   
 [DROP DATABASE &#40;Transact-SQL&#41;](../../t-sql/statements/drop-database-transact-sql.md)  
  
  
