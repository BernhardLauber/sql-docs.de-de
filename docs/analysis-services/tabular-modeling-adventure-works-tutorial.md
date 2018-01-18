---
title: "Tabellenmodellierung (Kompatibilitätsgrad 1200) | Microsoft Docs"
ms.custom: 
ms.date: 01/17/2018
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: get-started-article
applies_to: SQL Server 2016
keywords:
- Analysis Services
- tabellarisches Modell
- Lernprogramm
- SSAS
ms.assetid: 140d0b43-9455-4907-9827-16564a904268
caps.latest.revision: "40"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Active
ms.openlocfilehash: 20248d68dc0371ef158f287d1f3a8bc9e87360d3
ms.sourcegitcommit: dcac30038f2223990cc21775c84cbd4e7bacdc73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/18/2018
---
# <a name="tabular-modeling-1200-compatibility-level"></a>Tabellenmodellierung (Kompatibilitätsgrad 1200)
[!INCLUDE[ssas-appliesto-sql2016-later-aas](../includes/ssas-appliesto-sql2016-later-aas.md)]

Dieses Lernprogramm enthält Lektionen zum Erstellen einer Analysis Services-Tabellenmodell an die [Kompatibilitätsgrad 1200](../analysis-services/tabular-models/compatibility-level-for-tabular-models-in-analysis-services.md) mit [SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt), und die Bereitstellung Ihres Modells in einer Analysis Services Server lokal oder in Azure.  
 
