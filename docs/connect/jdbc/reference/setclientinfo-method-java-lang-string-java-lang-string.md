---
title: setClientInfo (método) (java.lang.String, java.lang.String) | Documentos de Microsoft
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 8d050831-8305-48a8-bd22-207932111040
caps.latest.revision: 19
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 054a29d5f4bbc2916b2b06778222e1ee53d66c56
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32843400"
---
# <a name="setclientinfo-method-javalangstring-javalangstring"></a>Método setClientInfo (java.lang.String, java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Establece el valor de la propiedad de información de cliente especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public void setClientInfo (java.lang.String name,  
                           java.lang.String value)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *Nombre*  
  
 Una cadena que contiene el nombre de la propiedad de información de cliente para establecer.  
  
 *value*  
  
 Una cadena que contiene el valor para establecer la propiedad de información de cliente.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Comentarios  
 Este método setClientInfo especificado por el método setClientInfo en la interfaz java.sql.Connection.  
  
 El [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] no admite las propiedades de información de cliente. En el controlador JDBC 2.0, este método genera una advertencia para una propiedad. Las aplicaciones deben utilizar [getWarnings](../../../connect/jdbc/reference/getwarnings-method-sqlserverconnection.md) método de la [SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md) clase para recuperar una advertencia.  
  
## <a name="see-also"></a>Vea también  
 [Método setClientInfo &#40;SQLServerConnection&#41;](../../../connect/jdbc/reference/setclientinfo-method-sqlserverconnection.md)   
 [Miembros de SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [Clase SQLServerConnection](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
