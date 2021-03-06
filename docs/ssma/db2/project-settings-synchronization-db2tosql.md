---
title: Projekt Settings(Synchronization) (DB2ToSQL) | Microsoft Docs
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: ''
ms.component: ssma-db2
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.technology:
- sql-ssma
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: a5629a72-8c17-46a4-bb4d-19d51a0b98a2
caps.latest.revision: 4
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: da4be629e37646b10011c76f5a78a2cde246865e
ms.sourcegitcommit: 9351e8b7b68f599a95fb8e76930ab886db737e5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2018
---
# <a name="project-settingssynchronization-db2tosql"></a>Project Settings(Synchronization) (DB2ToSQL)
Die Seite "Synchronisierung", der die **Projekteinstellungen** das Dialogfeld enthält Einstellungen, die anpassen, wie SSMA lädt und Aktualisierungen-Datenbankobjekte, z. B. Tabellen und gespeicherten Prozeduren in [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)].  
  
Die Standardoptionen für die Aktionen geben Standardeinstellungen für die Aktualisierung von Objekten aus der DB2-Datenbank und zum Synchronisieren von Objekten mit SQL Server-Datenbank. Weitere Informationen finden Sie unter [aus der Datenbank aktualisieren &#40;DB2ToSQL&#41;](../../ssma/db2/refresh-from-database-db2tosql.md).  
  
Sie können zwei unterschiedliche Synchronisierung Seiten zugreifen, die die gleichen Einstellungen enthalten:  
  
-   Zum Angeben von Einstellungen für alle zukünftigen SSMA-Projekte, auf die **Tools** Menü klicken Sie auf **Projekt Standardeinstellungen**, und klicken Sie dann auf **Synchronisierung** unten im linken Bereich.  
  
-   Zum Angeben von Einstellungen für das aktuelle Projekt auf die **Tools** Menü klicken Sie auf **Projekteinstellungen**, und klicken Sie dann auf **Synchronisierung** unten im linken Bereich.  
  
## <a name="miscellaneous-options"></a>Sonstige Optionen  
**Versuche**  
Gibt die Anzahl der Versuche, die beim Laden von Objekten in SSMA nehmen [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]. Objekte, die nicht geladen werden [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] in der aktuellen Versuch wird wiederholt werden bis SSMA die maximale Anzahl von versuchen, in die aktuelle Synchronisierung erreicht. Ist der Standardwert festgelegt **2**  
  
## <a name="synchronization-for-db2-options"></a>Synchronisierung für DB2-Optionen  
**Aktion bei Änderung der lokale und remote-Objekt**  
Gibt die Standardeinstellung im Dialogfeld "Synchronisierung", wenn sich die Objektdefinition in SSMA und auf dem Datenbankserver ändert. Ist der Standardwert festgelegt **aus der Datenbank aktualisieren**.  
  
-   Bei Auswahl des **aus der Datenbank aktualisieren**, SSMA laden Datenbankdefinitionen in den Metadaten ab, wenn die Bedingung erfüllt ist.  
  
-   Bei Auswahl des **Skip**, SSMA wird keine Aktualisierung Aktionen ausführen.  
  
**Aktion bei Änderung der lokale-Objekt**  
Gibt die Standardeinstellung im Dialogfeld "Synchronisierung", wenn das Objekt im SSMA ändert. Ist der Standardwert festgelegt **Skip**.  
  
-   Bei Auswahl des **aus der Datenbank aktualisieren**, SSMA laden Datenbankdefinitionen in den Metadaten ab, wenn die Bedingung erfüllt ist.  
  
-   Bei Auswahl des **Skip**, SSMA wird keine Aktualisierung Aktionen ausführen.  
  
**Aktion bei Änderung der remote-Objekt**  
Gibt die Standardeinstellung im Dialogfeld "Synchronisierung", wenn die Objekte auf dem Datenbankserver ändern. Ist der Standardwert festgelegt **aus der Datenbank aktualisieren**.  
  
-   Bei Auswahl des **aus der Datenbank aktualisieren**, SSMA laden Datenbankdefinitionen in den Metadaten ab, wenn die Bedingung erfüllt ist.  
  
-   Bei Auswahl des **Skip**, SSMA wird keine Aktualisierung Aktionen ausführen.  
  
**Aktion beim lokalen Objektmetadaten nicht vorhanden ist.**  
Gibt die Standardeinstellung im Dialogfeld Synchronisierung, bei der lokalen Metadaten fehlen. Ist der Standardwert festgelegt **aus der Datenbank aktualisieren**.  
  
-   Bei Auswahl des **aus der Datenbank aktualisieren**, SSMA SSMA laden Datenbankdefinitionen in den Metadaten ab, wenn die Bedingung erfüllt ist.  
  
-   Bei Auswahl des **Skip**, SSMA wird keine Aktualisierung Aktionen ausführen.  
  
## <a name="synchronization-for-sql-server-options"></a>Synchronisierung für SQL Server-Optionen  
**Aktion bei Änderung der lokale und remote-Objekt**  
Gibt die Standardeinstellung im Dialogfeld "Synchronisierung", wenn sich die Objektdefinition in SSMA und auf dem Datenbankserver ändert. Ist der Standardwert festgelegt **Schreiben in Datenbank**.  
  
-   Bei Auswahl des **aus der Datenbank aktualisieren**, SSMA laden Datenbankdefinitionen in den Metadaten ab, wenn die Bedingung erfüllt ist.  
  
-   Bei Auswahl des **in Datenbank schreiben**, SSMA werden Objekte in der Datenbank gemäß SSMA-Metadaten-Inhalt aktualisiert, wenn die Bedingung erfüllt ist.  
  
-   Bei Auswahl des **Skip**, SSMA wird keine Aktualisierung Aktionen ausführen.  
  
**Aktion bei Änderung der lokale-Objekt**  
Gibt die Standardeinstellung im Dialogfeld "Synchronisierung", wenn das Objekt im SSMA ändert. Ist der Standardwert festgelegt **Schreiben in Datenbank**.  
  
-   Bei Auswahl des **aus der Datenbank aktualisieren**, SSMA laden Datenbankdefinitionen in den Metadaten ab, wenn die Bedingung erfüllt ist.  
  
-   Bei Auswahl des **in Datenbank schreiben**, SSMA wird das Objekt in der Datenbank gemäß SSMA-Metadaten-Inhalt aktualisiert, wenn die Bedingung erfüllt ist.  
  
-   Bei Auswahl des **Skip**, SSMA wird keine Aktualisierung Aktionen ausführen.  
  
**Aktion bei Änderung der remote-Objekt**  
Gibt die Standardeinstellung im Dialogfeld "Synchronisierung", wenn die Objekte auf dem Datenbankserver ändern.  Ist der Standardwert festgelegt **aus der Datenbank aktualisieren**.  
  
-   Bei Auswahl des **aus der Datenbank aktualisieren**, SSMA laden Datenbankdefinitionen in den Metadaten ab, wenn die Bedingung erfüllt ist.  
  
-   Bei Auswahl des **in Datenbank schreiben**, SSMA wird das Objekt in der Datenbank gemäß SSMA-Metadaten-Inhalt aktualisiert, wenn die Bedingung erfüllt ist.  
  
-   Bei Auswahl des **Skip**, SSMA wird keine Aktualisierung Aktionen ausführen.  
  
**Aktion beim lokalen Objektmetadaten nicht vorhanden ist.**  
Gibt die Standardeinstellung im Dialogfeld Synchronisierung, bei der lokalen Metadaten fehlen. Ist der Standardwert festgelegt **aus der Datenbank aktualisieren**.  
  
-   Bei Auswahl des **aus der Datenbank aktualisieren**, SSMA wählt die **aus der Datenbank aktualisieren** option, wenn die Bedingung erfüllt ist.  
  
-   Bei Auswahl des **in Datenbank schreiben**, SSMA wird das Objekt aus der Datenbank löschen, wenn die Bedingung erfüllt ist.  
  
-   Bei Auswahl des **Skip**, SSMA wird keine Aktualisierung Aktionen ausführen.  
  
