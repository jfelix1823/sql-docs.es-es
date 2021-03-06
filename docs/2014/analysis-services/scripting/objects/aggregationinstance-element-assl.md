---
title: Elemento AggregationInstance (ASSL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- AggregationInstance Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
helpviewer_keywords:
- AggregationInstance element
ms.assetid: 2e77e9e1-9f2c-4df4-9aa6-5b7b911016a3
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: aef7afde2cf93d18ad0a567f5a5e1071b7e42ebf
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48177905"
---
# <a name="aggregationinstance-element-assl"></a>Elemento AggregationInstance (ASSL)
  Define una instancia de agregación para una partición.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
  
<AggregationInstances>  
   <AggregationInstance>  
      <AggregationType>...</AggregationType>  
      <AggregationID>...</AggregationID>  
      <Source>...</Source>  
      <Dimensions>...</Dimensions>  
      <Measures>...</Measures>  
      <Annotations>...</Annotations>  
   </AggregationInstance>  
</AggregationInstances>  
```  
  
## <a name="element-characteristics"></a>Características de los elementos  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|Tipo y longitud de los datos|None|  
|Valor predeterminado|None|  
|Cardinalidad|0-n: elemento opcional que puede aparecer más de una vez.|  
  
## <a name="element-relationships"></a>Relaciones del elemento  
  
|Relación|Elemento|  
|------------------|-------------|  
|Elementos primarios|[AggregationInstances](../collections/aggregationinstances-element-assl.md)|  
|Elementos secundarios|[AggregationID](../properties/id-element-assl.md), [AggregationType](../properties/aggregationtype-element-assl.md), [Annotations](../collections/annotations-element-assl.md), [Dimensions](../collections/dimensions-element-assl.md), [Measures](../collections/measures-element-assl.md), [Source](../properties/source-element-binding-assl.md)|  
  
## <a name="remarks"></a>Comentarios  
 Cuando un [partición](partition-element-assl.md) elemento usa un [AggregationDesign](aggregationdesign-element-assl.md) elemento que se va a generar las agregaciones para esa partición, cada [agregación](aggregation-element-assl.md) en el `AggregationDesign` es crea una instancia de esa partición. Varias particiones pueden usar el mismo diseño de agregaciones para generar varias instancias de una agregación definida. El elemento `AggregationInstance` representa una instancia de una agregación definida.  
  
 El elemento correspondiente en el modelo de objetos de Analysis Management Objects (AMO) es <xref:Microsoft.AnalysisServices.AggregationInstance>.  
  
## <a name="see-also"></a>Vea también  
 [Objetos &#40;ASSL&#41;](objects-assl.md)  
  
  
