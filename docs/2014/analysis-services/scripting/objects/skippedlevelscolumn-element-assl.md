---
title: El elemento SkippedLevelsColumn (ASSL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- SkippedLevelsColumn Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- SkippedLevelsColumn
helpviewer_keywords:
- SkippedLevelsColumn element
ms.assetid: 6b00a288-99c1-4735-9e6b-cd13ed4fa346
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 9727a5080437352bebbfa9c7ced1cd3c88689113
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48141735"
---
# <a name="skippedlevelscolumn-element-assl"></a>Elemento SkippedLevelsColumn (ASSL)
    
> [!NOTE]  
>  Esta característica no se incluye en esta versión de Microsoft SQL Server. Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan.  
  
 Proporciona los detalles de una columna que almacena el número de niveles omitidos (vacíos) entre cada miembro y su elemento primario.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
  
<DimensionAttribute>  
   ...  
   <SkippedLevelsColumn xsi:type="DataItem">...</SkippedLevelsColumn>  
   ...  
</DimensionAttribute>  
```  
  
## <a name="element-characteristics"></a>Características de los elementos  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|Tipo y longitud de los datos|[DataItem](../data-type/dataitem-data-type-assl.md)|  
|Valor predeterminado|None|  
|Cardinalidad|0-1: Elemento opcional que puede aparecer una y solo una vez.|  
  
## <a name="element-relationships"></a>Relaciones del elemento  
  
|Relación|Elemento|  
|------------------|-------------|  
|Elementos primarios|[DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md)|  
|Elementos secundarios|None|  
  
## <a name="remarks"></a>Comentarios  
 El `SkippedLevelsColumn` elemento solo es aplicable a los atributos primarios (en otras palabras, el valor de la [uso](../properties/usage-element-dimensionattribute-assl.md) (elemento) para el `DimensionAttribute` primario se establece en *primario*). El elemento `SkippedLevelsColumn` contiene la columna o el atributo del atributo primario que almacena el número de niveles omitidos entre cada miembro y su miembro primario. Esto permite jerarquías de elementos primarios y secundarios que están basadas en el atributo primario para omitir niveles entre miembros. Los valores contenidos en esta columna o atributo deben ser enteros no negativos; de lo contrario, se produce un error de procesamiento. Si el elemento `SkippedLevelsColumn` no se especifica o no contiene ningún valor, el miembro actual tiene una profundidad de un nivel por debajo de su miembro primario.  
  
 Para obtener más información sobre la `DataItem` tipo, incluida una tabla de objetos de Analysis Services Scripting Language (ASSL) y las propiedades de la `DataItem` de tabla, vea [tipo de datos DataItem &#40;ASSL&#41;](../data-type/dataitem-data-type-assl.md).  
  
 El elemento que se corresponde con el elemento primario de `SkippedLevelsColumn` en el objeto de Analysis Management Objects (AMO) es el modelo <xref:Microsoft.AnalysisServices.DimensionAttribute>.  
  
## <a name="see-also"></a>Vea también  
 [Atributos de elemento &#40;ASSL&#41;](../collections/attributes-element-assl.md)   
 [Elemento de dimensión &#40;ASSL&#41;](dimension-element-assl.md)   
 [Objetos &#40;ASSL&#41;](objects-assl.md)  
  
  
