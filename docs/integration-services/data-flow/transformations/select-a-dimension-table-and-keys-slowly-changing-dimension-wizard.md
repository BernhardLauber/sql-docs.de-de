---
title: "Dimensionstabelle und Schlüssel auswählen (Assistent für langsam veränderliche Dimensionen) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: data-flow
ms.reviewer: 
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: sql13.dts.loaddimwizard.selecttableandkeys.f1
ms.assetid: 01e0495f-de35-4607-ba19-0539e801e8fd
caps.latest.revision: "27"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: b1806a2951e8d2cb41a44a428fe182d14c5999f0
ms.sourcegitcommit: 7f8aebc72e7d0c8cff3990865c9f1316996a67d5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2017
---
# <a name="select-a-dimension-table-and-keys-slowly-changing-dimension-wizard"></a>Dimensionstabelle und Schlüssel auswählen (Assistent für langsam veränderliche Dimensionen)
  Mithilfe der Seite **Dimensionstabelle und Schlüssel auswählen** können Sie eine zu ladende Dimensionstabelle auswählen. Spalten aus dem Datenfluss werden den zu ladenden Spalten zugeordnet.  
  
 Weitere Informationen zu diesem Assistenten finden Sie unter [Slowly Changing Dimension Transformation](../../../integration-services/data-flow/transformations/slowly-changing-dimension-transformation.md).  
  
## <a name="options"></a>enthalten  
 **Verbindungs-Manager**  
 Wählen Sie in der Liste einen vorhandenen OLE DB-Verbindungs-Manager aus, oder erstellen Sie einen neuen OLE DB-Verbindungs-Manager, indem Sie auf **Neu** klicken.  
  
> [!NOTE]  
>  Der Assistent für langsam veränderliche Dimensionen unterstützt nur OLE DB-Verbindungs-Manager und Verbindungen mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
 **Neu**  
 Verwenden Sie das Dialogfeld **OLE DB-Verbindungs-Manager konfigurieren** , um einen vorhandenen Verbindungs-Manager auszuwählen, oder klicken Sie auf **Neu** , um eine neue OLE DB-Verbindung herzustellen.  
  
 **Tabelle oder Sicht**  
 Wählen Sie eine Tabelle oder eine Sicht aus der Liste aus.  
  
 **Eingabespalten**  
 Wählen Sie aus der Liste der Eingabespalten aus, für die Sie Zuordnungen angeben können.  
  
 **Dimensionsspalten**  
 Zeigen Sie alle verfügbaren Dimensionsspalten an.  
  
 **Schlüsseltyp**  
 Wählen Sie eine der Dimensionsspalten aus, die als Geschäftsschlüssel verwendet werden soll. Sie müssen über einen Geschäftsschlüssel verfügen.  
  
## <a name="see-also"></a>Siehe auch  
 [Konfiguration von Ausgaben mithilfe des Assistenten für langsam veränderliche Dimensionen](../../../integration-services/data-flow/transformations/configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
