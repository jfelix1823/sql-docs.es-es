---
title: Método setApplicationName (SQLServerDataSource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDataSource.setApplicationName
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 24d6e48d-53c4-4da2-a6de-1cdff463c9cd
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 54fadc7402489ce4811347d252c061bb2d42e713
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47721489"
---
# <a name="setapplicationname-method-sqlserverdatasource"></a>Método setApplicationName (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Establece el nombre de la aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public void setApplicationName(java.lang.String applicationName)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *applicationName*  
  
 Objeto **String** que contiene el nombre de la aplicación.  
  
## <a name="remarks"></a>Notas  
 El nombre de la aplicación se usa para identificar la aplicación específica en diversas herramientas de creación de perfiles y registros de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Si no se establece el nombre de aplicación, el método getApplicationName devuelve la cadena no localizada "[!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]".  
  
## <a name="see-also"></a>Ver también  
 [Miembros SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Clase SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
