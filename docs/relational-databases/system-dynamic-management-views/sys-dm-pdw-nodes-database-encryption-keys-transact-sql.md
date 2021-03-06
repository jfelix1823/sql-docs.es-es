---
title: Sys.dm_pdw_nodes_database_encryption_keys (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: ''
ms.prod_service: sql-data-warehouse, pdw
ms.reviewer: ''
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: e7fd02b2-5d7e-4816-a0af-b58ae2ac3f7a
author: ronortloff
ms.author: rortloff
manager: craigg
monikerRange: '>= aps-pdw-2016 || = azure-sqldw-latest || = sqlallproducts-allversions'
ms.openlocfilehash: 159643e38e7911f1a5403ae7aa1f5b9d88657127
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47727413"
---
# <a name="sysdmpdwnodesdatabaseencryptionkeys-transact-sql"></a>Sys.dm_pdw_nodes_database_encryption_keys (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md.md)]

  Devuelve información sobre el estado de cifrado de una base de datos y sus claves de cifrado de la base de datos asociadas. **Sys.dm_pdw_nodes_database_encryption_keys** proporciona esta información para cada nodo. Para obtener más información acerca del cifrado de base de datos, vea [cifrado transparente de datos (SQL Server PDW)](http://msdn.microsoft.com/b82ad21d-09dd-43dd-8fab-bcf2c8c3ac6d).  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|database_id|**int**|Id. de la base de datos física en cada nodo.|  
|encryption_state|**int**|Indica si la base de datos en este nodo es cifrar o no.<br /><br /> 0 = Ninguna clave de cifrado de la base de datos, sin cifrado<br /><br /> 1 = Sin cifrar<br /><br /> 2 = Cifrado en curso<br /><br /> 3 = Cifrado<br /><br /> 4 = Cambio de clave en curso<br /><br /> 5 = Descifrado en curso<br /><br /> 6 = cambio de protección en curso (el certificado que cifra la clave de cifrado de base de datos se está cambiando).|  
|create_date|**datetime**|Muestra la fecha de creación de la clave de cifrado.|  
|regenerate_date|**datetime**|Muestra la fecha de regeneración de la clave de cifrado.|  
|modify_date|**datetime**|Muestra la fecha de modificación de la clave de cifrado.|  
|set_date|**datetime**|Muestra la fecha de aplicación de la clave de cifrado a la base de datos.|  
|opened_date|**datetime**|Muestra la última vez que se abrió la clave de la base de datos.|  
|key_algorithm|**varchar(?)**|Muestra el algoritmo utilizado por la clave.|  
|key_length|**int**|Muestra la longitud de la clave.|  
|encryptor_thumbprint|**varbin**|Muestra la huella digital del sistema de cifrado.|  
|percent_complete|**real**|Porcentaje completado del cambio de estado del cifrado de la base de datos. Será 0 si no hay ningún cambio de estado.|  
|node_id|**int**|Identificador numérico único asociado al nodo.|  
  
## <a name="permissions"></a>Permisos  
 Necesita el permiso VIEW SERVER STATE en el servidor.  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Ejemplos: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] y [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 El ejemplo siguiente combina `sys.dm_pdw_nodes_database_encryption_keys` a otras tablas del sistema para indicar el estado de cifrado para cada nodo del TDE protegidas las bases de datos.  
  
```  
SELECT D.database_id AS DBIDinMaster, D.name AS UserDatabaseName,   
PD.pdw_node_id AS NodeID, DM.physical_name AS PhysDBName,   
keys.encryption_state  
FROM sys.dm_pdw_nodes_database_encryption_keys AS keys  
JOIN sys.pdw_nodes_pdw_physical_databases AS PD  
    ON keys.database_id = PD.database_id AND keys.pdw_node_id = PD.pdw_node_id  
JOIN sys.pdw_database_mappings AS DM  
    ON DM.physical_name = PD.physical_name  
JOIN sys.databases AS D  
    ON D.database_id = DM.database_id  
ORDER BY D.database_id, PD.pdw_node_ID;  
```  
  
## <a name="see-also"></a>Vea también  
 [Vistas de administración dinámica de almacenamiento de datos en paralelo y SQL Data Warehouse &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)   
 [CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;](../../t-sql/statements/create-database-encryption-key-transact-sql.md)   
 [ALTER DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-encryption-key-transact-sql.md)   
 [DROP DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;](../../t-sql/statements/drop-database-encryption-key-transact-sql.md)  
  
  

