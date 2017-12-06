---
title: "Übersicht über SQLServer on Linux | Microsoft Docs"
description: "In diesem Thema wird beschrieben, wie SQL Server auf dem Linux ausgeführt wird, und enthält Informationen zum mehr zu erfahren."
author: rothja
ms.author: jroth
manager: jhubbard
ms.date: 10/02/2017
ms.topic: article
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: sql-linux
ms.suite: sql
ms.custom: 
ms.technology: database-engine
ms.assetid: 9dcc6a90-0add-42c2-815b-862e4e2a21ac
ms.workload: Active
ms.openlocfilehash: b598357bb8ebe17ad15fb10e1d74c21c169c1da8
ms.sourcegitcommit: 531d0245f4b2730fad623a7aa61df1422c255edc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2017
---
# <a name="sql-server-on-linux"></a>SQL Server unter Linux

SQL Server-2017 wird nun unter Linux ausgeführt werden. Es ist die gleiche SQL Server-Datenbankmodul, mit vielen ähnlichen Funktionen und Dienste unabhängig von Ihrem Betriebssystem.

## <a name="install"></a>Install

Installieren Sie SQL Server unter Linux mit einer der folgenden Schnellstart-Lernprogrammen, um zu beginnen:

- [Installieren Sie auf Red Hat Enterprise Linux](quickstart-install-connect-red-hat.md)
- [Installieren Sie auf SUSE Linux Enterprise Server](quickstart-install-connect-suse.md)
- [Installieren Sie auf Ubuntu](quickstart-install-connect-ubuntu.md)
- [Führen Sie auf Docker](quickstart-install-connect-docker.md)
- [Provision a SQL VM in Azure (Bereitstellen einer SQL-VM in Azure)](/azure/virtual-machines/linux/sql/provision-sql-server-linux-virtual-machine?toc=%2fsql%2flinux%2ftoc.json)

> [!NOTE]
> Docker selbst wird ausgeführt auf mehreren Plattformen, was bedeutet, dass das Image von Docker unter Linux, Mac und Windows ausgeführt werden können.

## <a name="connect"></a>Connect

Verbinden Sie nach der Installation mit SQL Server-Instanz auf dem Linux-Computer. Sie können lokal oder Remote und mit einer Vielzahl von Tools und Treiber verbinden. Der Schnellstart-Lernprogrammen wird gezeigt, wie mithilfe der [Sqlcmd](sql-server-linux-setup-tools.md) Befehlszeilentool. Andere Tools umfassen Folgendes:

| Tool | Lernprogramm |
|-----|-----|
| Visual Studio-Code (Visual Studio-Code) | [Verwenden Sie Visual Studio Code mit SQLServer on Linux](sql-server-linux-develop-use-vscode.md) |
| SQL Server Management Studio (SSMS) | [Verwenden von SSMS unter Windows zur Verbindung mit SQL Server on Linux](sql-server-linux-develop-use-ssms.md) |
| SQL Server Data Tools (SSDT) | [Verwenden von SSDT mit SQLServer on Linux](sql-server-linux-develop-use-ssdt.md) |

## <a name="explore"></a>Erkunden

SQL Server-2017 weist das gleiche zugrunde liegende Datenbankmodul auf allen unterstützten Plattformen, einschließlich Linux. So viele vorhandene Features und Funktionen sind aus funktionaler Sicht denselben unter Linux. Dieser Teil der Dokumentation macht einige dieser Funktionen im Hinblick auf Linux verfügbar. Er ruft auch bestimmte Bereiche, die unter Linux besondere Anforderungen verfügen.

Wenn Sie bereits mit SQL Server vertraut sind, überprüfen Sie die [Anmerkungen zu dieser Version](sql-server-linux-release-notes.md) für allgemeine Richtlinien und bekannten Probleme für diese Version. Sehen Sie sich [für SQL Server on Linux Neuigkeiten](sql-server-linux-whats-new.md) sowie [für SQL Server-2017 insgesamt Neuigkeiten](../sql-server/what-s-new-in-sql-server-2017.md).

##  <a name="infotipmediageneralinfotippng-engage-with-the-sql-server-engineering-team"></a>![info_tip](./media/general/info_tip.png) Kontaktaufnahme mit dem SQL Server-Entwicklungsteam

- [DBA-Stapel Exchange](https://dba.stackexchange.com/questions/tagged/sql-server): Datenbank-Verwaltung Fragen
- [Stapelüberlauf](http://stackoverflow.com/questions/tagged/sql-server): Fragen für die Entwicklung
- [MSDN-Foren](https://social.msdn.microsoft.com/Forums/en-US/home?category=sqlserver): technische Fragen
- [Microsoft Connect](https://connect.microsoft.com/SQLServer/Feedback): Melden von Fehlern und Anforderung-Funktion
- [Reddit](https://www.reddit.com/r/SQLServer/): Besprechen Sie SQLServer
