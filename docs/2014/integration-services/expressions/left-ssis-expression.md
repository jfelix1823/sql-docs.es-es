---
title: LEFT (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
ms.assetid: 5634dbfb-740d-4c93-8fd5-2854cc741327
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 41aef87375e50d40ccdec3b6d80782ab028bbf1f
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48103685"
---
# <a name="left-ssis-expression"></a>LEFT (expresión de SSIS)
  Devuelve el número de caracteres especificado de la parte más a la izquierda de la expresión de caracteres dada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
LEFT(character_expression,number)  
```  
  
## <a name="arguments"></a>Argumentos  
 *character_expression*  
 Expresión de caracteres de la que se van a extraer caracteres.  
  
 *number*  
 Expresión entera que indica el número de caracteres que se van a devolver.  
  
## <a name="result-types"></a>Tipos de resultado  
 DT_WSTR  
  
## <a name="remarks"></a>Comentarios  
 Si *number* es mayor que la longitud de *character_expression*, la función devuelve *character_expression*.  
  
 Si el valor de *number* es cero, la función devuelve una cadena de longitud cero.  
  
 Si el valor de *number* es un número negativo, la función devuelve un error.  
  
 El argumento *number* admite variables y columnas.  
  
 LEFT solo funciona con el tipo de datos DT_WSTR. Un argumento *character_expression* que sea un literal de cadena o una columna de datos con el tipo de datos DT_STR se convertirá implícitamente al tipo de datos DT_WSTR antes de que LEFT realice su operación. Los otros tipos de datos deben convertirse explícitamente al tipo de datos DT_WSTR. Para obtener más información, vea [Tipos de datos de Integration Services](../data-flow/integration-services-data-types.md) y [Conversión &#40;expresión de SSIS&#41;](cast-ssis-expression.md).  
  
 LEFT devuelve un resultado NULL si alguno de los argumentos es NULL.  
  
## <a name="expression-examples"></a>Ejemplos de expresiones  
 En el siguiente ejemplo se utiliza un literal de cadena. El resultado devuelto es `"Mountain"`.  
  
```  
LEFT("Mountain Bike", 8)  
```  
  
## <a name="see-also"></a>Vea también  
 [DERECHA &#40;expresión de SSIS&#41;](right-ssis-expression.md)   
 [Funciones &#40;expresión de SSIS&#41;](functions-ssis-expression.md)  
  
  
