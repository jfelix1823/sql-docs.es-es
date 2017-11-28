---
title: Sys.dm_xe_packages (Transact-SQL) | Documentos de Microsoft
ms.custom: 
ms.date: 08/09/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- dm_xe_packages_TSQL
- sys.dm_xe_packages_TSQL
- dm_xe_packages
- sys.dm_xe_packages
dev_langs: TSQL
helpviewer_keywords:
- sys.dm_xe_packages dynamic management view
- extended events [SQL Server], views
ms.assetid: 2e5ecbe9-3ea8-45e6-a161-e31671a03e1d
caps.latest.revision: "24"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: d44f313bcb4f199d43305cd9752dda71db5da980
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmxepackages-transact-sql"></a>sys.dm_xe_packages (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Enumera todos los paquetes registrados con el motor de extended events.  
  
 
|Nombre de columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|name|**nvarchar (60)**|El nombre del paquete. La descripción se expone a partir del propio paquete. No admite valores NULL.|  
|
          guid|**uniqueidentifier**|GUID que identifica el paquete. No admite valores NULL.|  
|description|**nvarchar(256)**|Descripción del paquete. establecida por el autor del paquete descriptionis y no acepta valores NULL.|  
|capabilities|**int**|Mapa de bits que describe la funcionalidad de este paquete. Acepta valores NULL.|  
|capabilities_desc|**nvarchar(256)**|Lista de toda la funcionalidad posible de este paquete. Acepta valores NULL.|  
|module_guid|**uniqueidentifier**|GUID del módulo que expone este paquete. No admite valores NULL.|  
|module_address|**varbinary (8)**|La dirección base donde se carga el módulo que contiene el paquete. Un módulo único puede exponer varios paquetes. No admite valores NULL.|  
  
## <a name="permissions"></a>Permissions  
 es necesario contar con el permiso VIEW SERVER STATE en el servidor.  
  
## <a name="remarks"></a>Comentarios  
 Los paquetes registrados con el motor de Extended Events exponen eventos, acciones que se pueden realizar en el momento de la activación de los eventos, y destinos para el procesamiento sincrónico y asincrónico de datos de eventos.  
  
 Estos paquetes se pueden cargar dinámicamente en un espacio de direcciones del proceso. En el momento de cargarse el paquete, registra todos los objetos que expone con el motor de eventos extendidos.  
  
## <a name="relationship-cardinalities"></a>Cardinalidades de relación  
  
||||  
|-|-|-|  
|De|En|Relación|  
|sys.dm_xe_packages.module_address|sys.dm_os_loaded_modules.base_address|Varios a uno|  
  
## <a name="see-also"></a>Vea también  
 [Funciones y vistas de administración dinámica &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)  
  
  
