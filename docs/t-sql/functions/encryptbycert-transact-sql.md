---
title: ENCRYPTBYCERT (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ENCRYPTBYCERT
- ENCRYPTBYCERT_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- certificates [SQL Server], encryption
- encryption [SQL Server], certificates
- ENCRYPTBYCERT function
ms.assetid: ab66441f-e2d2-4e3a-bcae-bcc09e12f3c1
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 20bb47de8ce928e623f34e4e99874f0598369729
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="encryptbycert-transact-sql"></a>ENCRYPTBYCERT (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Verschlüsselt Daten mit dem öffentlichen Schlüssel eines Zertifikats.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
EncryptByCert ( certificate_ID , { 'cleartext' | @cleartext } )  
```  
  
## <a name="arguments"></a>Argumente  
 *Zertifikat-ID*  
 Die ID eines Zertifikats in der Datenbank. **int**.  
  
 *Klartext*  
 Eine Zeichenfolge mit Daten, die mit dem Zertifikat verschlüsselt werden.  
  
 **@cleartext**  
 Eine Variable vom Typ **Nvarchar**, **Char**, **Varchar**, **binäre**, **Varbinary**, oder **Nchar** mit Daten, die mit dem öffentlichen Schlüssel des Zertifikats verschlüsselt werden.  
  
## <a name="return-types"></a>Rückgabetypen  
 **varbinary** mit einer maximalen Größe von 8.000 Bytes.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion verschlüsselt Daten mit dem öffentlichen Schlüssel eines Zertifikats. Der verschlüsselte Text kann nur mit dem entsprechenden privaten Schlüssel entschlüsselt werden. Solche asymmetrischen Transformationen sind im Vergleich zum Verschlüsseln und Entschlüsseln mit einem symmetrischen Schlüssel sehr aufwändig. Von der asymmetrischen Verschlüsselung wird daher abgeraten, wenn Sie große Datasets, wie z. B. Benutzerdaten in Tabellen, verwenden.  
  
## <a name="examples"></a>Beispiele  
 In diesem Beispiel wird der in `@cleartext` gespeicherte Nur-Text mit dem Zertifikat mit dem Namen `JanainaCert02` verschlüsselt. Die verschlüsselten Daten werden in die `ProtectedData04`-Tabelle eingefügt.  
  
```  
INSERT INTO [AdventureWorks2012].[ProtectedData04]   
    VALUES ( N'Data encrypted by certificate ''Shipping04''',  
    EncryptByCert(Cert_ID('JanainaCert02'), @cleartext) );  
GO  
```  
  
## <a name="see-also"></a>Siehe auch  
 [DECRYPTBYCERT &#40; Transact-SQL &#41;](../../t-sql/functions/decryptbycert-transact-sql.md)   
 [CREATE CERTIFICATE &#40;Transact-SQL&#41;](../../t-sql/statements/create-certificate-transact-sql.md)   
 [ALTER CERTIFICATE &#40; Transact-SQL &#41;](../../t-sql/statements/alter-certificate-transact-sql.md)   
 [DROP CERTIFICATE &#40; Transact-SQL &#41;](../../t-sql/statements/drop-certificate-transact-sql.md)   
 [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](../../t-sql/statements/backup-certificate-transact-sql.md)   
 [Verschlüsselungshierarchie](../../relational-databases/security/encryption/encryption-hierarchy.md)  
  
  
