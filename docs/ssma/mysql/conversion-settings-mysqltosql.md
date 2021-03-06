---
title: Configuración de conversión (MySQLToSQL) | Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: f551cf6e-1575-4206-9cca-975b5b43a6b8
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: a311b35597b3c474c2128e73b148ab882f19f42c
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47732323"
---
# <a name="conversion-settings-mysqltosql"></a>Configuración de conversión (MySQLToSQL)
El **'Configuración'** pestaña permite al usuario establecer la configuración del nivel de nodo. La pestaña estará disponible en los siguientes nodos de la Metabase:  
  
-   Nodo de base de datos  
  
-   Categoría de funciones  
  
-   Nodo de función  
  
-   Categoría de tablas  
  
-   Nodo de tabla  
  
## <a name="specifications"></a>Especificaciones:  
El **configuración** pestaña tiene dos configuraciones de usuario, viz.:  
  
1.  Conversión de función  
  
2.  Conversión de la tabla  
  
Estas opciones estarán disponibles en función del tipo de nodo de la Metabase. Por ejemplo, conversión de función relacionados con la configuración no estará disponible en el nodo de tabla  
  
> [!NOTE]  
> -   Los cambios realizados por el usuario se guardará en el área de trabajo del proyecto como un archivo de preferencias independiente.  
> -   La extensión de este archivo será **ccprefs**.  
  
1.  **Configuración de conversión de función:**  
  
    1.  Esta ficha contiene **'Forzar la conversión de la función'** opción. La opción puede tener uno de los siguientes cuatro valores:  
  
        -   Convertir según la configuración de proyecto [heredada]  
  
        -   Convertir siempre a una función  
  
        -   Convertir siempre a un procedimiento  
  
        -   Convertir según la configuración del proyecto  
  
    2.  Según la configuración, la función se convertirá a una función o a un procedimiento almacenado.  
  
    3.  La configuración realizada por el usuario se guarda en el archivo de preferencias en cascada al hacer clic en **aplicar** botón.  
  
2.  **Configuración de conversión de tabla:**  
  
    1.  Esta ficha contiene **'Generación de columna auxiliar suprimir ROWID'** opción. La opción puede tener uno de los siguientes cuatro valores:  
  
        -   Convertir según la configuración de proyecto [heredada]  
  
        -   Sí  
  
        -   no  
  
        -   Convertir según la configuración del proyecto  
  
    2.  Si **'Sí'**, esta configuración prohíbe la creación de la creación de la columna auxiliar ROWID en tablas de destino.  
  
    3.  La configuración realizada por el usuario se guarda en el archivo de preferencias en cascada al hacer clic en **aplicar** botón.  
  
## <a name="see-also"></a>Vea también  
[Configuración del proyecto (conversión) (MySQL a SQL)](http://msdn.microsoft.com/en-us/7ad5fe44-6445-4ba8-a457-5af792631f11)  
  
