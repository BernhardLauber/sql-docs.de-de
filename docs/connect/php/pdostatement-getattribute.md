---
title: PDOStatement::getAttribute | Microsoft Docs
ms.custom: 
ms.date: 07/13/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: php
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41d0cca3-8556-4573-bb90-8e9402d9379f
caps.latest.revision: "10"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 01332bc8166f2f242e4daffdd7204bbd5efe11de
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="pdostatementgetattribute"></a>PDOStatement::getAttribute
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Ruft den Wert eines vordefinierten PDOStatement-Attributs oder ein benutzerdefiniertes Treiber-Attributs ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
mixed PDOStatement::getAttribute( $attribute );  
```  
  
#### <a name="parameters"></a>Parameter  
$*Attribut*: eine ganze Zahl, eine der Konstanten PDO:: attr_ * oder PDO:: sqlsrv_attr_\* Konstanten. Unterstützte Attribute sind die Attribute, die einstellbaren mit [pdostatement:: setAttribute](../../connect/php/pdostatement-setattribute.md), PDO:: sqlsrv_attr_direct_query (Weitere Informationen finden Sie unter [direkte Anweisungsausführung und vorbereitete Anweisungsausführung im der PDO_SQLSRV-Treiber](../../connect/php/direct-statement-execution-prepared-statement-execution-pdo-sqlsrv-driver.md)), PDO:: attr_cursor und sqlsrv_attr_cursor_scroll_type (Weitere Informationen finden Sie unter [Cursortypen (PDO_SQLSRV-Treiber)](../../connect/php/cursor-types-pdo-sqlsrv-driver.md)).  
  
## <a name="return-value"></a>Rückgabewert  
Bei Erfolg wird ein (gemischter) Wert für ein vordefiniertes PDO-Attribut oder ein benutzerdefiniertes Treiber-Attribut zurückgegeben. Gibt bei einem Fehler NULL zurück.  
  
## <a name="remarks"></a>Hinweise  
Ein Beispiel hierzu finden Sie unter [PDOStatement::setAttribute](../../connect/php/pdostatement-setattribute.md) .  
  
Unterstützung für PDO wurde in Version 2.0 von [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)]hinzugefügt.  
  
## <a name="see-also"></a>Siehe auch  
[PDOStatement-Klasse](../../connect/php/pdostatement-class.md)  
[PDO](http://go.microsoft.com/fwlink/?LinkID=187441)  
  
