---
title: Método getLockTimeout (SQLServerDataSource) | Documentos de Microsoft
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
apiname:
- SQLServerDataSource.getLockTimeout
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 676094e9-ec18-4524-9b21-1f9c5b16dd52
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: feac1b27f0a76492083b4cfcdb63968ff09ac5af
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32834950"
---
# <a name="getlocktimeout-method-sqlserverdatasource"></a>Método getLockTimeout (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Devuelve un **int** valor que indica el número de milisegundos que esperará la base de datos antes de informar de un tiempo de espera de bloqueo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public int getLockTimeout()  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Un **int** valor que contiene el número de milisegundos que esperará la base de datos.  
  
## <a name="remarks"></a>Comentarios  
 El tiempo de espera de bloqueo es el número de milisegundos que hay que esperar antes de que la base de datos informe del tiempo de espera para la exclusión. El valor predeterminado de -1 indica que la espera será indefinida. Si se especifica, este valor será el valor predeterminado para todas las instrucciones de la conexión.  
  
> [!NOTE]  
>  Un valor de 0 indica que el tiempo de espera será nulo. Si no se establece la propiedad lockTimeout, el método getLockTimeout devuelve el valor predeterminado de -1.  
  
## <a name="see-also"></a>Vea también  
 [Miembros SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Clase SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
