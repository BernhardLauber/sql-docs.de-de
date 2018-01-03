---
title: Verweisen auf die ADO-Bibliotheken In Visual Basic 6-Anwendungen | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology: "“drivers”"
ms.topic: article
dev_langs: VB
helpviewer_keywords:
- libraries [ADO]
- referencing libraries in a Visual Basic application[ADO]
- ADO, libraries
ms.assetid: cfd37a82-aad2-41cd-8d13-1566c43d95f0
caps.latest.revision: "12"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: eee5dea5945d48b4fd9a2d40380c61c632d02410
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="referencing-the-ado-libraries-in-a-visual-basic-6-application"></a>Verweisen auf die ADO-Bibliotheken In Visual Basic 6-Anwendungen
Um die ADO-Bibliotheken in eine Microsoft Visual Basic 6-Anwendung importieren, müssen Sie einen Verweis in Visual Basic-Projekt festlegen.  
  
### <a name="to-set-a-reference-to-the-ado-libraries-in-a-visual-basic-project"></a>Einen Verweis auf die ADO-Bibliotheken in Visual Basic-Projekt festlegen  
  
1.  Erstellen Sie ein neues oder öffnen Sie ein vorhandenes Visual Basic-Projekt.  
  
2.  Klicken Sie auf die **Projekt** Menüelement und wählen Sie dann **Verweise...**  aus dem Dropdown-Menü Bereich.  
  
3.  Von **Verfügbare Verweise**, aktivieren Sie das Kontrollkästchen für **Microsoft ActiveX Data Objects *ist n.n* Bibliothek**, wobei ***ist n.n*** stellt die neuesten Versionsnummer. Die **Speicherort** Feld unten sollten Identifizieren Ihrer Wahl als *$installDir\msado15.dll*, wobei *$installDir* bezeichnet den Pfad des Verzeichnisses, in dem die ADO-Bibliothek wurde installiert.  
  
4.  Wenn Sie ADO MD verwenden möchten, wiederholen Sie Schritt 3 auswählen **Microsoft ActiveX Data Objects (Multi-dimensional) *ist n.n* Bibliothek**. Die **Speicherort** Feld sollte diese Auswahl als identifizieren *$installDir\msadomd.dll*.  
  
5.  Wenn Sie ADOX verwenden möchten, wiederholen Sie Schritt 3 auswählen **Microsoft ADO automatischer *ist n.n* für DDL-Befehle und Sicherheit**. Die **Speicherort** Feld sollte diese Auswahl als identifizieren *$installDir\msadox.dll*.  
  
6.  Klicken Sie auf **OK** abgeschlossen, die Verweise festlegen.  
  
## <a name="backward-compatibility"></a>Backward Compatibility  
 Installieren von ADO wird außerdem die folgenden Typbibliotheken früherer Versionen kopiert:  
  
-   *msado27.tlb*, Version 2.7 ADO-Typbibliothek  
  
-   *msado26.tlb*, ADO 2.6-Typbibliothek  
  
-   *msado25.tlb*, ADO 2.5-Typbibliothek  
  
-   *MSADO21*, 2,1 ADO-Typbibliothek  
  
-   *msado20.tlb*, ADO-2.0-Typbibliothek  
  
 Wenn Ihre Anwendung diese ADO-Bibliotheken aus Gründen der Abwärtskompatibilität verwenden muss, müssen Sie die entsprechende Version der Typbibliothek zu importieren. Führen Sie dazu die Verfahren im vorherigen Abschnitt, und Ersetzen Sie dabei *"MSADO15.dll"* von *msadoXX.tlb*, wobei *XX* stellt die Versionsnummer, die Sie importieren müssen.
