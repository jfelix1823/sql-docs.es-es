---
title: Método updateBinaryStream (int, java.io.InputStream) | Microsoft Docs
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
- SQLServerResultSet.updateBinaryStream (java.lang.String, java.io.InputStream, int)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 9be246a7-85fa-49fc-ad79-aabe97f5b280
caps.latest.revision: 21
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 890535e7f58c0f67950b05bec12ba9f1b7d98945
ms.sourcegitcommit: 603d2e588ac7b36060fa0cc9c8621ff2a6c0fcc7
ms.translationtype: MTE75
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2018
ms.locfileid: "42785702"
---
# <a name="updatebinarystream-method-javalangstring-javaioinputstream-int"></a>Método updateBinaryStream (java.lang.String, java.io.InputStream, int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Actualiza la columna designada con un valor de flujo binario, que tendrá el número especificado de bytes.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public void updateBinaryStream(java.lang.String columnLabel,  
                               java.io.InputStream x,  
                               int length)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *columnLabel*  
  
 Valor string que contiene la etiqueta de columna.  
  
 *x*  
  
 Un objeto InputStream.  
  
 *length*  
  
 Valor **int** que indica la longitud del flujo.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Notas  
 Este método updateBinaryStream especificado por el método updateBinaryStream en la interfaz java.sql.ResultSet.  
  
 Este método pasa bytes desde un objeto InputStream a las columnas binarias de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] seleccionadas, como binary, varbinary, varbinary(max), image, xml y udt. Este método no admite la actualización de columnas de caracteres. Para actualizar las columnas de caracteres con un elemento InputStream, use el método [updateAsciiStream](../../../connect/jdbc/reference/updateasciistream-method-sqlserverresultset.md).  
  
 Si la longitud del flujo es distinta a la especificada en el parámetro *length*, el controlador JDBC produce una excepción cuando la fila se actualiza o se inserta.  
  
 Si se desconoce la longitud del flujo, el parámetro *length* puede establecerse en -1 para indicar que el controlador debe aceptar el flujo independientemente de su longitud. Con sqljdbc4.jar, se recomienda usar el [Método updateBinaryStream &#40;java.lang.String, java.io.InputStream&#41;](../../../connect/jdbc/reference/updatebinarystream-method-java-lang-string-java-io-inputstream.md) de JDBC 4.0 si la aplicación quiere actualizar la columna a partir de un flujo cuya longitud se desconoce.  
  
## <a name="see-also"></a>Ver también  
 [Método updateBinaryStream &#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/updatebinarystream-method-sqlserverresultset.md)   
 [Miembros SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Clase SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
