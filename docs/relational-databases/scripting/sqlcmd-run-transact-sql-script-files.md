---
title: "Ausführen von Transact-SQL-Skriptdateien mithilfe von „sqlcmd“"
ms.custom: 
ms.date: 07/15/2016
ms.prod: sql-non-specified
ms.prod_service: ssms
ms.service: 
ms.component: scripting
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: transact sql scripts
ms.assetid: 90067eb8-ca3e-44e8-bb1a-bf7d1a359423
caps.latest.revision: "42"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Active
ms.openlocfilehash: 29c0d2c346777e0f5add0c1b4fd03517f5e9c587
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="sqlcmd---run-transact-sql-script-files"></a>Ausführen von Transact-SQL-Skriptdateien mithilfe von „sqlcmd“
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)] Verwenden Sie zum Ausführen einer Transact-SQL-Skriptdatei den Befehl **sqlcmd**. Eine Transact-SQL-Skriptdatei ist eine Textdatei, die eine Kombination aus Transact-SQL-Anweisungen, **sqlcmd** -Befehlen und Skriptvariablen enthalten kann.  

## <a name="create-a-script-file"></a>Erstellen einer Skriptdatei  
 Führen Sie die folgenden Schritte aus, um eine einfache Transact-SQL-Skriptdatei mithilfe des Editors zu erstellen:  
  
1.  Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, zeigen Sie auf **Zubehör**, und klicken Sie dann auf **Editor**.  
  
2.  Kopieren Sie den folgenden Transact-SQL-Code, und fügen Sie ihn im Editor ein:  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT p.FirstName + ' ' + p.LastName AS 'Employee Name',  
    a.AddressLine1, a.AddressLine2 , a.City, a.PostalCode   
    FROM Person.Person AS p   
       INNER JOIN HumanResources.Employee AS e   
            ON p.BusinessEntityID = e.BusinessEntityID  
        INNER JOIN Person.BusinessEntityAddress bea   
            ON bea.BusinessEntityID = e.BusinessEntityID  
        INNER JOIN Person.Address AS a   
            ON a.AddressID = bea.AddressID;  
    GO  
    ```  
  
3.  Speichern Sie die Datei auf dem Laufwerk C unter dem Namen **myScript.sql** .  
  
## <a name="run-the-script-file"></a>Ausführen der Skriptdatei  
  
1.  Öffnen Sie ein Eingabeaufforderungsfenster.  
  
2.  Geben Sie im Eingabeaufforderungsfenster Folgendes ein: **sqlcmd -S myServer\instanceName -i C:\myScript.sql**  
  
3.  Drücken Sie die EINGABETASTE.  
  
 Eine Liste mit Namen und Adressen von Mitarbeitern aus [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] wird in das Eingabeaufforderungsfenster geschrieben.  

## <a name="save-the-output-to-a-text-file"></a>Speichern der Ausgabe in einer Textdatei
  
1.  Öffnen Sie ein Eingabeaufforderungsfenster.  
  
2.  Geben Sie im Eingabeaufforderungsfenster Folgendes ein: **sqlcmd -S myServer\instanceName -i C:\myScript.sql -o C:\EmpAdds.txt**  
  
3.  Drücken Sie die EINGABETASTE.  
  
 In diesem Fall erfolgt keine Ausgabe im Eingabeaufforderungsfenster. Stattdessen erfolgt die Ausgabe in die Datei EmpAdds.txt. Sie können diese Ausgabe prüfen, indem Sie die Datei EmpAdds.txt öffnen.  
  
## <a name="see-also"></a>Siehe auch  
 [Starten des Hilfsprogramms "sqlcmd"](../../relational-databases/scripting/sqlcmd-start-the-utility.md)   
 [sqlcmd (Hilfsprogramm)](../../tools/sqlcmd-utility.md)  
  
  
