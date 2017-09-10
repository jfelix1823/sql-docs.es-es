---
title: Cubo de almacenamiento (Analysis Services - datos multidimensionales) | Documentos de Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- measure groups [Analysis Services], cubes
- cubes [Analysis Services], storage
- linked measure groups [Analysis Services]
- storing data [Analysis Services], cubes
- partitions [Analysis Services], cubes
- storage [Analysis Services], cubes
ms.assetid: 1b1ad360-9a9b-4996-bee9-84238a2bb4ac
caps.latest.revision: 41
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 27b0e9be1051b6abab2e0be7b0e521e9a5b54567
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="cube-storage-analysis-services---multidimensional-data"></a>Almacenamiento de cubos (Analysis Services - Datos multidimensionales)
  Puede que el almacenamiento solamente incluya metadatos del cubo o puede que incluya todos los datos de origen de la tabla de hechos y las agregaciones definidas por dimensiones relacionadas con el grupo de medida. La cantidad de datos almacenados varía en función del modo de almacenamiento seleccionado y el número de agregaciones. La cantidad de datos almacenados afecta directamente al rendimiento de las consultas. [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usa varias técnicas para minimizar el espacio necesario para el almacenamiento de datos del cubo y las agregaciones:  
  
-   Las opciones de almacenamiento permiten seleccionar las ubicaciones y los modos de almacenamiento más adecuados a los datos del cubo.  
  
-   Un sofisticado algoritmo diseña eficientes agregaciones de resumen para minimizar el almacenamiento sin que se pierda velocidad.  
  
-   No se asigna almacenamiento a las celdas vacías.  
  
 El almacenamiento se define de partición en partición, existiendo al menos una partición para cada grupo de medida de un cubo. Para obtener más información, vea [particiones &#40; Analysis Services - datos multidimensionales &#41; ](../../analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md), [Modos de almacenamiento y procesamiento de la partición](../../analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md), [medidas y grupos de medida](../../analysis-services/multidimensional-models/measures-and-measure-groups.md), y [crear medidas y grupos de medida en modelos multidimensionales](../../analysis-services/multidimensional-models/create-measures-and-measure-groups-in-multidimensional-models.md) .  
  
## <a name="partition-storage"></a>Almacenamiento de particiones  
 El almacenamiento de un grupo de medida se puede dividir en varias particiones. Las particiones permiten distribuir un grupo de medida en segmentos discretos en un solo servidor o en varios servidores, y optimizar el almacenamiento y el rendimiento de las consultas. Cada partición de un grupo de medida se puede basar en un origen de datos diferente y se puede almacenar mediante distintos valores de almacenamiento.  
  
 Al crear una partición se especifica el origen de datos para ella. También puede cambiar el origen de datos de cualquier partición existente. En un grupo de medida se pueden crear particiones vertical u horizontalmente. Cada partición de un grupo de medida con particiones creadas verticalmente se basa en la vista filtrada de una única tabla de origen. Por ejemplo, si un grupo de medida se basa en una única tabla que contiene varios años de datos, se puede crear una partición independiente para los datos de cada año. Por el contrario, cada partición de un grupo de medida con particiones creadas horizontalmente se basa en una tabla independiente. Las particiones horizontales se utilizan si el origen de datos almacena los datos de cada año en una tabla independiente.  
  
 Las particiones se crean inicialmente con la misma configuración de almacenamiento que el grupo de medida en el que se han creado. La configuración de almacenamiento determina si los datos de agregación y detalle se almacenan en formato multidimensional en la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], en formato relacional en el servidor de origen o en una combinación de ambos. La configuración de almacenamiento también determina si se utiliza el almacenamiento en caché automático para procesar automáticamente los cambios de datos de origen en los datos multidimensionales almacenados en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].  
  
 Las particiones de un cubo no son visibles para el usuario. Sin embargo, puede que la elección de configuración de almacenamiento para distintas particiones afecte a la inmediatez de los datos, la cantidad de espacio en disco que se utiliza y el rendimiento de las consultas. Las particiones se pueden almacenar en varias instancias de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]. Con ello se proporciona un método de agrupación en clústeres para el almacenamiento de los cubos y se distribuye la carga de trabajo entre varios servidores de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]. Para obtener más información, consulte [procesamiento y modos de almacenamiento de partición](../../analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md), [las particiones remotas](../../analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-remote-partitions.md), y [particiones &#40; Analysis Services - datos multidimensionales &#41; ](../../analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md).  
  
## <a name="linked-measure-groups"></a>Grupos de medida vinculados  
 Puede que se necesite gran cantidad de espacio en disco para almacenar varias copias de un cubo en distintas instancias de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], pero se puede reducir considerablemente el espacio necesario si se reemplazan las copias del grupo de medida por grupos de medida vinculados. Un grupo de medida vinculado se basa en un grupo de medida de un cubo de otra base se datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], en la misma instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] o en otra instancia. Un grupo de medida vinculado también se puede utilizar con dimensiones vinculadas del mismo cubo de origen. Las dimensiones y grupos de medida vinculados utilizan las agregaciones del cubo de origen o no tienen requisitos de almacenamiento de datos propios. Por lo tanto, al mantener las dimensiones y los grupos de medida de origen en una base de datos, y crear dimensiones y cubos vinculados en cubos de otras bases de datos, se puede ahorrar espacio en disco que de lo contrario se utilizaría para almacenamiento. Para obtener más información, consulte [grupos de medida vinculados](../../analysis-services/multidimensional-models/linked-measure-groups.md).  
  
## <a name="see-also"></a>Vea también  
 [Agregaciones y diseños de agregaciones](../../analysis-services/multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md)  
  
  