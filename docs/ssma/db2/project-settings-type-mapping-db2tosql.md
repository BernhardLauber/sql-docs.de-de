---
title: Projekteinstellungen (Zuordnung) (DB2ToSQL) | Microsoft Docs
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
ms.assetid: cf426c69-6a8e-4d19-951d-6661d5ae2562
caps.latest.revision: 5
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a268c4a080248028d8eeb399db68f0de57412b01
ms.sourcegitcommit: 9351e8b7b68f599a95fb8e76930ab886db737e5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2018
---
# <a name="project-settings-type-mapping-db2tosql"></a>Projekteinstellungen (Zuordnung) (DB2ToSQL)
Die Seite "Type Mapping", der die **Projekteinstellungen** Dialogfeld enthält Einstellungen, anpassen, wie SSMA DB2-Datentypen in konvertiert [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Datentypen.  
  
Die Seite "Type Mapping" steht in der **Projekteinstellungen** und **Projekt Standardeinstellungen** Dialogfelder.  
  
-   Zum Angeben von Einstellungen für alle zukünftigen SSMA-Projekte, auf die **Tools** klicken Sie im Menü **Projekt Standardeinstellungen**, wählen Sie die Migration-Projekttyp, die für die Einstellungen sind erforderlich, angezeigt oder geändert werden **Migration Zielversion** Dropdown-Liste, und klicken Sie dann auf **Type Mapping** unten im linken Bereich.  
  
-   Zum Angeben von Einstellungen für das aktuelle Projekt auf die **Tools** klicken Sie im Menü **Projekteinstellungen**, und klicken Sie dann auf **Type Mapping** unten im linken Bereich.  
  
Verwenden Sie zum Angeben von Einstellungen für das aktuelle Objekt oder eine Klasse von Objekten der **Type Mapping** Registerkarte im primären SSMA-Fenster.  
  
## <a name="options"></a>enthalten  
Die folgende Tabelle zeigt die **Type Mapping** Registerkarte Optionen:  
  
**Quelltyp**  
Der zugeordnete DB2-Datentyp.  
  
**Zieltyp**  
Das Ziel [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Datentyp für den angegebenen DB2-Datentyp.  
  
Finden Sie in den Tabellen im nächsten Abschnitt für den standardmäßigen SSMA für die DB2-datentypzuordnungen.  
  
**Hinzufügen**  
Klicken Sie auf diese Option, um einen Datentyp der Zuordnungsliste hinzuzufügen.  
  
**Bearbeiten**  
Klicken Sie auf diese Option, um den ausgewählten Datentyp in der Zuordnungsliste zu bearbeiten.  
  
**Entfernen**  
Klicken Sie auf diese Option, um die ausgewählte Zuordnung aus der Zuordnungsliste zu entfernen.  
  
**Standard wiederherstellen**  
Klicken Sie auf diese Option, um die Liste ' datentypzuordnung ' auf die SSMA-Standardwerte zurückzusetzen.  
  
## <a name="default-type-mappings"></a>Standard-Datentypzuordnungen  
In SSMA für DB2 können Sie benutzerdefinierte datentypzuordnungen für Argumente, die Spalten, die lokalen Variablen und die Rückgabewerte festlegen. Die standardzuordnung für Argumente und Rückgabetypen ist nahezu identisch.  
  
### <a name="default-argument-type-and-return-value-type-mapping"></a>Standard-Argumenttyp und Typzuordnung Wert zurückgeben  
Die folgende Tabelle enthält die standardmäßige datentypzuordnung für Argumente und Rückgabewerte.  
  
|DB2-Datentyp|Standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] -Datentyp|  
|-----------------|-------------------------------------------------------------------------|  
|BFILE|varbinary(max)|  
|binary_double|float[53]|  
|binary_float|float[53]|  
|binary_integer|int|  
|Blob|varbinary(max)|  
|boolean|bit|  
|char|varchar(max)|  
|char varying|varchar(max)|  
|character|varchar(max)|  
|character varying|varchar(max)|  
|CLOB|varchar(max)|  
|Datum|datetime2 [0]|  
|dec|dec[38][0]|  
|Decimal|float[53]|  
|mit doppelter Genauigkeit|float[53]|  
|float|float[53]|  
|int|int|  
|integer|int|  
|long|varchar(max)|  
|Long raw|varbinary(max)|  
|Long raw [\*... 8000]<sup>*</sup>|varbinary[*]|  
|Long raw [8001..\*]<sup>*</sup>|varbinary(max)|  
|National char|nvarchar(max)|  
|National Char varying|nvarchar(max)|  
|nationale Zeichensätze|nvarchar(max)|  
|nationale Zeichensätze varying<sup>**</sup>|nvarchar(max)|  
|nationale Zeichensätze varying<sup>*</sup>|nvarchar(max)|  
|NCHAR|nvarchar(max)|  
|NCLOB|nvarchar(max)|  
|number|float[53]|  
|numeric|float[53]|  
|nvarchar2|nvarchar(max)|  
|pls_integer|int|  
|raw|varbinary(max)|  
|real|float[53]|  
|rowid|uniqueidentifier|  
|Signtype|smallint|  
|smallint|smallint|  
|Zeichenfolge|varchar(max)|  
|timestamp|datetime2|  
|Zeitstempel mit der lokalen Zeitzone|datetimeoffset|  
|Zeitstempel mit Zeitzone|datetimeoffset|  
|UROWID|uniqueidentifier|  
|varchar|varchar(max)|  
|varchar2|varchar(max)|  
|xmltype|xml|  
  
<sup>*</sup> Gilt für Typ wertezuordnung nur zurückgeben.  
  
<sup>**</sup> Gilt für das Argument Typ nur zuordnen.  
  
### <a name="default-column-type-mapping"></a>Standardtypmapping Spalte  
Die folgende Tabelle enthält die Standard-Typzuordnung für Spalten.  
  
|DB2-Datentyp|Standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] -Datentyp|  
|-----------------|-------------------------------------------------------------------------|  
|BFILE|varbinary(max)|  
|binary_double|float[53]|  
|binary_float|float[53]|  
|Blob|varbinary(max)|  
|char|char|  
|Char varying [*.. \*]|Varchar [*]|  
|Char [*.. \*]|char[*]|  
|character|char|  
|unterschiedliche Zeichen [*.. \*]|Varchar [*]|  
|Zeichen [*.. \*]|char[*]|  
|CLOB|varchar(max)|  
|Datum|datetime2 [0]|  
|dec|dec[38][0]|  
|dec[*..\*]|DEC [*] [0]|  
|dec[*..\*][\*..\*]|dec[*][\*]|  
|Decimal|decimal[38][0]|  
|Dezimal [*.. \*]|Dezimal [*] [0]|  
|decimal[*..\*][\*..\*]|decimal[*][\*]|  
|mit doppelter Genauigkeit|float[53]|  
|float|float[53]|  
|"float" [*.. 53]|"float" [*]|  
|float[54..*]|float[53]|  
|int|int|  
|integer|int|  
|long|varchar(max)|  
|Long raw|varbinary(max)|  
|Long raw [*.. 8000]|varbinary[*]|  
|Long raw [8001.. *]|varbinary(max)|  
|lange varchar|varchar(max)|  
|lange [*.. 8000]|Varchar [*]|  
|long[8001..*]|varchar(max)|  
|National char|NCHAR|  
|National Char varying [*.. \*]|nvarchar[*]|  
|National Char [*.. \*]|nchar[*]|  
|nationale Zeichensätze|NCHAR|  
|nationale Zeichensätze varying [*.. \*]|nvarchar[*]|  
|nationale Zeichensätze [*.. \*]|nchar[*]|  
|NCHAR|NCHAR|  
|nchar[*]|nchar[*]|  
|NCLOB|nvarchar(max)|  
|number|float[53]|  
|Anzahl [*.. \*]|numeric[*]|  
|number[*..\*][\*..\*]|numeric[*][\*]|  
|numeric|numeric|  
|numeric[*..\*]|numeric[*]|  
|numeric[*..\*][\*..\*]|numeric[*][\*]|  
|nvarchar2[*..\*]|nvarchar[*]|  
|Rohdaten [*.. \*]|varbinary[*]|  
|real|float[53]|  
|rowid|uniqueidentifier|  
|smallint|smallint|  
|timestamp|datetime2|  
|Zeitstempel mit der lokalen Zeitzone|datetimeoffset|  
|Zeitstempel mit der lokalen Zeitzone [*.. \*]|datetimeoffset[*]|  
|Zeitstempel mit Zeitzone|datetimeoffset|  
|Zeitstempel mit Zeitzone [*.. \*]|datetimeoffset[*]|  
|timestamp[*..\*]|datetime2 [*]|  
|UROWID|uniqueidentifier|  
|urowid[*..\*]|uniqueidentifier|  
|Varchar [*.. \*]|Varchar [*]|  
|varchar2[*..\*]|Varchar [*]|  
|Xmltype|xml|  
  