Wenn Sie 2017 von SQL Server oder Azure Analysis Services, und Sie verwenden möchten, Ihr Modell auf die Kompatibilität 1400 Ebene erstellen, verwenden die [Azure Analysis Services - Adventure Works-Lernprogramm](https://review.docs.microsoft.com/azure/analysis-services/tutorials/aas-adventure-works-tutorial?branch=master). Diese aktualisierte Version der neue, moderne Get Data-Funktion verwendet, um eine Verbindung herzustellen, und importieren die Quelldaten und die M-Sprache verwendet, um Partitionen zu konfigurieren.
 
  
## <a name="what-youll-learn"></a>Ihre Lernziele   
  
-   Vorgehensweise: erstellen ein neuen tabellenmodellprojekts in SSDT.
  
-   Importieren von Daten von einer relationalen SQL Server-Datenbank in ein Tabellenmodellprojekt.  
  
-   Erstellen und Verwalten von Beziehungen zwischen Tabellen im Modell.  
  
-   Erstellen und Verwalten von Berechnungen, Measures und Key Performance Indicators, mit denen Benutzer Modelldaten analysieren können.  
  
-   Erstellen und Verwalten von Perspektiven und Hierarchien, mit denen Benutzer durch die Bereitstellung von geschäfts- und anwendungsspezifischen Blickpunkten einfacher Modelldaten durchsuchen können.  
  
-   Erstellen von Partitionen, mit denen sich Tabellendaten in kleinere logische Teile aufteilen lassen, die unabhängig von anderen Partitionen verarbeitet werden können.  
  
-   Sichern von Modellobjekten und -daten durch die Erstellung von Rollen mit Benutzerelementen.  
  
-   Wie Sie ein tabellarisches Modell in Analysis Services-Server lokal oder in Azure bereitstellen.  
  
## <a name="scenario"></a>Szenario  
Dieses Lernprogramm basiert auf dem Adventure Works Cycles, einem fiktiven Unternehmen. Adventure Works ist ein großes, multinationales Herstellungsunternehmen, das produziert und vertreibt Fahrräder aus Metallene und Verbundwerkstoffen für kommerzielle Märkte in Nordamerika, Europa und Asien. Mit Hauptsitz in Bothell, Washington werden in das Unternehmen 500 Arbeiter beschäftigt. Darüber hinaus Verkaufsteams Adventure Works mehrere regionalen gesamte marktbasis.  
  
Um die Datenanalyseanforderungen von Verkaufs- und Marketingteams sowie des Senior Managements besser zu unterstützen, werden Sie damit beauftragt, ein Tabellenmodell für Benutzer zu erstellen, um Internetumsatzdaten in der AdventureWorksDW-Beispieldatenbank zu analysieren.  
  
Um das Lernprogramm und das Tabellenmodell für die Adventure Works-Internetverkäufe abzuschließen, ist eine Reihe von Lektionen auszuführen. Jede Lektion umfasst eine Reihe von Aufgaben, und das Abschließen jeder Aufgabe ist zum Abschließen der jeweiligen Lektion erforderlich. Während in einer bestimmten Lektion gibt es möglicherweise mehrere Aufgaben, die einem ähnlichen Ergebnis zu erreichen, aber wie jede Aufgabe etwas anders ist. Dadurch wird angezeigt, dass oftmals mehrere Möglichkeiten, um eine bestimmte Aufgabe auszuführen, und fordern Sie mithilfe von Fähigkeiten, die Sie in vorherigen Aufgaben gelernt haben.  
  
Die Lektionen ist, führt Sie durch die Erstellung eines basistabellenmodells, das im InMemory Modus ausgeführt wird, indem Sie viele der in SSDT enthaltenen Features. Da jede Lektion auf der jeweils vorherigen Lektion aufbaut, sollten Sie die Lektionen in der entsprechenden Reihenfolge bearbeiten. Nachdem Sie alle Lektionen abgeschlossen haben, werden Sie erstellt und der Adventure Works Internet Sales tabular Beispielmodell auf einem Analysis Services-Server bereitgestellt.  
  
Dieses Lernprogramm enthält keine Lektionen oder Informationen zum Verwalten einer Datenbank für Tabellenmodelle unter Verwendung von SQL Server Management Studio oder das Verwenden einer Berichterstellungs-Clientanwendung zur Herstellung einer Verbindung mit einem bereitgestellten Modell zum Durchsuchen von Modelldaten.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
Um dieses Lernprogramm abzuschließen, benötigen Sie die folgenden Voraussetzungen:  
  
-   Die neueste Version von [! UMFASSEN[SsBIDevStudioFull](../ssdt/download-sql-server-data-tools-ssdt.md).

-   Die neueste Version von SQL Server Management Studio. [Abrufen der neuesten Version](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms). 
  
-   Eine Clientanwendung, z. B. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) oder [!INCLUDE[msCoName](../includes/msconame-md.md)] Excel.    
  
-   Eine SQL Server-Instanz mit der Beispieldatenbank Adventure Works DW 2014. Diese Beispieldatenbank beinhaltet die für das Abschließen des Lernprogramms notwendigen Daten. [Abrufen der neuesten Version](http://go.microsoft.com/fwlink/?LinkID=335807).  
  

-   Ein Azure Analysis Services oder SQL Server 2016 oder höher Analysis Services-Instanz Ihres Modells bereitstellen. [Registrieren Sie sich für eine kostenlose Testversion von Azure Analysis Services](https://azure.microsoft.com/services/analysis-services/).
  
## <a name="lessons"></a>Lektionen  
Dieses Tutorial umfasst die folgenden Lektionen:  
  
|Lektion|Für den Abschluss voraussichtlich benötigte Zeit|  
|----------|------------------------------|  
|[Lektion 1: Erstellen eines neuen Tabellenmodellprojekts](../analysis-services/lesson-1-create-a-new-tabular-model-project.md)|10 Minuten|  
|[Lektion 2: Hinzufügen von Daten](../analysis-services/lesson-2-add-data.md)|20 Minuten|  
|[Lektion 3: Markieren Sie als Date-Tabelle](../analysis-services/lesson-3-mark-as-date-table.md)|3 Minuten|  
|[Lektion 4: Erstellen von Beziehungen](../analysis-services/lesson-4-create-relationships.md)|10 Minuten|  
|[Lektion 5: Erstellen von berechneten Spalten](../analysis-services/lesson-5-create-calculated-columns.md)|15 Minuten|
|[Lektion 6: Erstellen von Measures](../analysis-services/lesson-6-create-measures.md)|30 Minuten|  
|[Lektion 7: Erstellen von Leistungskennzahlen](../analysis-services/lesson-7-create-key-performance-indicators.md)|15 Minuten|  
|[Lektion 8: Erstellen von Perspektiven](../analysis-services/lesson-8-create-perspectives.md)|5 Minuten|  
|[Lektion 9: Erstellen von Hierarchien](../analysis-services/lesson-9-create-hierarchies.md)|20 Minuten|  
|[Lektion 10: Erstellen von Partitionen](../analysis-services/lesson-10-create-partitions.md)|15 Minuten|  
|[Lektion 11: Erstellen von Rollen](../analysis-services/lesson-11-create-roles.md)|15 Minuten|  
|[Lektion 12: In Excel analysieren](../analysis-services/lesson-12-analyze-in-excel.md)|20 Minuten| 
|[Lektion 13: Bereitstellen](../analysis-services/lesson-13-deploy.md)|5 Minuten|  
  
## <a name="supplemental-lessons"></a>Ergänzende Lektionen  
Dieses Tutorial umfasst außerdem [ergänzende Lektionen](http://msdn.microsoft.com/library/2018456f-b4a6-496c-89fb-043c62d8b82e). Die Themen in diesem Abschnitt sind nicht erforderlich, um das Lernprogramm abzuschließen, aber sie können das Verständnis der erweiterten Funktionen zum Erstellen eines Tabellenmodells erleichtern.  
  
|Lektion|Für den Abschluss voraussichtlich benötigte Zeit|  
|----------|------------------------------|  
|[Implementieren von dynamischer Sicherheit mithilfe von Zeilenfiltern](../analysis-services/supplemental-lesson-implement-dynamic-security-by-using-row-filters.md)|30 Minuten|  

  
## <a name="next-step"></a>Nächster Schritt  
Um das Tutorial zu starten, gehen Sie zur ersten Lektion über: [Lektion 1: Erstellen eines neuen Tabellenmodellprojekts](../analysis-services/lesson-1-create-a-new-tabular-model-project.md).  
  
  
  

