---
title: Read (Datenbankmodul) | Microsoft Docs
ms.custom: 
ms.date: 7/22/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|data-types
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Read_TSQL
- Read
dev_langs:
- TSQL
helpviewer_keywords:
- Read [Database Engine]
ms.assetid: f2b8207c-b69f-4327-a874-100b3a1f27d8
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 72ebda7a9bd00b44983d29db2ef433c9f7d43f94
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="read-database-engine"></a>Read (Datenbankmodul)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Lesen liest die binäre Darstellung von **SqlHierarchyId** aus den übergebenen **BinaryReader** und legt die **SqlHierarchyId** -Objekt auf diesen Wert. Lesen kann nicht aufgerufen werden, mithilfe von [!INCLUDE[tsql](../../includes/tsql-md.md)]. Verwenden Sie stattdessen CAST oder CONVERT.
  
## <a name="syntax"></a>Syntax  
  
```sql
void Read( BinaryReader r )   
```  
  
## <a name="arguments"></a>Argumente  
*r*  
 Die **BinaryReader** -Objekt, das einen binären Datenstrom in eine binäre Darstellung der entsprechenden erzeugt eine **Hierarchyid** Knoten.  
  
## <a name="return-types"></a>Rückgabetypen
 **CLR-Typ: Void zurückgeben**  
  
## <a name="remarks"></a>Hinweise  
 Lesen wird die Eingabe nicht überprüft werden. Wenn eine ungültige binäre Eingabe gegeben wird, lesen eine Ausnahme ausgelöst. Oder es ist auch erfolgreich und erzeugt ein ungültiges **SqlHierarchyId** Objekt, dessen Methoden zu unvorhersagbaren Ergebnisse führen oder eine Ausnahme ausgelöst werden können.  
  
 Lesen kann nur aufgerufen werden auf einer neu erstellten **SqlHierarchyId** Objekt.  
  
 Lesen wird intern von verwendet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Wenn ist es erforderlich, z. B. beim Schreiben von Daten auf **Hierarchyid** Spalte. Lesen wird außerdem intern aufgerufen, wenn eine Konvertierung zwischen erfolgt **Varbinary** und **Hierarchyid**.  
  
## <a name="examples"></a>Beispiele  
  
```sql
Byte[] encoding = new byte[] { 0x58 };  
MemoryStream stream = new MemoryStream(encoding, false /*not writable*/);  
BinaryReader br = new BinaryReader(stream);  
SqlHierarchyId hid = new SqlHierarchyId();  
hid.Read(br);   
```  
  
## <a name="see-also"></a>Siehe auch  
[Schreibzugriff &#40; Datenbankmodul &#41;](../../t-sql/data-types/write-database-engine.md)  
[ToString &#40; Datenbankmodul &#41;](../../t-sql/data-types/tostring-database-engine.md)  
[CAST und CONVERT &#40;Transact-SQL&#41;](../../t-sql/functions/cast-and-convert-transact-sql.md)  
[hierarchyid-Datentyp-Methodenverweis](http://msdn.microsoft.com/library/01a050f5-7580-4d5f-807c-7f11423cbb06)
  
  
