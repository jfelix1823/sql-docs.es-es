---
title: Obtener los parámetros configurables del argumento ADD TARGET | Documentos de Microsoft
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- extended events [SQL Server], ADD TARGET argument
- xe
ms.assetid: 08454543-c5c8-4ca3-9af9-f1d82264471c
caps.latest.revision: 14
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d27a1983d71bd78399893ae63f90e19ca1e0fd08
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36197451"
---
# <a name="get-the-configurable-parameters-for-the-add-target-argument"></a>Obtener los parámetros configurables del argumento ADD TARGET
  Esta tarea se lleva a cabo con el Editor de consultas en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].  
  
 Una vez finalizadas las instrucciones de este procedimiento, la pestaña **Resultados** del Editor de consultas mostrará las columnas siguientes:  
  
-   package_name  
  
-   target_name  
  
-   parameter_name  
  
-   parameter_type  
  
-   required  
  
##  <a name="BeforeYouBegin"></a> Antes de empezar  
 Antes de crear una sesión de eventos extendidos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , resulta útil averiguar qué parámetros pueden establecerse al utilizar el argumento ADD TARGET en CREATE EVENT SESSION o ALTER EVENT SESSION.  
  
### <a name="to-get-the-configurable-parameters-for-the-add-target-argument-using-query-editor"></a>Para obtener los parámetros configurables del argumento ADD TARGET mediante el Editor de consultas.  
  
-   En el Editor de consultas, emita las instrucciones siguientes.  
  
    ```  
    SELECT p.name package_name, o.name target_name, c.name parameter_name,   
    c.type_name parameter_type, CASE c.capabilities_desc WHEN 'mandatory' THEN 'yes' ELSE 'no' END   
    required   
    FROM sys.dm_xe_objects o JOIN sys.dm_xe_packages p ON o.package_guid = p.guid   
    JOIN sys.dm_xe_object_columns c ON o.name = c.object_name AND c.column_type = 'customizable'  
    WHERE o.object_type = 'target'   
    ORDER BY package_name, target_name, required DESC  
    ```  
  
## <a name="see-also"></a>Vea también  
 [CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql)   
 [ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql)   
 [sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql)   
 [sys.dm_xe_packages &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql)  
  
  