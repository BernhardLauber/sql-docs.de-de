---
title: SQLPostInstallerError Funktion | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: odbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname: SQLPostInstallerError
apilocation: sqlsrv32.dll
apitype: dllExport
f1_keywords: SQLPostInstallerError
helpviewer_keywords: SQLPostInstallerError function [ODBC]
ms.assetid: 4c60d827-b2d2-4f27-b220-daa9e1fcdd8d
caps.latest.revision: "7"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: e1cc79480eb9ef38529612aecb263ee2892a128f
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="sqlpostinstallererror-function"></a>SQLPostInstallerError-Funktion
**Konformität**  
 Version eingeführt: ODBC 3.0  
  
 **Zusammenfassung**  
 **SQLPostInstallerError** bietet einen Mechanismus zum Treiber oder Konvertierer Setup, um eine Bibliothek zum Melden von Fehlern für die **ConfigDriver**, **ConfigDSN**, und **ConfigTranslator**  Funktionen in die Warteschlange der Installer-Fehler. Anwendungen verwenden Sie diese API nicht. Verwenden sie **SQLInstallerError** um den Fehler abzurufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
RETCODE SQLPostInstallerError(  
     DWORD    fErrorCode,  
     LPSTR    szErrorMsg);  
```  
  
## <a name="arguments"></a>Argumente  
 *fErrorCode*  
 [Eingabe] Installer-Fehlercode.  
  
 *von SQLDiagRec()*  
 [Eingabe] Text der Fehlermeldung.  
  
## <a name="returns"></a>Rückgabewert  
 SQL_SUCCESS oder SQL_ERROR zurück.  
  
## <a name="diagnostics"></a>Diagnose  
 **SQLPostInstallerError** Fehlerwerte für sich selbst wird nicht gesendet. Wenn der Fehler zur Installer Fehlerwarteschlange wurde erfolgreich gesendet wurde (abrufbar mit **SQLInstallerError**), wird SQL_SUCCESS zurückgegeben. SQL_ERROR zurückgegeben, wenn der Wert in der *DwErrorCode* Argument ist nicht der angegebenen Installer-Fehlercodes.  
  
## <a name="related-functions"></a>Verwandte Funktionen  
  
|Informationen zu|Finden Sie unter|  
|---------------------------|---------|  
|Hinzufügen, ändern oder Entfernen eines Treibers|[ConfigDriver](../../../odbc/reference/syntax/configdriver-function.md)|  
|Hinzufügen, ändern oder Entfernen von Datenquellen|[ConfigDSN](../../../odbc/reference/syntax/configdsn-function.md)|  
|Festlegen einer Übersetzungsoption|[ConfigTranslator](../../../odbc/reference/syntax/configtranslator-function.md)|
