---
title: Configuración de errores (cuadro de diálogo de estructura de minería de datos) (Analysis Services - datos multidimensionales) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.asvs.miningstructuredialog.general.f1
ms.assetid: d9aa028b-bad9-49c7-a81c-c2150e4dd481
caps.latest.revision: 12
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 95f347b876673bd178f2059136bbbf6e79d8df5a
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36103430"
---
# <a name="error-configuration-mining-structure-dialog-box-analysis-services---multidimensional-data"></a>Configuración de errores (cuadro de diálogo Propiedades de la estructura de minería de datos) (Analysis Services: datos multidimensionales)
  Use la página **Configuración de errores** del cuadro de diálogo **Propiedades de la estructura de minería de datos** de **SQL Server Management Studio** para definir las propiedades de configuración de errores de una estructura de minería de datos en una base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .  
  
## <a name="options"></a>Opciones  
 **Utilizar la configuración predeterminada de error**  
 Seleccione esta opción para utilizar la configuración de errores predeterminada para los objetos en la operación de procesamiento.  
  
 **Acción del error de clave**  
 Elija una de las siguientes acciones que tienen lugar cuando se encuentra una nueva clave que no se puede buscar durante el procesamiento:  
  
-   **Convertir en desconocido** agrega la información del registro en el miembro desconocido.  
  
-   **Descartar registro** excluye la información del registro del procesamiento del objeto.  
  
 **Omitir recuento de errores**  
 Haga en esta opción clic para omitir los errores que se producen durante el procesamiento.  
  
 **Detenerse ante errores**  
 Haga clic en esta opción para detener el procesamiento cuando se producen errores. Esta opción habilita las opciones **Número de errores** y **Acción ante el error** .  
  
 **Número de errores**  
 Escriba el número de errores que se ignorarán antes de que el proceso se detenga.  
  
 **Acción ante el error**  
 Elija una de las siguientes acciones para que se realice cuando el número de errores supere el valor de **Número de errores**:  
  
-   **Detener el procesamiento** finaliza la operación de procesamiento.  
  
-   **Detener el registro** detiene el registro de errores, pero continúa la operación de procesamiento.  
  
 **Clave no encontrada**  
 Especifique una de las siguientes acciones para que se lleve a cabo cuando no se encuentre una clave al procesar un objeto:  
  
-   **Omitir error** omite el error.  
  
-   **Informar y continuar** informa del error y continúa la operación de procesamiento.  
  
-   **Informar y detenerse** informa del error y detiene la operación de procesamiento.  
  
 **Clave duplicada**  
 Especifique una de las siguientes acciones para que se lleve a cabo si se encuentra una clave duplicada al procesar un objeto:  
  
-   **Omitir error** omite el error.  
  
-   **Informar y continuar** informa del error y continúa la operación de procesamiento.  
  
-   **Informar y detenerse** informa del error y detiene la operación de procesamiento.  
  
 **Clave NULL convertida en desconocida**  
 Especifique una de las siguientes acciones para que se lleve a cabo cuando se agregue una clave de miembro NULL al procesar un objeto:  
  
-   **Omitir error** omite el error.  
  
-   **Informar y continuar** informa del error y continúa la operación de procesamiento.  
  
-   **Informar y detenerse** informa del error y detiene la operación de procesamiento.  
  
 **Clave NULL no permitida**  
 Especifique una de las siguientes acciones para que se lleve a cabo cuando se encuentre una clave NULL al procesar un objeto:  
  
-   **Omitir error** omite el error.  
  
-   **Informar y continuar** informa del error y continúa la operación de procesamiento.  
  
-   **Informar y detenerse** informa del error y detiene la operación de procesamiento.  
  
 **Ruta de acceso del registro de errores**  
 Escriba la ruta de acceso completa y un nombre para el archivo de registro de errores.  
  
## <a name="see-also"></a>Vea también  
 [Cuadro de diálogo de propiedades de estructura de minería de datos &#40;Analysis Services: minería de datos&#41;](mining-structure-properties-dialog-analysis-services-data-mining.md)   
 [General &#40;cuadro de diálogo de estructura de minería de datos&#41; &#40;Analysis Services: minería de datos&#41;](general-mining-structure-dialog-box-analysis-services-data-mining.md)  
  
  