---
title: '@@VERSION (Transact-SQL) | Documentos de Microsoft'
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '@@VERSION'
- '@@VERSION_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- '@@VERSION function'
- current SQL Server installation information
- versions [SQL Server], @@VERSION
- processors [SQL Server], types
ms.assetid: 385ba80e-7c28-41a5-9cdb-5648f3785983
caps.latest.revision: 40
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: b8367bb24a37996b2956e3107113812a32086fed
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="version---transact-sql-configuration-functions"></a>Versión - Transact funciones de configuración de SQL
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Devuelve información del sistema y la compilación para la instalación actual de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
@@VERSION  
```  
  
## <a name="return-types"></a>Tipos devueltos  
 **nvarchar**  
  
## <a name="remarks"></a>Comentarios  
 El @@VERSION resultados se presentan como una sola cadena nvarchar. Puede usar el [SERVERPROPERTY &#40; Transact-SQL &#41; ](../../t-sql/functions/serverproperty-transact-sql.md) función para recuperar los valores de propiedad individuales.  
  
 En [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], se devuelve la siguiente información.  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Versión  
  
-   Arquitectura del procesador  
  
-   Fecha de compilación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]  
  
-   Instrucción de copyright  
  
-   Edición de[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]   
  
-   Versión del sistema operativo  
  
 En [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)], se devuelve la siguiente información.  
  
-   Edición: "SQL Database de Microsoft Azure"  
  
-   Nivel de producto: "(CTP)" o "(RTM)"  
  
-   Versión del producto  
  
-   Fecha de compilación  
  
-   Instrucción de copyright  
  
## <a name="examples"></a>Ejemplos  
  
### <a name="a-return-the-current-version-of-includessnoversionincludesssnoversion-mdmd"></a>R: regresar a la versión actual de[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]  
 En el ejemplo siguiente se muestra cómo devolver la información de versión de la instalación actual.  
  
```  
SELECT @@VERSION AS 'SQL Server Version';  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Ejemplos: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] y[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="b-return-the-current-version-of-includessdwincludesssdw-mdmd"></a>B. Devolver la versión actual de[!INCLUDE[ssDW](../../includes/ssdw-md.md)]  
  
```  
SELECT @@VERSION AS 'SQL Server PDW Version';  
```  
  
## <a name="see-also"></a>Vea también  
 [SERVERPROPERTY &#40;Transact-SQL&#41;](../../t-sql/functions/serverproperty-transact-sql.md)  
  
  

