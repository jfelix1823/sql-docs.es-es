---
title: Elemento Password (ASSL) | Microsoft Docs
ms.date: 5/8/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: cc5464e4530e00a0d12807cb0cef2c2e1aa22afa
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2018
ms.locfileid: "38050673"
---
# <a name="password-element-assl"></a>Elemento Password (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Contiene la contraseña de la cuenta de usuario para el [ImpersonationInfo](../../../analysis-services/scripting/data-type/impersonationinfo-data-type-assl.md) elemento.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
  
<ImpersonationInfo  
   ...  
  <Password>...</Password>  
   ...  
</ImpersonationInfo>  
```  
  
## <a name="element-characteristics"></a>Características del elemento  
  
|Característica|Descripción|  
|--------------------|-----------------|  
|Tipo y longitud de los datos|String|  
|Valor predeterminado|None|  
|Cardinalidad|0-1: Elemento opcional que puede aparecer una y solo una vez.|  
  
## <a name="element-relationships"></a>Relaciones del elemento  
  
|Relación|Elemento|  
|------------------|-------------|  
|Elemento primario|[ImpersonationInfo](../../../analysis-services/scripting/data-type/impersonationinfo-data-type-assl.md)|  
|Elementos secundarios|None|  
  
## <a name="remarks"></a>Notas  
 El valor de la **contraseña** elemento, así como el valor de la [cuenta](../../../analysis-services/scripting/properties/account-element-impersonationinfo-assl.md) elemento, se usa para la suplantación si el valor de la [ImpersonationMode](../../../analysis-services/scripting/properties/impersonationmode-element-assl.md) (elemento) para cualquier elemento derivado de la **ImpersonationInfo** tipo de datos está establecido en *ImpersonateAccount*.  
  
 Solo los miembros del rol de administrador del servidor para el [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instancia puede proporcionar un valor en blanco para el **contraseña** elemento  
  
## <a name="see-also"></a>Vea también  
 [Elemento DataSourceImpersonationInfo &#40;ASSL&#41;](../../../analysis-services/scripting/properties/datasourceimpersonationinfo-element-assl.md)   
 [Propiedades &#40;ASSL&#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
