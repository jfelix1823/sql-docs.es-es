---
title: Configuración de la información del dispositivo ATOM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- reporting-services-native
ms.topic: conceptual
ms.assetid: fe4a56a4-5552-423c-85c1-895e2e212fee
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: a424f7af44f6272f0d511a68b1e29d89b90d3372
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48108505"
---
# <a name="atom-device-information-settings"></a>Configuración de la información del dispositivo ATOM
  La configuración de información de dispositivo para la extensión de representación Atom admite el envío de un nombre de una fuente Atom y la codificación de caracteres que se usará.  
  
 En la siguiente tabla se enumera la configuración de información de dispositivo para la representación en un documento de servicio de datos.  
  
|Parámetro|Valor|  
|-------------|-----------|  
|`DataFeed`|Si se especifica, representa la fuente Atom que corresponde al nombre de fuente proporcionado en esta configuración. De lo contrario, representa el documento de servicio Atom para el informe. El identificador único generado automáticamente de la fuente de distribución de datos. Este valor se usa internamente y no se debe cambiar.|  
|**Codificación**|Nombre del organismo Internet Assigned Numbers Authority (IANA) de una codificación de caracteres que es compatible con .NET Framework. El valor predeterminado es `UTF-8`. Entre los ejemplos de otros valores se incluyen ASCII, UTF-7 y UTF-16.|  
  
## <a name="see-also"></a>Vea también  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 [Pasar la configuración de información de dispositivo a las extensiones de representación](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md)   
 [Personalizar los parámetros de extensión de representación en RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md)   
 [Referencia técnica &#40;SSRS&#41;](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
