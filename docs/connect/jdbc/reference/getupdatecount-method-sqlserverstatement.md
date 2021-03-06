---
title: getUpdateCount (método) (SQLServerStatement) | Documentos de Microsoft
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
- SQLServerStatement.getUpdateCount
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: e9570228-4500-44b6-b2f1-84ac050b5112
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 4723a0eeadee50480593a39acfe31f47d3d169cd
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32838471"
---
# <a name="getupdatecount-method-sqlserverstatement"></a>getUpdateCount (método) (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Recupera el resultado actual como un recuento de actualización.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public final int getUpdateCount()  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Un **int** que contiene el número de actualizaciones. Si el resultado que se devuelve es un objeto de conjunto de resultados o no hay más resultados, se devolverá -1.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Comentarios  
 Este método getUpdateCount especificado por el método getUpdateCount en la interfaz java.sql.Statement.  
  
## <a name="see-also"></a>Vea también  
 [Miembros SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [Clase SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
