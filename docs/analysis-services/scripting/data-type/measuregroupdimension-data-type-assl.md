---
title: Tipo de datos MeasureGroupDimension (ASSL) | Documentos de Microsoft
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: assl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: e449579bc1544f0cc26f181dc67dbec5f9e00f2f
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
ms.locfileid: "34037226"
---
# <a name="measuregroupdimension-data-type-assl"></a>Tipo de datos MeasureGroupDimension (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Define un tipo de datos primitivo abstracto que representa la relación existente entre una dimensión y un grupo de medida.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
  
<MeasureGroupDimension>  
   <CubeDimensionID>...</CubeDimensionID>  
      <Annotations>...</Annotations>  
   <Source>...</Source>  
</MeasureGroupDimension>  
```  
  
## <a name="data-type-characteristics"></a>Características del tipo de datos  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|Tipos de datos base|Ninguno|  
|Tipos de datos derivados|[DataMiningMeasureGroupDimension](../../../analysis-services/scripting/data-type/dataminingmeasuregroupdimension-data-type-assl.md), [DegenerateMeasureGroupDimension](../../../analysis-services/scripting/data-type/degeneratemeasuregroupdimension-data-type-assl.md), [ManyToManyMeasureGroupDimension](../../../analysis-services/scripting/data-type/manytomanymeasuregroupdimension-data-type-assl.md), [ReferenceMeasureGroupDimension](../../../analysis-services/scripting/data-type/referencemeasuregroupdimension-data-type-assl.md), [RegularMeasureGroupDimension](../../../analysis-services/scripting/data-type/regularmeasuregroupdimension-data-type-assl.md)|  
  
## <a name="data-type-relationships"></a>Relaciones entre tipos de datos  
  
|Relación|Elemento|  
|------------------|-------------|  
|Elementos primarios|Ninguno|  
|Elementos secundarios|[Annotations](../../../analysis-services/scripting/collections/annotations-element-assl.md), [CubeDimensionID](../../../analysis-services/scripting/properties/cubedimensionid-element-assl.md), [Source](../../../analysis-services/scripting/properties/source-element-binding-assl.md)|  
|Elementos derivados|[Dimension](../../../analysis-services/scripting/objects/dimension-element-assl.md) ([colección Dimensions](../../../analysis-services/scripting/collections/dimensions-element-assl.md) de [MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md))|  
  
## <a name="remarks"></a>Comentarios  
 Cada **MeasureGroupDimension** es una referencia a una de las dimensiones del cubo. Éstos definen qué dimensiones de cubo se aplican al grupo de medida.  
  
 El conjunto de atributos que se proporcionan determina la granularidad (ámbito) en la que se conocen las medidas del grupo de medida. Por ejemplo, las medidas que representan las ventas de productos están contenidas en el grupo de medida Sales. La información de estas medidas se almacena en el origen de datos subyacente con una granularidad mensual, en vez de semanal o diaria. En este caso, solo debería aparecer listado el atributo Month para el **MeasureGroupDimension** que describe la relación existente entre una dimensión de tiempo y el grupo de medida Sales. En algún caso aislado, la granularidad se podría definir en términos de un conjunto de atributos. Por ejemplo, dado el conjunto de atributos {Day, Week, Month, Year}, donde Day implica Week y Month, pero Week no implica Month, podrían conocerse las medidas contenidas en el grupo de medida Forecasts por Month y Week, pero no por Day.  
  
 Si no se proporciona ningún atributo, es como si solo apareciera en la lista el atributo clave de la dimensión (que define el nivel mínimo de granularidad). Cada partición de un grupo de medida debe tener la misma granularidad. El conjunto de atributos enumerado no debería ser redundante con respecto a las relaciones entre atributos. Por ejemplo, si Month implica Year, la granularidad se define como Month, no como Month y Year.  
  
 Un **MeasureGroupDimension** necesita incluir una jerarquía solo si tiene algo específico que así lo indique. (No hay ninguna manera de seleccionar qué jerarquías se aplican a un grupo de medida determinado). De igual forma, necesita incluir un [MeasureGroupAttribute](../../../analysis-services/scripting/data-type/measuregroupattribute-data-type-assl.md) solo si tiene algo específico que así lo indique.  
  
 Cada jerarquía debe ser un subconjunto de las jerarquías incluidas en [CubeDimension](../../../analysis-services/scripting/data-type/cubedimension-data-type-assl.md). No es posible seleccionar los niveles, aunque algunos se podrían deshabilitar automáticamente dependiendo de la granularidad del grupo de medida.  
  
 El elemento correspondiente en el modelo de objetos de Analysis Management Objects (AMO) es <xref:Microsoft.AnalysisServices.MeasureGroupDimension>.  
  
## <a name="see-also"></a>Vea también  
 [Analysis Services Scripting Language tipos de datos XML & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
