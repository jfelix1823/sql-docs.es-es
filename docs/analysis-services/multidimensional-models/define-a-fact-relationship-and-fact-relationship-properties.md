---
title: Definir una relación de hechos y las propiedades de relación de hechos | Documentos de Microsoft
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: multidimensional-models
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 2341335d1d9c4904e1832e0a8087c0fa8198fd58
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
ms.locfileid: "34021702"
---
# <a name="define-a-fact-relationship-and-fact-relationship-properties"></a>Definir relaciones de hechos y propiedades de las relaciones de hechos
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  Al definir una nueva dimensión de cubo o un nuevo grupo de medida, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] intentará detectar si existe una relación de dimensión de hechos y, después, establecerá la configuración del uso de dimensiones en **Fact**. Puede ver o modificar una relación de dimensión de hechos en la pestaña **Uso de dimensiones** del Diseñador de cubos. La relación de hechos entre una dimensión y un grupo de medida presenta las siguientes restricciones:  
  
-   Una dimensión de cubo solamente puede tener una relación de hechos para un determinado grupo de medida.  
  
-   Una dimensión de cubo puede tener relaciones de hechos independientes con varios grupos de medida.  
  
-   El atributo de granularidad de la relación debe ser el atributo clave (como Transaction Number) de la dimensión. De este modo se crea una relación de uno a uno entre la dimensión y los hechos de la tabla de hechos.  
  
  
