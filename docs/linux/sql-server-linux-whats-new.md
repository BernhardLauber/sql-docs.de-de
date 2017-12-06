---
title: "Neuigkeiten für SQLServer 2017 unter Linux | Microsoft Docs"
description: "In diesem Thema werden die Neuigkeiten für SQL Server-2017 unter Linux hervorgehoben."
author: rothja
ms.author: jroth
manager: jhubbard
ms.date: 11/28/2017
ms.topic: article
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: sql-linux
ms.suite: sql
ms.custom: 
ms.technology: database-engine
ms.assetid: 456b6f31-6b97-4e31-80ab-b40151ec4868
ms.workload: On Demand
ms.openlocfilehash: 3e4a3e19fd9d03d3f6e4dd4a68a5a15b922f348d
ms.sourcegitcommit: 531d0245f4b2730fad623a7aa61df1422c255edc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2017
---
# <a name="whats-new-for-sql-server-2017-on-linux"></a>Neuigkeiten für SQL Server-2017 unter Linux

[!INCLUDE[tsql-appliesto-sslinux-only](../includes/tsql-appliesto-sslinux-only.md)]

Dieser Artikel beschreibt die wichtigsten Funktionen und die verfügbaren Dienste für SQL Server-2017 auf Linux ausgeführt wird.

> [!NOTE]
> Zusätzlich zu diesen Funktionen in diesem Artikel sind kumulative Updates in regelmäßigen Abständen nach GA-Version veröffentlicht. Diese kumulativen Updates enthalten viele Verbesserungen und Fehlerbehebungen. Informationen über die neueste Version des CU finden Sie unter [http://aka.ms/sql2017cu](http://aka.ms/sql2017cu). Paketdownloads und bekannte Probleme finden Sie in der [Anmerkungen zu dieser Version](sql-server-linux-release-notes.md).

## <a name="sql-server-database-engine"></a>SQL Server-Datenbankmodul

- Aktiviert die Hauptfunktionen von SQL Server-Datenbankmoduls.
- Unterstützung für systemeigene Linux-Pfade.
- Unterstützung von IPv6.
- Unterstützung für die Datenbankdateien auf NFS.
- Aktiviert [transparente Layer Security](sql-server-linux-encrypted-connections.md) (TLS)-Verschlüsselung.
- Aktiviert [Active Directory-Authentifizierung](sql-server-linux-active-directory-authentication.md).
- [Verfügbarkeit Partitionsgruppenfunktionalität](sql-server-linux-availability-group-overview.md) für hohe Verfügbarkeit.
- [Volltextsuche](sql-server-linux-setup-full-text-search.md) unterstützen.

## <a name="sql-server-agent"></a>SQL Server-Agent

- Aktiviert [SQL Server-Agent](sql-server-linux-setup-sql-agent.md) für die folgenden Aufgaben unterstützen:
  - [Transact-SQL-Aufträge](sql-server-linux-run-sql-server-agent-job.md)
  - [DB-mail](sql-server-linux-db-mail-sql-agent.md)
  - [Protokollversand](sql-server-linux-use-log-shipping.md)

## <a name="sql-server-integration-services-ssis"></a>SQL Server Integration Services (SSIS)

- Die Fähigkeit zum Ausführen von SSIS-Pakete auf Linux. Weitere Informationen finden Sie unter [konfigurieren Sie SQL Server Integration Services unter Linux mit Ssis-Conf](sql-server-linux-configure-ssis.md).

## <a name="other-improvements"></a>Weitere Verbesserungen

- Befehlszeilen-Konfigurationstool, [Mssql-Conf](sql-server-linux-configure-mssql-conf.md).
- Unterstützung der unbeaufsichtigten Installation mit [Umgebungsvariablen](sql-server-linux-configure-environment-variables.md).
- Plattformübergreifende [Visual Studio Code-Mssql-servererweiterung](sql-server-linux-develop-use-vscode.md).
- Plattformübergreifende-Skript-Generator [Mssql Skripter](https://github.com/Microsoft/sql-xplat-cli/blob/dev/doc/usage_guide.md).
- Plattformübergreifende Dynamic Management View (DMV)-Monitor [DBFS Tool](https://github.com/Microsoft/dbfs).

## <a name="next-steps"></a>Nächste Schritte

Um SQL Server on Linux installieren, gehen Sie die folgenden Lernprogramme:

- [Installieren Sie auf Red Hat Enterprise Linux](quickstart-install-connect-red-hat.md)
- [Installieren Sie auf SUSE Linux Enterprise Server](quickstart-install-connect-suse.md)
- [Installieren Sie auf Ubuntu](quickstart-install-connect-ubuntu.md)
- [Führen Sie auf Docker](quickstart-install-connect-docker.md)
- [Provision a SQL VM in Azure (Bereitstellen einer SQL-VM in Azure)](/azure/virtual-machines/linux/sql/provision-sql-server-linux-virtual-machine?toc=%2fsql%2flinux%2ftoc.json)

Weitere Informationen zu SQL Server unter Linux finden Sie unter der [Übersicht](sql-server-linux-overview.md). Paketdownloads und eine Liste von nicht unterstützten Funktionen und bekannten Problemen finden Sie in der [Anmerkungen zu dieser Version](sql-server-linux-release-notes.md).

Zu den weiteren Verbesserungen in SQL Server-2017 eingeführt wurden, finden Sie unter [Neuigkeiten in SQL Server-2017](../sql-server/what-s-new-in-sql-server-2017.md).

[!INCLUDE[get-help-options](../includes/paragraph-content/get-help-options.md)]