### <a name="default-local-variable-type-mapping"></a>Standardtypmapping lokale Variablen  
Die folgende Tabelle enthält die Standard-Typzuordnung für lokale Variablen.  
  
|DB2-Datentyp|Standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] -Datentyp|  
|-----------------|-------------------------------------------------------------------------|  
|BFILE|varbinary(max)|  
|binary_double|float[53]|  
|binary_float|float[53]|  
|binary_interger|int|  
|Blob|varbinary(max)|  
|Boolean|bit|  
|Char|char|  
|Char varying [*.. 8000]|Varchar [*]|  
|char varying[8001..*]|varchar(max)|  
|Char [*.. 8000]|char[*]|  
|char[8001..*]|varchar(max)|  
|Zeichen|char|  
|unterschiedliche Zeichen [*.. 8000]|Varchar [*]|  
|unterschiedliche Zeichen [8001.. *]|varchar(max)|  
|Zeichen [*.. 8000]|char[*]|  
|character[8001..*]|varchar(max)|  
|CLOB|varchar(max)|  
|Datum|datetime2 [0]|  
|dec|dec[38][0]|  
|dec[*..\*]|DEC [*] [0]|  
|dec[*..\*][\*..\*]|dec[*][\*]|  
|Decimal|decimal[38][0]|  
|Dezimal [*.. \*]|Dezimal [*] [0]|  
|decimal[*..\*][\*..\*]|decimal[*][\*]|  
|mit doppelter Genauigkeit|float[53]|  
|Float|float[53]|  
|"float" [*.. 53]|"float" [*]|  
|float[54..*]|float[53]|  
|int|int|  
|Integer|int|  
|ganze Zahl [*.. \*]|numeric[*][0]|  
|Long|varchar(max)|  
|Long raw|varbinary(max)|  
|Long raw [*.. 8000]|varbinary[*]|  
|Long raw [8001.. *]|varbinary(max)|  
|National char|NCHAR|  
|National Char varying [*.. 4000]|nvarchar[*]|  
|National Char varying [4001.. *]|nvarchar(max)|  
|National Char [*.. 4000]|nchar[*]|  
|National Char [4001.. *]|nvarchar(max)|  
|nationale Zeichensätze|NCHAR|  
|nationale Zeichensätze [*.. 4000]|nvarchar[*]|  
|nationale Zeichensätze [4001.. *]|nvarchar(max)|  
|nationale Zeichensätze varying [*.. 4000]|nvarchar[*]|  
|nationale Zeichensätze varying [4001.. *]|nvarchar(max)|  
|Nchar|NCHAR|  
|NCHAR [*.. 4000]|nchar[*]|  
|nchar[4001..*]|nvarchar(max)|  
|NCHAR varying [*.. 4000]|nvarchar[*]|  
|NCHAR varying [4001.. *]|nvarchar(max)|  
|Nclob|nvarchar(max)|  
|Number|float[53]|  
|Anzahl [*.. \*]|numeric[*]|  
|number[*..\*][\*..\*]|numeric[*][\*]|  
|Numerisch|numeric[38][0]|  
|numeric[*..\*]|numeric[*]|  
|numeric[*..\*][\*..\*]|numeric[*][\*]|  
|NVARCHAR2 [*.. 4000]|nvarchar[*]|  
|nvarchar2[4001..*]|nvarchar(max)|  
|pls_integer|int|  
|Rohdaten [*.. 8000]|varbinary[*]|  
|raw[8001..*]|varbinary(max)|  
|Real|float[53]|  
|ROWID|uniqueidentifier|  
|Signtype|smallint|  
|Smallint|smallint|  
|Zeichenfolge [*.. 8000]|Varchar [*]|  
|string[8001..*]|varchar(max)|  
|timestamp|datetime2|  
|Zeitstempel mit der lokalen Zeitzone|datetimeoffset|  
|Zeitstempel mit Zeitzone|datetimeoffset|  
|Zeitstempel mit der lokalen Zeitzone [*.. \*]|datetimeoffset[*]|  
|Zeitstempel mit Zeitzone [*.. \*]|datetimeoffset[*]|  
|timestamp[*..\*]|datetime2 [*]|  
|UROWID|uniqueidentifier|  
|urowid[*..\*]|uniqueidentifier|  
|Varchar [*.. 8000]|Varchar [*]|  
|varchar[8001..*]|varchar(max)|  
|VARCHAR2 [*.. 8000]|Varchar [*]|  
|varchar2[8001..*]|varcha(max)|  
|Xmltype|xml|  
  
## <a name="see-also"></a>Siehe auch  
[Referenz zur Benutzeroberfläche &#40;DB2ToSQL&#41;](../../ssma/db2/user-interface-reference-db2tosql.md)  
  
