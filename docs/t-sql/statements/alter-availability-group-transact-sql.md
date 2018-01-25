---
title: ALTER AVAILABILITY GROUP (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 01/02/2018
ms.prod: sql-non-specified
ms.prod_service: sql-database
ms.service: 
ms.component: t-sql|statements
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ALTER_AVAILABILITY_GROUP_TSQL
- ALTER_AVAILABILITY_TSQL
- ALTER AVAILABILITY GROUP
- ALTER AVAILABILITY
dev_langs: TSQL
helpviewer_keywords:
- Availability Groups [SQL Server], availability replicas
- ALTER AVAILABILITY GROUP statement
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], Transact-SQL statements
ms.assetid: f039d0de-ade7-4aaf-8b7b-d207deb3371a
caps.latest.revision: "152"
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: d9f18ee709fde7c9f239b08f553eaf43fad6e9d2
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="alter-availability-group-transact-sql"></a>ALTER AVAILABILITY GROUP (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Ändert eine vorhandene Always On-verfügbarkeitsgruppe in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Die meisten ALTER AVAILABILITY GROUP-Argumente werden nur von dem aktuellen primäre Replikat unterstützt. Die JOIN-, FAILOVER- und FORCE_FAILOVER_ALLOW_DATA_LOSS-Argumente werden hingegen nur auf sekundären Replikaten unterstützt.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```SQL  
  
ALTER AVAILABILITY GROUP group_name   
  {  
     SET ( <set_option_spec> )   
   | ADD DATABASE database_name   
   | REMOVE DATABASE database_name  
   | ADD REPLICA ON <add_replica_spec>   
   | MODIFY REPLICA ON <modify_replica_spec>  
   | REMOVE REPLICA ON <server_instance>  
   | JOIN  
   | JOIN AVAILABILITY GROUP ON <add_availability_group_spec> [ ,...2 ]  
   | MODIFY AVAILABILITY GROUP ON <modify_availability_group_spec> [ ,...2 ]  
   | GRANT CREATE ANY DATABASE  
   | DENY CREATE ANY DATABASE  
   | FAILOVER  
   | FORCE_FAILOVER_ALLOW_DATA_LOSS   | ADD LISTENER ‘dns_name’ ( <add_listener_option> )  
   | MODIFY LISTENER ‘dns_name’ ( <modify_listener_option> )  
   | RESTART LISTENER ‘dns_name’  
   | REMOVE LISTENER ‘dns_name’  
   | OFFLINE  
  }  
[ ; ]  
  
<set_option_spec> ::=   
    AUTOMATED_BACKUP_PREFERENCE = { PRIMARY | SECONDARY_ONLY| SECONDARY | NONE }  
  | FAILURE_CONDITION_LEVEL  = { 1 | 2 | 3 | 4 | 5 }   
  | HEALTH_CHECK_TIMEOUT = milliseconds  
  | DB_FAILOVER  = { ON | OFF }   
  | REQUIRED_SYNCHRONIZED_SECONDARIES_TO_COMMIT = { integer }
  
<server_instance> ::=   
 { 'system_name[\instance_name]' | 'FCI_network_name[\instance_name]' }  
  
<add_replica_spec>::=  
  <server_instance> WITH  
    (  
       ENDPOINT_URL = 'TCP://system-address:port',  
       AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT | CONFIGURATION_ONLY },  
       FAILOVER_MODE = { AUTOMATIC | MANUAL }   
       [ , <add_replica_option> [ ,...n ] ]  
    )   
  
  <add_replica_option>::=  
       SEEDING_MODE = { AUTOMATIC | MANUAL }   
     | BACKUP_PRIORITY = n  
     | SECONDARY_ROLE ( {   
          ALLOW_CONNECTIONS = { NO | READ_ONLY | ALL }   
        | READ_ONLY_ROUTING_URL = 'TCP://system-address:port'   
          } )  
     | PRIMARY_ROLE ( {   
          ALLOW_CONNECTIONS = { READ_WRITE | ALL }   
        | READ_ONLY_ROUTING_LIST = { ( ‘<server_instance>’ [ ,...n ] ) | NONE }   
          } )  
     | SESSION_TIMEOUT = seconds  
  
<modify_replica_spec>::=  
  <server_instance> WITH  
    (    
       ENDPOINT_URL = 'TCP://system-address:port'   
     | AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }   
     | FAILOVER_MODE = { AUTOMATIC | MANUAL }   
     | SEEDING_MODE = { AUTOMATIC | MANUAL }   
     | BACKUP_PRIORITY = n  
     | SECONDARY_ROLE ( {   
          ALLOW_CONNECTIONS = { NO | READ_ONLY | ALL }   
        | READ_ONLY_ROUTING_URL = 'TCP://system-address:port'   
          } )  
     | PRIMARY_ROLE ( {   
          ALLOW_CONNECTIONS = { READ_WRITE | ALL }   
        | READ_ONLY_ROUTING_LIST = { ( ‘<server_instance>’ [ ,...n ] ) | NONE }   
          } )  
     | SESSION_TIMEOUT = seconds  
    )   
  
<add_availability_group_spec>::=  
 <ag_name> WITH  
    (  
       LISTENER_URL = 'TCP://system-address:port',  
       AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT },  
       FAILOVER_MODE = MANUAL,  
       SEEDING_MODE = { AUTOMATIC | MANUAL }  
    )  
  
<modify_availability_group_spec>::=  
 <ag_name> WITH  
    (  
       LISTENER = 'TCP://system-address:port'  
       | AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }  
       | SEEDING_MODE = { AUTOMATIC | MANUAL }  
    )  
  
<add_listener_option> ::=  
   {  
      WITH DHCP [ ON ( <network_subnet_option> ) ]  
    | WITH IP ( { ( <ip_address_option> ) } [ , ...n ] ) [ , PORT = listener_port ]  
   }  
  
  <network_subnet_option> ::=  
     ‘four_part_ipv4_address’, ‘four_part_ipv4_mask’    
  
  <ip_address_option> ::=  
     {   
        ‘four_part_ipv4_address’, ‘four_part_ipv4_mask’  
      | ‘ipv6_address’  
     }  
  
<modify_listener_option>::=  
    {  
       ADD IP ( <ip_address_option> )   
     | PORT = listener_port  
    }  
  
```  
  
## <a name="arguments"></a>Argumente  
 *group_name*  
 Gibt den Namen der neuen Verfügbarkeitsgruppe an. *Gruppenname* muss ein gültiger [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Bezeichner, und er muss eindeutig sein in allen Verfügbarkeitsgruppen im WSFC-Cluster.  
  
 AUTOMATED_BACKUP_PREFERENCE  **=**  {PRIMÄREN | SECONDARY_ONLY | SEKUNDÄRE | KEINE}  
 Legt fest, wie ein Sicherungsauftrag das primäre Replikat auswerten soll, wenn ausgewählt wird, wo Sicherungen ausgeführt werden müssen. Sie können einen gegebenen Sicherungsauftrag erstellen, um die automatisierte Sicherungseinstellung zu berücksichtigen. Es ist wichtig zu verstehen, dass die Einstellung von nicht erzwungen wird [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], sodass er keine Auswirkungen auf ad-hoc-Sicherungen verfügt.  
  
 Wird nur für das primäre Replikat unterstützt.  
  
 Mit den Parametern werden folgende Werte angegeben:  
  
 PRIMARY  
 Gibt an, dass die Sicherungen immer auf dem primären Replikat erfolgen müssen. Diese Option ist hilfreich, wenn Sie Sicherungsfunktionen benötigen, z. B. das Erstellen differenzieller Sicherungen, die nicht unterstützt werden, wenn die Sicherung auf einem sekundären Replikat ausgeführt wird.  
  
> [!IMPORTANT]  
>  Wenn Sie den Protokollversand verwenden möchten, um sekundäre Datenbanken auf eine Verfügbarkeitsgruppe vorzubereiten, legen Sie die Voreinstellung für automatisierte Sicherungen auf **Primär** fest, bis alle sekundären Datenbanken vorbereitet und mit der Verfügbarkeitsgruppe verknüpft worden sind.  
  
 SECONDARY_ONLY  
 Gibt an, dass Sicherungen nie auf dem primären Replikat ausgeführt werden dürfen. Wenn es sich beim primären Replikat um das einzige Onlinereplikat handelt, darf keine Sicherung erfolgen.  
  
 SECONDARY  
 Gibt an, dass Sicherungen auf einem sekundären Replikat erfolgen müssen, außer wenn es sich beim primären Replikat um das einzige Onlinereplikat handelt. In diesem Fall muss die Sicherung auf dem primären Replikat erfolgen. Dies ist das Standardverhalten.  
  
 Keine  
 Gibt an, dass Sicherungsaufträge die Rolle der Verfügbarkeitsreplikate ignorieren sollen, wenn sie das Replikat zum Durchführen der Sicherungen auswählen. Hinweis: Sicherungsaufträge können andere Faktoren auswerten, wie z. B. die Sicherungspriorität jedes Verfügbarkeitsreplikats in Verbindung mit seinem Betriebszustand und Verbindungsstatus.  
  
> [!IMPORTANT]  
>  Die Einstellung AUTOMATED_BACKUP_PREFERENCE wird nicht erzwungen. Die Interpretation dieser Einstellung hängt von der Logik ab, die Sie ggf. per Skript in Sicherungsaufträge für die Datenbanken in einer angegebenen Verfügbarkeitsgruppe integriert haben. Die Voreinstellung für automatisierte Sicherung hat keine Auswirkungen auf ad-hoc-Sicherungen. Weitere Informationen finden Sie unter [Konfigurieren der Sicherung auf Verfügbarkeitsreplikaten &#40; SQLServer &#41; ](../../database-engine/availability-groups/windows/configure-backup-on-availability-replicas-sql-server.md).  
  
> [!NOTE]  
>  Um die automatisierte sicherungseinstellung einer vorhandenen verfügbarkeitsgruppe anzuzeigen, wählen Sie die **Automated_backup_preference** oder **Automated_backup_preference_desc** Spalte die [ availability_groups](../../relational-databases/system-catalog-views/sys-availability-groups-transact-sql.md) -Katalogsicht angezeigt. Darüber hinaus [Sys. fn_hadr_backup_is_preferred_replica &#40; Transact-SQL &#41; ](../../relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql.md) können verwendet werden, um das bevorzugte sicherungsreplikat zu bestimmen.  Diese Funktion gibt immer 1 für mindestens eines der Replikate zurück, sogar wenn `AUTOMATED_BACKUP_PREFERENCE = NONE` ist.  
  
 FAILURE_CONDITION_LEVEL  **=**  {1 | 2 | **3** | 4 | 5}  
 Gibt an, welche Fehlerbedingungen ein automatisches Failover für diese Verfügbarkeitsgruppe auslösen. FAILURE_CONDITION_LEVEL wird auf Gruppenebene festgelegt, aber spielt nur auf verfügbarkeitsreplikaten, die für den Verfügbarkeitsmodus für synchrone Commits konfiguriert sind (AVAILIBILITY_MODE  **=**  SYNCHRONOUS_COMMIT). Weiterhin können fehlerbedingungen ein automatisches Failover auslösen, nur dann, wenn die primären und sekundären Replikate für den automatischen Failovermodus konfiguriert sind (FAILOVER_MODE  **=**  automatische) und das sekundäre Replikat ist. derzeit synchronisiert mit dem primären Replikat.  
  
 Wird nur für das primäre Replikat unterstützt.  
  
 Die Fehlerbedingungsebenen (1-5) reichen von der Ebene 1 mit den wenigsten Einschränkungen bis zur Ebene 5 mit den meisten Einschränkungen. Jede Bedingungsebene umfasst stets auch sämtliche weniger restriktiven Ebenen. Daher schließt die strengste Bedingungsebene 5 die vier Bedingungsebenen mit weniger Einschränkungen (1-4) ein, Ebene 4 schließt die Ebenen 1-3 ein usw. In der folgenden Tabelle wird die Fehlerbedingung beschrieben, die der jeweiligen Ebene entspricht.  
  
|Ebene|Fehlerbedingung|  
|-----------|-----------------------|  
|1|Gibt an, dass in einem der folgenden Fälle ein automatisches Failover initiiert werden muss:<br /><br /> Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienst ist ausgefallen.<br /><br /> Das Leasing der Verfügbarkeitsgruppe für die Verbindung mit dem WSFC-Cluster läuft ab, da keine ACK-Meldung von der Serverinstanz empfangen wird. Weitere Informationen finden Sie unter [How It Works: SQL Server AlwaysOn Lease Timeout](http://blogs.msdn.com/b/psssql/archive/2012/09/07/how-it-works-sql-server-Always%20On-lease-timeout.aspx).|  
|2|Gibt an, dass in einem der folgenden Fälle ein automatisches Failover initiiert werden muss:<br /><br /> Die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stellt keine Verbindung mit dem Cluster her, und der vom Benutzer angegebene HEALTH_CHECK_TIMEOUT-Schwellenwert der Verfügbarkeitsgruppe wurde überschritten.<br /><br /> Das Verfügbarkeitsreplikat weist einen fehlerhaften Status auf.|  
|3|Gibt an, dass ein automatisches Failover bei kritischen internen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlern initiiert werden soll, z. B. verwaisten Spinlocks, schwerwiegenden Schreibzugriffsverletzungen oder zu vielen Sicherungen.<br /><br /> Dies ist das Standardverhalten.|  
|4|Gibt an, dass ein automatisches Failover bei mittelschweren internen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlern initiiert werden soll, z. B. bei dauerhaft unzureichendem Arbeitsspeicher im internen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Ressourcenpool.|  
|5|Gibt an, dass ein automatisches Failover bei sämtlichen qualifizierten Fehlerbedingungen initiiert werden soll, einschließlich:<br /><br /> Erschöpfung der SQL Engine-Arbeitsthreads.<br /><br /> Erkennung eines unlösbaren Deadlocks.|  
  
> [!NOTE]  
>  Fehlen einer Reaktion von einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client Anforderungen ist nicht relevant für Verfügbarkeitsgruppen.  
  
 Der FAILURE_CONDITION_LEVEL- und der HEALTH_CHECK_TIMEOUT-Wert definieren eine *flexible Failoverrichtlinie für* für eine bestimmte Gruppe. Diese flexible Failoverrichtlinie bietet eine präzise Kontrolle der Bedingungen, die ein automatisches Failover verursachen müssen. Weitere Informationen finden Sie unter [Flexible Failoverrichtlinie für automatisches Failover einer Verfügbarkeitsgruppe &#40; SQLServer &#41; ](../../database-engine/availability-groups/windows/flexible-automatic-failover-policy-availability-group.md).  
  
 HEALTH_CHECK_TIMEOUT  **=**  *Millisekunden*  
 Gibt die Wartezeit (in Millisekunden) für die [Sp_server_diagnostics](../../relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql.md) gespeicherte Systemprozedur Serverzustand Informationen zurückgegeben werden sollen, bevor der wsfc-Cluster wird davon ausgegangen, dass die Serverinstanz langsam oder blockiert ist. HEALTH_CHECK_TIMEOUT wird auf Gruppenebene festgelegt, aber spielt nur auf verfügbarkeitsreplikaten, die für den Verfügbarkeitsmodus für synchrone Commits mit automatischem Failover konfiguriert sind (AVAILIBILITY_MODE  **=**  SYNCHRONE _COMMIT).  Darüber hinaus kann ein integritätsprüfungstimeout ein automatisches Failover auslösen, nur dann, wenn die primären und sekundären Replikate für den automatischen Failovermodus konfiguriert sind (FAILOVER_MODE  **=**  automatische) und der sekundären Datenbank Replikat ist derzeit mit dem primären Replikat synchronisiert.  
  
 Der standardmäßige HEALTH_CHECK_TIMEOUT-Wert beträgt 30.000 Millisekunden (30 Sekunden). Der minimale Wert beträgt 15.000 Millisekunden (15 Sekunden) und der maximale Wert 4.294.967.295 Millisekunden.  
  
 Wird nur für das primäre Replikat unterstützt.  
  
> [!IMPORTANT]  
>  **sp_server_diagnostics** führt keine Integritätsprüfungen auf Datenbankebene aus.  
  
 DB_FAILOVER  **=** { ON | OFF }  
 Gibt die Antwort an, die bei eine Datenbank auf dem primären Replikat offline ist. Alle Status außer ONLINE für eine Datenbank in der verfügbarkeitsgruppe auf ON festgelegt, wird ein automatisches Failover ausgelöst. Wenn diese Option auf OFF festgelegt ist, wird nur die Integrität der Instanz verwendet, auf Automatisches Failover auslösen.  
 
 Weitere Informationen zu dieser Einstellung finden Sie unter [Datenbankoption für die Erkennung von Ebene Integrität](../../database-engine/availability-groups/windows/sql-server-always-on-database-health-detection-failover-option.md) 

 
 REQUIRED_SYNCHRONIZED_SECONDARIES_TO_COMMIT   
 In SQLServer 2017 eingeführt. Dient zum Festlegen einer minimalen Anzahl von synchrone sekundäre Replikate erforderlich, um einen Commit auszuführen, bevor die primäre eine Transaktion ein Commit ausgeführt wird. Stellt sicher, dass SQL Server-Transaktionen wartet, bis die Transaktionsprotokolle für die minimale Anzahl von sekundären Replikaten aktualisiert werden. Der Standardwert ist 0. das gleiche Verhalten wie SQL Server 2016 bietet. Der minimale Wert ist 0. Der maximale Wert ist die Anzahl der Replikate minus 1. Diese Option bezieht sich auf die Replikate im synchronen Commit-Modus. Wenn Replikate im synchronen Commit-Modus befinden, Schreibvorgänge auf dem primären Replikat warten, bis der Schreibvorgänge auf den sekundären Replikaten für synchrone Commit im Transaktionsprotokoll der Replikat-Datenbank. Wenn eine SQL-Server, die ein synchrone sekundäre Replikat hostet, nicht mehr reagiert, wird SQL Server, der das primäre Replikat hostet dieses sekundäre Replikat als nicht synchronisiert, und fahren Sie fort markieren. Bei nicht reagierende Datenbank wieder online geschaltet wird es befindet sich in einem Zustand "nicht synchronisiert", und das Replikat wird als "fehlerhaft" markiert werden, bis das primäre synchronen Vorgang erleichtern kann. Diese Einstellung wird sichergestellt, dass das primäre Replikat wird nicht fortgesetzt, bis die minimale Anzahl der Replikate für jede Transaktion ein Commit ausgeführt wurde. Wenn die minimale Anzahl der Replikate nicht verfügbar ist, schlägt Commits auf dem primären fehl. Für Clustertyp `EXTERNAL` die Einstellung geändert wird, wenn die Clusterressource die verfügbarkeitsgruppe hinzugefügt wird. Finden Sie unter [hohe Verfügbarkeit und Datenschutz für verfügbarkeitsgruppenkonfigurationen](../../linux/sql-server-linux-availability-group-ha.md).
  
 Hinzufügen von Datenbanken *Database_name*  
 Gibt eine Liste von Benutzerdatenbanken an, die Sie der Verfügbarkeitsgruppe hinzufügen möchten. Diese Datenbanken müssen sich auf der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] befinden, die das aktuelle primäre Replikat hostet. Sie können mehrere Datenbanken für eine Verfügbarkeitsgruppe angeben, aber jede Datenbank kann nur zu einer Verfügbarkeitsgruppe gehören. Weitere Informationen zu den Typ von Datenbanken, die eine verfügbarkeitsgruppe unterstützt werden, finden Sie unter [Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen &#40; SQLServer &#41; ](../../database-engine/availability-groups/windows/prereqs-restrictions-recommendations-always-on-availability.md). Um herauszufinden, welche lokalen Datenbanken bereits zu einer verfügbarkeitsgruppe gehören, finden Sie unter der **Replica_id** Spalte in der [sys.databases](../../relational-databases/system-catalog-views/sys-databases-transact-sql.md) -Katalogsicht angezeigt.  
  
 Wird nur für das primäre Replikat unterstützt.  
  
> [!NOTE]  
>  Nachdem Sie eine Verfügbarkeitsgruppe erstellt haben, müssen Sie wiederum eine Verbindung zu jeder Serverinstanz herstellen, die ein sekundäres Replikat hostet, und anschließend jede sekundäre Datenbank vorbereiten und mit der Verfügbarkeitsgruppe verknüpfen. Weitere Informationen finden Sie weiter unten in diesem Thema im Abschnitt [Starten der Datenverschiebung auf einer sekundären Always On-Datenbank &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/start-data-movement-on-an-always-on-secondary-database-sql-server.md).  
  
 "Datenbank entfernen" *Database_name*  
 Entfernt die angegebene primäre Datenbank und die entsprechenden sekundären Datenbanken aus der Verfügbarkeitsgruppe. Wird nur für das primäre Replikat unterstützt.  
  
 Informationen zu den empfohlenen Schritten nach dem Entfernen einer verfügbarkeitsdatenbank aus einer verfügbarkeitsgruppe finden Sie unter [Entfernen einer Primärdatenbank aus einer Verfügbarkeitsgruppe &#40; SQLServer &#41; ](../../database-engine/availability-groups/windows/remove-a-primary-database-from-an-availability-group-sql-server.md).  
  
 ADD REPLICA ON  
 Gibt eine bis acht SQL Server-Instanzen an, in denen sekundäre Replikate in einer Verfügbarkeitsgruppe gehostet werden sollen.  Jedes Replikat wird von seiner Serverinstanzadresse gefolgt von einer WITH (…)-Klausel angegeben.  
  
 Wird nur für das primäre Replikat unterstützt.  
  
 Sie müssen jedes neue sekundäre Replikat mit der Verfügbarkeitsgruppe verknüpfen. Weitere Informationen finden Sie in der Beschreibung der JOIN-Option weiter unten in diesem Abschnitt.  
  
 \<server_instance>  
 Gibt die Adresse der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die als Host für ein Replikat. Das Adressformat hängt davon ab, ob die Instanz die Standardinstanz oder eine benannte Instanz ist und ob es eine eigenständige Instanz oder eine Failoverclusterinstanz (FCI) ist. Die Syntax lautet wie folgt:  
  
 { '*system_name*[\\*instance_name*]' | '*FCI_network_name*[\\*instance_name*]' }  
  
 Diese Adresse weist die folgenden Komponenten auf:  
  
 *system_name*  
 Der NetBIOS-Name des Computersystems, auf dem sich eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Zielinstanz befindet. Dieser Computer muss ein WSFC-Knoten sein.  
  
 *FCI_network_name*  
 Ist der Netzwerkname, der verwendet wird, um auf einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Failovercluster zuzugreifen. Verwenden Sie diesen Namen, wenn die Serverinstanz als [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Failoverpartner beteiligt ist. Zur Ausführung von SELECT- [@@SERVERNAME ](../../t-sql/functions/servername-transact-sql.md) auf einer FCI-Serverinstanz gibt die gesamte '*FCI_network_name*[\\*Instance_name*]' Zeichenfolge (also die vollständigen replikatnamen).  
  
 *instance_name*  
 Der Name einer Instanz von einem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gehostet wird *System_name* oder *FCI_network_name* und Always On aktiviert. Bei einer Standardserverinstanz ist *instance_name* optional. Bei dem Instanznamen wird die Groß-/Kleinschreibung berücksichtigt. Auf einer eigenständigen Serverinstanz Name dieses Werts ist identisch mit den Rückgabewert von zur Ausführung von SELECT- [@@SERVERNAME](../../t-sql/functions/servername-transact-sql.md).  
  
 \  
 Ein Trennzeichen verwendet werden, nur bei der Angabe *Instance_name*, um sie über separate *System_name* oder *FCI_network_name*.  
  
 Informationen zu den erforderlichen Komponenten für wsfc-Knoten und Serverinstanzen finden Sie unter [Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen &#40; SQLServer &#41; ](../../database-engine/availability-groups/windows/prereqs-restrictions-recommendations-always-on-availability.md).  
  
 ENDPOINT_URL = "TCP: / /*Systemadresse*:*Port*"  
 Gibt den URL-Pfad für die [datenbankspiegelungsendpunkt](../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md) für die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die das verfügbarkeitsreplikat, das Sie hinzufügen oder Ändern von hostet.  
  
 ENDPOINT_URL ist in der ADD REPLICA ON-Klausel erforderlich und in der MODIFY REPLICA ON-Klausel optional.  Weitere Informationen finden Sie unter [Angeben der Endpunkt-URL beim Hinzufügen oder Ändern eines Verfügbarkeitsreplikats &#40; SQLServer &#41;](../../database-engine/availability-groups/windows/specify-endpoint-url-adding-or-modifying-availability-replica.md)zu unterstützen.  
  
 **"**TCP**://***Systemadresse***:***Port***"**  
 Gibt eine URL zum Bestimmen einer Endpunkt-URL oder einer URL für das schreibgeschützte Routing an. Die URL-Parameter lauten wie folgt:  
  
 *system-address*  
 Ist eine Zeichenfolge, beispielsweise ein Systemname, ein vollqualifizierter Domänenname oder eine IP-Adresse, die das Zielcomputersystem eindeutig identifiziert.  
  
 *port*  
 Ist eine Portnummer, die dem Spiegelungsendpunkt der Serverinstanz (für die ENDPOINT_URL-Option) oder der Portnummer, die von [!INCLUDE[ssDE](../../includes/ssde-md.md)] der Serverinstanz (für die READ_ONLY_ROUTING_URL-Option) verwendet wird, zugeordnet ist.  
  
 AVAILABILITY_MODE  **=**  {SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT | CONFIGURATION_ONLY}  
 Gibt an, ob das primäre Replikat auf das sekundäre Replikat warten muss, um das Verstärken (Schreiben) der Protokolldatensätze auf einem Datenträger zu bestätigen, bevor das primäre Replikat die Transaktion auf einer bestimmten primären Datenbank ausführen kann. Die Transaktionen auf anderen Datenbanken über dasselbe primäre Replikat können unabhängig einen Commit ausführen.  
  
 SYNCHRONOUS_COMMIT  
 Gibt an, dass das primäre Replikat mit der Ausführung von Transaktionen wartet, bis sie auf diesem sekundären Replikat (Modus mit synchronem Commit) verstärkt wurden. Sie können SYNCHRONOUS_COMMIT für bis zu drei Replikate angeben, einschließlich des primären Replikats.  
  
 ASYNCHRONOUS_COMMIT  
 Gibt an, dass das primäre Replikat einen Commit für Transaktionen ausführt, ohne zu warten, bis dieses sekundäre Replikat das Protokoll verstärkt (Verfügbarkeitsmodus mit synchronem Commit). Sie können ASYNCHRONOUS_COMMIT für bis zu fünf Verfügbarkeitsreplikate angeben, einschließlich des primären Replikats.  

 CONFIGURATION_ONLY gibt an, dass das primäre Replikat synchron verfügbarkeitsgruppenmetadaten Konfiguration mit der master-Datenbank auf diesem Replikat einen Commit auszuführen. Das Replikat enthält keine Benutzerdaten. Diese Option:

- Kann auf eine beliebige Edition von SQL Server Express Edition einschließlich gehostet werden.
- Müssen die Daten mit dem datenbankspiegelungs-Endpunkt des Replikats CONFIGURATION_ONLY Typ `WITNESS`.
- Kann nicht geändert werden.
- Ist nicht gültig, wenn `CLUSTER_TYPE = WSFC`. 

   Weitere Informationen finden Sie unter [Konfiguration nur Replikat](../../linux/sql-server-linux-availability-group-ha.md).
    
 AVAILABILITY_MODE ist in der ADD REPLICA ON-Klausel erforderlich und in der MODIFY REPLICA ON-Klausel optional. Weitere Informationen finden Sie unter [Verfügbarkeitsmodi &#40;Always On-Verfügbarkeitsgruppen&#41;](../../database-engine/availability-groups/windows/availability-modes-always-on-availability-groups.md)ausgetauscht werden.  
  
 FAILOVER_MODE  **=**  {AUTOMATISCHE | MANUELLE}  
 Gibt den Failovermodus des Verfügbarkeitsreplikats an, das Sie definieren.  
  
 AUTOMATIC  
 Aktiviert das automatische Failover. AUTOMATIC wird nur unterstützt, wenn Sie auch AVAILABILITY_MODE = SYNCHRONOUS_COMMIT angeben. Sie können AUTOMATIC für zwei Verfügbarkeitsreplikate angeben, einschließlich des primären Replikats.  
  
> [!NOTE]  
>  SQL Server-Failoverclusterinstanzen (FCIs) unterstützen kein automatisches Failover durch Verfügbarkeitsgruppen. Daher können die Verfügbarkeitsreplikate, die von einer FCI gehostet werden, nur für manuelles Failover konfiguriert werden.  
  
 MANUAL  
 Ermöglicht manuelles Failover oder erzwungenes Manuelles Failover (*erzwungenes Failover*) durch den Datenbankadministrator.  
  
 FAILOVER_MODE ist in der ADD REPLICA ON-Klausel erforderlich und in der MODIFY REPLICA ON-Klausel optional. Zwei Typen manuellen Failovers sind vorhanden, manuelles Failover ohne Datenverlust und erzwungenes Failover (mit möglichem Datenverlust), die unter anderen Bedingungen unterstützt werden.  Weitere Informationen finden Sie weiter unten in diesem Thema unter [Failover und Failovermodi &#40;Always On-Verfügbarkeitsgruppen&#41;](../../database-engine/availability-groups/windows/failover-and-failover-modes-always-on-availability-groups.md).  
  
 SEEDING_MODE  **=**  {AUTOMATISCHE | MANUELLE}  
 Gibt an, wie das sekundäre Replikat ursprünglich ausgeführt werden.  
  
 AUTOMATIC  
 Ermöglicht direkte seeding. Diese Methode wird das sekundäre Replikat über das Netzwerk Ausgangswert. Diese Methode erfordert nicht das Sichern und Wiederherstellen einer Kopie der primären Datenbank auf dem Replikat.  
  
> [!NOTE]  
>  Für das direkte seeding, müssen Sie das Erstellen einer Datenbank auf jedem sekundären Replikat zulassen, durch den Aufruf **ALTER AVAILABILITY GROUP** mit der **GRANT CREATE ANY DATABASE** Option.  
  
 MANUAL  
 Gibt an, manuelle seeding (Standard). Diese Methode erfordert, dass Sie eine Sicherung der Datenbank auf dem primären Replikat zu erstellen und diese Sicherung auf dem sekundären Replikat manuell wiederherstellen.  
  
 BACKUP_PRIORITY **=***n*  
 Gibt die Priorität für die Ausführung von Sicherungen auf diesem Replikat in Relation zu den anderen Replikaten in derselben Verfügbarkeitsgruppe an. Der Wert liegt im Bereich von 0 bis 100 und ist eine ganze Zahl. Diese Werte haben die folgenden Bedeutungen:  
  
-   1..100 gibt an, dass das Verfügbarkeitsreplikat zum Ausführen von Sicherungen ausgewählt werden könnte. 1 gibt die niedrigste Priorität und 100 die höchste Priorität an. Wenn BACKUP_PRIORITY = 1, würde das Verfügbarkeitsreplikat nur zum Ausführungen von Sicherungen ausgewählt werden, wenn gerade keine höheren Prioritätsverfügbarkeitsreplikate verfügbar sind.  
  
-   0 gibt an, dass dieses Verfügbarkeitsreplikat nie zum Ausführen von Sicherungen ausgewählt wird. Dies ist zum Beispiel für ein Remoteverfügbarkeitsreplikat hilfreich, für das keine Failover bei Sicherungen auftreten sollen.  
  
 Weitere Informationen finden Sie unter [Aktive sekundäre Replikate: Sicherung auf sekundären Replikaten &#40;Always On-Verfügbarkeitsgruppen&#41;](../../database-engine/availability-groups/windows/active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md)wichtig sind.  
  
 SECONDARY_ROLE **(** ... **)**  
 Gibt rollenspezifische Einstellungen an, die wirksam werden, wenn dieses Verfügbarkeitsreplikat die sekundäre Rolle (d. h. wenn es gerade ein sekundäres Replikat ist) gerade besitzt. Geben Sie innerhalb der Klammern eine oder beide sekundäre Rollenoptionen an. Wenn Sie beide angeben, verwenden Sie eine durch Trennzeichen getrennte Liste.  
  
 Folgende Optionen stehen für die sekundäre Rolle zur Verfügung:  
  
 ALLOW_CONNECTIONS  **=**  {NEIN | READ_ONLY | ALLE}  
 Gibt an, ob die Datenbanken eines bestimmten Verfügbarkeitsreplikats, das die sekundäre Rolle einnimmt (das heißt, als sekundäres Replikat dient), Verbindungen von Clients akzeptieren können, z. B.:  
  
 NO  
 Es werden keine Verbindungen mit sekundären Datenbanken dieses Replikats zugelassen. Sie sind für den Lesezugriff nicht verfügbar. Dies ist das Standardverhalten.  
  
 READ_ONLY  
 Nur Verbindungen mit den Datenbanken im sekundären Replikat, die die Anwendungsabsicht-Eigenschaft auf festgelegt ist, zulässig sind **ReadOnly**. Weitere Informationen zu dieser Eigenschaft finden Sie unter [Using Connection String Keywords with SQL Server Native Client](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).  
  
 ALL  
 Für alle Verbindungen mit den Datenbanken im sekundären Replikat ist der schreibgeschützte Zugriff zugelassen.  
  
 Weitere Informationen finden Sie unter [Aktive sekundäre Replikate: Lesbare sekundäre Replikate &#40;Always On-Verfügbarkeitsgruppen&#41;](../../database-engine/availability-groups/windows/active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)wichtig sind.  
  
 READ_ONLY_ROUTING_URL **= "**TCP**://***Systemadresse***:***Port***"**  
 Gibt die URL an, die zum Weiterleiten von Verbindungsanforderungen für beabsichtigte Lesevorgänge zu diesem Verfügbarkeitsreplikat verwendet werden soll. Dies ist die URL, die das SQL Server-Datenbankmodul überwacht. In der Regel überwacht die Standardinstanz des SQL Server-Datenbankmoduls auf TCP-Port 1433.  
  
 Für eine benannte Instanz verwenden, erhalten Sie die Portnummer durch Abfragen der **Port** und **Type_desc** Spalten von der [dm_tcp_listener_states](../../relational-databases/system-dynamic-management-views/sys-dm-tcp-listener-states-transact-sql.md) -verwaltungssicht. Die Serverinstanz verwendet den Transact-SQL-Listener (**Type_desc = "TSQL"**).  
  
 Weitere Informationen zum Berechnen der schreibgeschützten routing-URL für ein verfügbarkeitsreplikat finden Sie unter [berechnen von Read_only_routing_url für AlwaysOn-](http://blogs.msdn.com/b/mattn/archive/2012/04/25/calculating-read-only-routing-url-for-Always%20On.aspx).  
  
> [!NOTE]  
>  Für eine benannte Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sollte der Transact-SQL-Listener konfiguriert werden, um einen bestimmten Port zu verwenden. Weitere Informationen finden Sie unter [Konfigurieren eines Servers zur Überwachung eines bestimmten TCP-Ports &#40;SQL Server-Konfigurations-Manager&#41;](../../database-engine/configure-windows/configure-a-server-to-listen-on-a-specific-tcp-port.md).  
  
 PRIMARY_ROLE **(** ... **)**  
 Gibt rollenspezifische Einstellungen an, die wirksam werden, wenn dieses Verfügbarkeitsreplikat die primäre Rolle (d. h. wenn es gerade ein primäres Replikat ist) gerade besitzt. Geben Sie innerhalb der Klammern eine oder beide primäre Rollenoptionen an. Wenn Sie beide angeben, verwenden Sie eine durch Trennzeichen getrennte Liste.  
  
 Folgende Optionen stehen für die primäre Rolle zur Verfügung:  
  
 ALLOW_CONNECTIONS  **=**  {READ_WRITE | ALLE}  
 Gibt den Verbindungstyp an, den die Datenbanken eines bestimmten Verfügbarkeitsreplikats, das die primäre Rolle einnimmt (das heißt, als primäres Replikat dient), von Clients akzeptieren können, z. B.:  
  
 READ_WRITE  
 Verbindungen, bei denen die Verbindungseigenschaft für die Anwendungsabsicht auf **ReadOnly** festgelegt ist, werden nicht zugelassen.  Wenn die Eigenschaft für die Anwendungsabsicht auf **ReadWrite** festgelegt ist oder keine Verbindungseigenschaft für die Anwendungsabsicht festgelegt wurde, wird die Verbindung zugelassen. Weitere Informationen zur Verbindungseigenschaft für die Anwendungsabsicht finden Sie unter [Using Connection String Keywords with SQL Server Native Client](../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).  
  
 ALL  
 Für die Datenbanken im primären Replikat sind alle Verbindungen zugelassen. Dies ist das Standardverhalten.  
  
 READ_ONLY_ROUTING_LIST **=** { **(‘**\<server_instance>**’** [ **,**...*n* ] **)** | NONE }  
 Gibt beim Ausführen unter der sekundären Rolle eine durch Trennzeichen getrennte Liste von Serverinstanzen an, die Verfügbarkeitsreplikate für diese Verfügbarkeitsgruppe hosten, die die folgenden Anforderungen erfüllt:  
  
-   Wird konfiguriert, um alle Verbindungen oder schreibgeschützte Verbindungen (siehe das obige ALLOW_CONNECTIONS-Argument der SECONDARY_ROLE-Option) zuzulassen.  
  
-   Die schreibgeschützte Routing-URL wurde definiert (siehe das obige READ_ONLY_ROUTING_URL-Argument der SECONDARY_ROLE-Option).  
  
 Die READ_ONLY_ROUTING_LIST-Werte lauten wie folgt:  
  
 \<server_instance>  
 Gibt die Adresse der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] an, die als Host für ein Verfügbarkeitsreplikat fungiert, das ein lesbares sekundäres Replikat ist, wenn es unter der sekundären Rolle ausgeführt wird.  
  
 Verwenden Sie eine durch Trennzeichen getrennte Liste, um alle der Serverinstanzen anzugeben, die ein lesbares sekundäres Replikat hosten könnten. Schreibgeschütztes Routing erfolgt in der Reihenfolge, in der Serverinstanzen in der Liste angegeben werden. Wenn Sie die Hostserverinstanz eines Replikats auf der schreibgeschützten Routingliste des Replikats einschließen, ist es eine empfohlene Vorgehensweise, diese Serverinstanz am Ende der Liste zu platzieren, damit Verbindungen für beabsichtigte Lesevorgänge bei Verfügbarkeit zu einem sekundären Replikat wechseln.  
  
 Beginnend mit [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)], können Sie die Anforderungen für den Lastenausgleich mit leseabsicht über lesbare sekundäre Replikate. Dies können Sie angeben, indem Sie die Replikate in einer geschachtelten Klammern innerhalb der schreibgeschützten Routingliste platzieren. Weitere Informationen und Beispiele finden Sie unter [Konfigurieren von Lastenausgleich über schreibgeschützte Replikate hinweg](../../database-engine/availability-groups/windows/configure-read-only-routing-for-an-availability-group-sql-server.md#loadbalancing).  
  
 Keine  
 Gibt an, dass, wenn dieses Verfügbarkeitsreplikat das primäre Replikat ist, schreibgeschütztes Routing nicht unterstützt wird. Dies ist das Standardverhalten. Wenn dieser Wert zusammen mit MODIFY REPLICA ON verwendet wird, aktiviert er ggf. die vorhandene Liste.  
  
 SESSION_TIMEOUT **= *** Sekunden*  
 Gibt den Zeitraum für das Sitzungstimeout in Sekunden an. Wenn Sie die Option nicht angeben, beträgt der Timeoutzeitraum standardmäßig 10 Sekunden. Der Wert muss mindestens 5 Sekunden betragen.  
  
> [!IMPORTANT]  
>  Es wird empfohlen, einen Timeoutzeitraum von 10 Sekunden oder mehr zu wählen.  
  
 Weitere Informationen über die Sitzungstimeout finden Sie unter [(Übersicht) der AlwaysOn-Verfügbarkeitsgruppen &#40; SQLServer &#41; ](../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md).  
  
 MODIFY REPLICA ON  
 Ändert ein beliebiges Replikat der Verfügbarkeitsgruppe. Die Liste der zu ändernden Replikate enthält die Serverinstanzadresse und eine WITH (...)-Klausel für jedes Replikat.  
  
 Wird nur für das primäre Replikat unterstützt.  
  
 REMOVE REPLICA ON  
 Entfernt das angegebene sekundäre Replikat aus der Verfügbarkeitsgruppe. Das aktuelle primäre Replikat kann nicht aus einer Verfügbarkeitsgruppe entfernt werden. Das Replikat empfängt keine Daten mehr, wenn es entfernt wird. Seine sekundären Datenbanken werden aus der Verfügbarkeitsgruppe entfernt und nehmen den Status RESTORING an.  
  
 Wird nur für das primäre Replikat unterstützt.  
  
> [!NOTE]  
>  Wenn Sie ein Replikat im nicht verfügbaren oder fehlerhaften Status entfernen, erkennt es, dass es nicht mehr zur Verfügbarkeitsgruppe gehört, wenn es wieder online ist.  
  
 JOIN  
 Bewirkt, dass die lokale Serverinstanz ein sekundäres Replikat in der angegebenen Verfügbarkeitsgruppe hostet.  
  
 Wird nur für ein sekundäres Replikat unterstützt, das der Verfügbarkeitsgruppe noch nicht hinzugefügt wurde.  
  
 Weitere Informationen finden Sie unter [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/join-a-secondary-replica-to-an-availability-group-sql-server.md)verwendet werden.  
  
 FAILOVER  
 Initiiert ein manuelles Failover der Verfügbarkeitsgruppe ohne Datenverlust an das sekundäre Replikat, mit dem Sie verbunden sind. Das Replikat auf dem Sie einen failoverzielbefehl eingeben, wird als bezeichnet den.  Das Failoverziel übernimmt die primäre Rolle und stellt seine Kopie jeder Datenbank wieder her und schaltet sie als neue primäre Datenbanken online. Das frühere primäre Replikat geht gleichzeitig in die sekundäre Rolle über, und seine Datenbanken werden sekundäre Datenbanken und werden sofort angehalten. Zwischen diesen Rollen kann möglicherweise durch eine Reihe von Fehlern hin- und hergeschaltet werden.  
  
 Wird nur auf einem sekundären Replikat mit synchronem Commit unterstützt, das derzeit mit dem primären Replikat synchronisiert ist. Hinweis: Damit das sekundäre Replikat synchronisiert werden kann, muss das primäre Replikat ebenfalls im Modus mit synchronem Commit ausgeführt werden.  
  
> [!NOTE]  
>  Ein Failoverbefehl gibt einen Wert zurück, sobald das Failoverziel den Befehl akzeptiert hat. Die Datenbankwiederherstellung tritt jedoch asynchron auf, nachdem die Verfügbarkeitsgruppe aufgehört hat, ein Failover auszuführen.  
  
 Informationen zu den Einschränkungen, Voraussetzungen und Empfehlungen zum Ausführen eines geplanten manuellen Failovers finden Sie unter [Ausführen eines geplanten manuellen Failovers einer Verfügbarkeitsgruppe &#40; SQLServer &#41; ](../../database-engine/availability-groups/windows/perform-a-planned-manual-failover-of-an-availability-group-sql-server.md).  
  
 FORCE_FAILOVER_ALLOW_DATA_LOSS  
 > [!CAUTION]  
>  Das Erzwingen eines Failovers kann zu Datenverlusten führen und ist daher ausschließlich als Notfallwiederherstellungsmethode vorgesehen. Daher empfehlen wir dringend, dass Sie nur Failover erzwingen, wenn das primäre Replikat nicht mehr ausgeführt wird, da Sie bereitwillig Datenverluste riskieren. Außerdem müssen Sie den Dienst sofort für die Verfügbarkeitsgruppe wiederherstellen.  
  
 Wird nur auf einem Replikat unterstützt, dessen Rolle sich im Status SECONDARY oder RESOLVING befindet. --Für das Replikat auf dem Sie ein failoverbefehl eingeben, wird als bezeichnet den *failoverziel*.  
  
 Erzwingt ein Failover der Verfügbarkeitsgruppe zum Failoverziel (mit möglichem Datenverlust). Das Failoverziel übernimmt die primäre Rolle und stellt seine Kopie jeder Datenbank wieder her und schaltet sie als neue primäre Datenbanken online. Auf jeglichen verbleibenden sekundären Replikaten wird jede sekundäre Datenbank angehalten, bis sie manuell fortgesetzt wird. Wenn das frühere primäre Replikat verfügbar wird, wechselt es zur sekundären Rolle, und seine Datenbanken werden angehaltene sekundäre Datenbanken.  
  
> [!NOTE]  
>  Ein Failoverbefehl gibt einen Wert zurück, sobald das Failoverziel den Befehl akzeptiert hat. Die Datenbankwiederherstellung tritt jedoch asynchron auf, nachdem die Verfügbarkeitsgruppe aufgehört hat, ein Failover auszuführen.  
  
 Informationen zu den Einschränkungen, Voraussetzungen und Empfehlungen zum Erzwingen eines Failovers sowie den Auswirkungen eines erzwungenen Failovers auf den bisherigen primären Datenbanken in der verfügbarkeitsgruppe finden Sie unter [Ausführen eines erzwungenen manuellen Failovers einer verfügbarkeitsgruppe Group &#40; SQLServer &#41; ](../../database-engine/availability-groups/windows/perform-a-forced-manual-failover-of-an-availability-group-sql-server.md).  
  
 ADD LISTENER **"***Dns_name***" (** \<Add_listener_option > **)**  
 Definiert einen neuen Verfügbarkeitsgruppenlistener für diese Verfügbarkeitsgruppe. Wird nur für das primäre Replikat unterstützt.  
  
> [!IMPORTANT]  
>  Vor dem Erstellen des ersten Listeners wird dringend empfohlen, Sie lesen [erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners &#40; SQLServer &#41; ](../../database-engine/availability-groups/windows/create-or-configure-an-availability-group-listener-sql-server.md).  
>   
>  Nachdem Sie einen Listener für eine Verfügbarkeitsgruppe erstellt haben, empfehlen wir dringend, folgende Schritte auszuführen:  
>   
>  -   Bitten Sie den Netzwerkadministrator, die IP-Adresse des Listeners zur exklusiven Verwendung zu reservieren.  
> -   Geben Sie den DNS-Hostnamen des Listeners an Anwendungsentwickler weiter, damit diese den Namen in Verbindungszeichenfolgen zum Anfordern von Clientverbindungen mit dieser Verfügbarkeitsgruppe verwenden.  
  
 *dns_name*  
 Gibt den DNS-Hostnamen des Verfügbarkeitsgruppenlisteners an. Der DNS-Name des Listeners muss in der Domäne und NetBIOS eindeutig sein.  
  
 *Dns_name* ist ein Zeichenfolgenwert. Dieser Name darf nur alphanumerische Zeichen, Bindestriche (-) und Unterstriche (_) enthalten (in beliebiger Reihenfolge). Bei DNS-Hostnamen muss die Groß-/Kleinschreibung beachtet werden. Die maximale Länge beträgt 63 Zeichen.  
  
 Wir empfehlen, dass Sie eine sinnvolle Zeichenfolge angeben. Für eine Verfügbarkeitsgruppe mit dem Namen `AG1`wäre ein sinnvoller DNS-Hostname z. B. `ag1-listener`.  
  
> [!IMPORTANT]  
>  NetBIOS erkennt nur die ersten 15 Zeichen im dns_name. Wenn Sie zwei WSFC-Cluster verwenden, die vom gleichen Active Directory gesteuert werden, und Sie versuchen, Verfügbarkeitsgruppenlistener in beiden Clustern mit Namen mit mehr als 15 Zeichen und einem identischen 15-Zeichen-Präfix zu erstellen, erhalten Sie eine Fehlermeldung mit dem Hinweis, dass die VNN-Ressource nicht online geschaltet werden konnte. Informationen zu Präfix-Benennungsregeln für DNS-Namen finden Sie unter [Zuweisen von Domänennamen](http://technet.microsoft.com/library/cc731265\(WS.10\).aspx).  
  
 JOIN-VERFÜGBARKEITSGRUPPE AUF  
 Verknüpft mit einem *verteilten verfügbarkeitsgruppe*. Wenn Sie eine verteilte verfügbarkeitsgruppe erstellen, wird die verfügbarkeitsgruppe auf dem Cluster, in dem es erstellt wird, der primären verfügbarkeitsgruppe. Die verfügbarkeitsgruppe, die die verteilte verfügbarkeitsgruppe verknüpft ist, die sekundäre verfügbarkeitsgruppe.  
  
 \<ag_name>  
 Gibt den Namen der verfügbarkeitsgruppe, die eine bildet die Hälfte der verteilten verfügbarkeitsgruppe.  
  
 LISTENER **= "**TCP**://***Systemadresse***:***Port***"**  
 Gibt den URL-Pfad für den Listener der verfügbarkeitsgruppe zugeordnet.  
  
 Die LISTENER-Klausel ist erforderlich.  
  
 **"**TCP**://***Systemadresse***:***Port***"**  
 Gibt eine URL für den Listener der verfügbarkeitsgruppe zugeordnet. Die URL-Parameter lauten wie folgt:  
  
 *system-address*  
 Ist eine Zeichenfolge, z. B. ein Systemname, einen vollqualifizierten Domänennamen oder eine IP-Adresse, die den Listener zielcomputersystem eindeutig identifiziert.  
  
 *port*  
 Ist eine Portnummer, die dem Spiegelungsendpunkt der verfügbarkeitsgruppe zugeordnet ist. Beachten Sie, dass dies nicht der Port des Listeners ist.  
  
 AVAILABILITY_MODE  **=**  {SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT}  
 Gibt an, ob das primäre Replikat warten Sie, bis die sekundäre verfügbarkeitsgruppe bestätigen Sie das verstärken (Schreiben), der die Protokolldatensätze auf den Datenträger, bevor das primäre Replikat einen Commit die Transaktion auf eine bestimmte primäre Datenbank ausführen kann.  
  
 SYNCHRONOUS_COMMIT  
 Gibt an, dass das primäre Replikat wartet, um Transaktionen zu übernehmen, bis sie auf die sekundäre verfügbarkeitsgruppe festgeschrieben wurden. Sie können SYNCHRONOUS_COMMIT für bis zu zwei Verfügbarkeitsgruppen, einschließlich der primären verfügbarkeitsgruppe angeben.  
  
 ASYNCHRONOUS_COMMIT  
 Gibt an, dass das primäre Replikat Transaktionen ein Commit ausgeführt wird, ohne zu warten, die für diese sekundäre verfügbarkeitsgruppe auf das Protokoll festschreibt. Sie können ASYNCHRONOUS_COMMIT für bis zu zwei Verfügbarkeitsgruppen, einschließlich der primären verfügbarkeitsgruppe angeben.  
  
 Die AVAILABILITY_MODE-Klausel ist erforderlich.  
  
 FAILOVER_MODE  **=**  {MANUELLE}  
 Gibt den Failovermodus der verteilten verfügbarkeitsgruppe.  
  
 MANUAL  
 Ermöglicht, Geplantes Manuelles Failover oder erzwungenes Manuelles Failover (normalerweise *erzwungenes Failover*) durch den Datenbankadministrator.  
  
 Das automatische Failover auf die sekundäre Verfügbarkeitsgruppe wird nicht unterstützt.  
  
 SEEDING_MODE **=**  {AUTOMATISCHE | MANUELLE}  
 Gibt an, wie die sekundäre verfügbarkeitsgruppe anfänglich ausgeführt werden.  
  
 AUTOMATIC  
 Ermöglicht das automatische seeding. Diese Methode wird die sekundäre verfügbarkeitsgruppe über das Netzwerk Ausgangswert. Diese Methode erfordert nicht das Sichern und Wiederherstellen einer Kopie der primären Datenbank auf den Replikaten der sekundären verfügbarkeitsgruppe.  
  
 MANUAL  
 Gibt an, das seeding manuell. Diese Methode müssen Sie eine Sicherung der Datenbank auf dem primären Replikat zu erstellen und diese Sicherung auf die Replikate der sekundären verfügbarkeitsgruppe manuell wiederherstellen.  
  
 ÄNDERN DER VERFÜGBARKEITSGRUPPE AUF  
 Ändert ein beliebiges die verfügbarkeitsgruppeneinstellungen einer verteilten verfügbarkeitsgruppe. Die Liste der zu ändernden Verfügbarkeitsgruppen enthält den Namen und eine WITH (...)-Klausel für jede verfügbarkeitsgruppe.  
  
> [!IMPORTANT]  
>  Dieser Befehl muss auf dem primären verfügbarkeitsgruppe und dem sekundären verfügbarkeitsreplikat Gruppeninstanzen wiederholt werden.  
  
 GRANT BELIEBIGE DATENBANK ERSTELLEN  
 Ermöglicht die verfügbarkeitsgruppe zum Erstellen von Datenbanken für das primäre Replikat, das direkte seeding unterstützt (SEEDING_MODE = AUTOMATIC). Dieser Parameter sollte auf jedem sekundären Replikat ausgeführt werden, die direkte seeding unterstützt, nachdem diese sekundäre Datenbank der verfügbarkeitsgruppe verknüpft.  Erfordert die CREATE ANY DATABASE-Berechtigung.  
  
 VERWEIGERN BELIEBIGE DATENBANK ERSTELLEN  
 Entfernt die Möglichkeit zum Erstellen von Datenbanken für das primäre Replikat der verfügbarkeitsgruppe.  
  
 \<add_listener_option>  
 ADD LISTENER verwendet eine der folgenden Optionen:  
  
 MIT DHCP [ON { **("***four_part_ipv4_address***","***four_part_ipv4_mask***")** }]  
 Gibt an, dass der Verfügbarkeitsgruppenlistener das Dynamic Host Configuration-Protokoll (DHCP) verwendet.  Verwenden Sie die ON-Klausel optional, um das Netzwerk zu identifizieren, auf dem dieser Listener erstellt wird. DHCP ist auf ein einzelnes Subnetz beschränkt, das für alle Serverinstanzen verwendet wird, die ein Verfügbarkeitsreplikat in der Verfügbarkeitsgruppe hosten.  
  
> [!IMPORTANT]  
>  DHCP wird in einer Produktionsumgebung nicht empfohlen. Wenn die DHCP-IP-Leasedauer bei einer Downtime abläuft, ist eine Verlängerung erforderlich, um die neue IP-Adresse des DHCP-Netzwerks zu registrieren, die dem DNS-Namen des Listeners zugeordnet ist, was sich auf die Clientkonnektivität auswirkt. DHCP eignet sich jedoch gut zum Einrichten der Entwicklungs- und Testumgebung, um grundlegende Funktionen von Verfügbarkeitsgruppen und die Integration in Ihre Anwendungen zu überprüfen.  
  
 Beispiel:  
  
 `WITH DHCP ON ('10.120.19.0','255.255.254.0')`  
  
 MIT IP-Adresse **(** { **("***four_part_ipv4_address***","***four_part_ipv4_mask***")** | **("***ipv6_address***")** } [ **,** ...  *n*  ] **)** [ **,** PORT **= *** Listener_port* ]  
 Gibt an, dass, der Listener der Verfügbarkeitsgruppe statt DHCPr eine oder mehrere statische IP-Adressen verwendet. Um eine Verfügbarkeitsgruppe über mehrere Subnetze zu erstellen, erfordert jedes Subnetz in der Listenerkonfiguration eine statische IP-Adresse. Für ein angegebenes Subnetz kann die statische IP-Adresse entweder eine IPv4-Adresse oder eine IPv6-Adresse sein. Wenden Sie sich an Ihren Netzwerkadministrator, um eine statische IP-Adresse für jedes Subnetz zu erhalten, das ein Verfügbarkeitsreplikat für die neue Verfügbarkeitsgruppe hostet.  
  
 Beispiel:  
  
 `WITH IP ( ('10.120.19.155','255.255.254.0') )`  
  
 *four_part_ipv4_address*  
 Gibt eine vierteilige IPv4-Adresse für einen Verfügbarkeitsgruppenlistener an. Beispiel: `10.120.19.155`.  
  
 *four_part_ipv4_mask*  
 Gibt eine vierteilige IPv4-Maske für einen Verfügbarkeitsgruppenlistener an. Beispiel: `255.255.254.0`.  
  
 *ipv6_address*  
 Gibt eine IPv6-Adresse für einen Verfügbarkeitsgruppenlistener an. Beispiel: `2001::4898:23:1002:20f:1fff:feff:b3a3`.  
  
 PORT **=** *listener_port*  
 Gibt die Portnummer –*Listener_port*– von einem Verfügbarkeitsgruppen-Listener verwendet werden, die von einer WITH IP-Klausel angegeben ist. PORT ist optional.  
  
 Die Standardportnummer 1433 wird unterstützt. Wenn Sie jedoch Sicherheitsbedenken hegen, empfehlen wir die Verwendung einer anderen Portnummer.  
  
 Beispiel: `WITH IP ( ('2001::4898:23:1002:20f:1fff:feff:b3a3') ) , PORT = 7777`  
  
 MODIFY LISTENER **"***Dns_name***" (** \<Modify_listener_option > **)**  
 Ändert einen vorhandenen Verfügbarkeitsgruppenlistener für diese Verfügbarkeitsgruppe. Wird nur für das primäre Replikat unterstützt.  
  
 \<modify_listener_option>  
 MODIFY LISTENER verwendet eine der folgenden Optionen:  
  
 ADD IP { **("***four_part_ipv4_address***","***four_part_ipv4_mask***")** | **("**Dns_name*ipv6_ Address***')**}  
 Fügt die angegebene IP-Adresse an den Listener der verfügbarkeitsgruppe gemäß *Dns_name*.  
  
 PORT **=** *listener_port*  
 Die Beschreibung dieses Arguments finden Sie weiter oben in diesem Abschnitt.  
  
 LISTENER neu starten **"***Dns_name***"**  
 Startet den Listener, der dem angegebenen DNS-Namen zugeordnet ist, erneut. Wird nur für das primäre Replikat unterstützt.  
  
 LISTENER entfernen **"***Dns_name***"**  
 Entfernt den Listener, der dem angegebenen DNS-Namen zugeordnet ist. Wird nur für das primäre Replikat unterstützt.  
  
 OFFLINE  
 Schaltet eine Onlineverfügbarkeitsgruppe offline. Es gibt keinen Datenverlust bei Datenbanken mit synchronem Commit.  
  
 Nachdem eine Verfügbarkeitsgruppe offline geschaltet wurde, sind ihre Datenbanken für Clients nicht mehr verfügbar, und Sie können die Verfügbarkeitsgruppe nicht wieder online schalten. Verwenden Sie die OFFLINE-Option daher nur während einer Kreuzclustermigration von [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], wenn Sie Verfügbarkeitsgruppenressourcen zu einem neuen WSFC-Cluster migrieren.  
  
 Weitere Informationen finden Sie unter [nehmen eine Verfügbarkeit Gruppe Offline &#40; SQLServer &#41; ](../../database-engine/availability-groups/windows/take-an-availability-group-offline-sql-server.md).  
  
## <a name="prerequisites-and-restrictions"></a>Voraussetzungen und Einschränkungen  
 Informationen zu den Voraussetzungen und Einschränkungen für verfügbarkeitsreplikate und deren hostserverinstanzen und Computer, finden Sie unter [Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen &#40; SQLServer &#41; ](../../database-engine/availability-groups/windows/prereqs-restrictions-recommendations-always-on-availability.md).  
  
 Informationen zu Einschränkungen bei den AVAILABILITY GROUP-Transact-SQL-Anweisungen finden Sie unter [Übersicht von Transact-SQL-Anweisungen für AlwaysOn-Verfügbarkeitsgruppen &#40; SQLServer &#41; ](../../database-engine/availability-groups/windows/transact-sql-statements-for-always-on-availability-groups.md).  
  
## <a name="security"></a>Sicherheit  
  
### <a name="permissions"></a>Berechtigungen  
 Erfordert die ALTER AVAILABILITY GROUP-Berechtigung für die Verfügbarkeitsgruppe, die CONTROL AVAILABILITY GROUP-Berechtigung, die ALTER ANY AVAILABILITY GROUP-Berechtigung oder die CONTROL SERVER-Berechtigung.  Außerdem erfordert die ALTER ANY DATABASE-Berechtigung.   
  
## <a name="examples"></a>Beispiele  
  
###  <a name="Join_Secondary_Replica"></a> A. Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe  
 Im folgenden Beispiel verknüpft ein sekundäres Replikat mit dem Sie verbunden sind, die `AccountsAG` verfügbarkeitsgruppe.  
  
```SQL  
ALTER AVAILABILITY GROUP AccountsAG JOIN;  
GO  
```  
  
###  <a name="Force_Failover"></a> B. Erzwingen eines Failovers einer Verfügbarkeitsgruppe  
 Im folgenden Beispiel wird ein Failover der `AccountsAG`-Verfügbarkeitsgruppe zum sekundären Replikat erzwungen, mit dem Sie verbunden sind.  
  
```SQL
ALTER AVAILABILITY GROUP AccountsAG FORCE_FAILOVER_ALLOW_DATA_LOSS;  
GO  
```  
  
## <a name="see-also"></a>Siehe auch  
 [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;;](../../t-sql/statements/create-availability-group-transact-sql.md)   
 [ALTER DATABASE SET HADR &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql-set-hadr.md)   
 [DROP AVAILABILITY GROUP &#40;Transact-SQL&#41;](../../t-sql/statements/drop-availability-group-transact-sql.md)   
 [sys.availability_replicas &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-availability-replicas-transact-sql.md)   
 [sys.availability_groups &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-availability-groups-transact-sql.md)   
 [Problembehandlung für die Always On-Verfügbarkeitsgruppenkonfiguration &#40; SQLServer &#41;](../../database-engine/availability-groups/windows/troubleshoot-always-on-availability-groups-configuration-sql-server.md)   
 [Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)   
 [Verfügbarkeitsgruppenlistener, Clientkonnektivität und Anwendungsfailover (SQL Server)](../../database-engine/availability-groups/windows/listeners-client-connectivity-application-failover.md)  
  
  
