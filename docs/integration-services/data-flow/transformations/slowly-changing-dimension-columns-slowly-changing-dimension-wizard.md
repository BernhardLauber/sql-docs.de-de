---
title: "Spalten von langsam veränderlichen Dimensionen (Assistent für langsam veränderliche Dimensionen) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: data-flow
ms.reviewer: 
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: sql13.dts.loaddimwizard.scdsupport.f1
ms.assetid: 36de99d5-5368-48e0-b876-17e9c6862c6c
caps.latest.revision: "23"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 5cdf56b8da5d4c952c2202264125a9a48461f3e6
ms.sourcegitcommit: 7f8aebc72e7d0c8cff3990865c9f1316996a67d5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2017
---
# <a name="slowly-changing-dimension-columns-slowly-changing-dimension-wizard"></a>Spalten von langsam veränderlichen Dimensionen (Assistent für langsam veränderliche Dimensionen)
  Im Dialogfeld **Spalten von langsam veränderlichen Dimensionen** können Sie für jede Spalte einer langsam veränderlichen Dimension einen Änderungstyp auswählen.  
  
 Weitere Informationen zu diesem Assistenten finden Sie unter [Slowly Changing Dimension Transformation](../../../integration-services/data-flow/transformations/slowly-changing-dimension-transformation.md).  
  
## <a name="options"></a>enthalten  
 **Dimensionsspalten**  
 Wählen Sie eine Dimensionsspalte aus der Liste aus.  
  
 **Änderungstyp**  
 Wählen Sie ein **Festes Attribut**oder einen der beiden Typen von veränderlichen Attributen aus. Verwenden Sie **Festes Attribut** , wenn sich der Wert in einer Spalte nicht ändern soll; [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] behandelt Änderungen dann als Fehler. Verwenden Sie **Veränderliches Attribut** , wenn vorhandene Werte von geänderten Werten überschrieben werden sollen. Verwenden Sie **Verlaufsattribut** , wenn geänderte Werte in neuen Datensätzen gespeichert werden sollen, während die vorigen Datensätze gleichzeitig als veraltet gekennzeichnet werden.  
  
 **Entfernen**  
 Wählen Sie eine Dimensionsspalte aus, und entfernen Sie sie aus der Liste der zugeordneten Spalten, indem Sie auf **Entfernen**klicken.  
  
## <a name="see-also"></a>Siehe auch  
 [Konfiguration von Ausgaben mithilfe des Assistenten für langsam veränderliche Dimensionen](../../../integration-services/data-flow/transformations/configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
