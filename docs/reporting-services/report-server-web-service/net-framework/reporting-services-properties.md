---
title: Propiedades de Reporting Services | Documentos de Microsoft
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- report servers [Reporting Services], properties
- properties [Reporting Services], about properties
- reports [Reporting Services], properties
- Report Server Web service, properties
- report properties [Reporting Services]
- XML Web service [Reporting Services], properties
- Web service [Reporting Services], properties
- properties [Reporting Services]
ms.assetid: 8c855194-4c20-4ecc-a328-5137d54b560c
caps.latest.revision: 34
author: sabotta
ms.author: asaxton
manager: erikre
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: 3a81e521f0e17404ddfc0ed6d36950d8611ba666
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017

---
# <a name="reporting-services-properties"></a>Propiedades de Reporting Services
  El servidor de informes define un conjunto de propiedades del sistema que son globales al servidor de informes y un conjunto de propiedades de elementos que están asociadas a un elemento individual almacenado en la base de datos del servidor de informes. Las propiedades definidas por el servidor de informes no se pueden eliminar y en algunos casos son de solo lectura. Una aplicación puede extender las propiedades del sistema y las propiedades de los elementos agregando propiedades definidas por el usuario adicionales a las propiedades de los elementos y del sistema.  
  
 Los siguientes métodos de servicio Web recuperar y establecer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] propiedades.  
  
|Método|Acción|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.GetProperties%2A>|Devuelve los valores de una o más propiedades en un elemento de la base de datos del servidor de informes.|  
|<xref:ReportService2010.ReportingService2010.GetSystemProperties%2A>|Devuelve una o más propiedades del sistema.|  
|<xref:ReportService2010.ReportingService2010.SetProperties%2A>|Establece una o varias propiedades de un elemento en la base de datos del servidor de informes.|  
|<xref:ReportService2010.ReportingService2010.SetSystemProperties%2A>|Establece una o más propiedades del sistema.|  
  
## <a name="in-this-section"></a>En esta sección  
  
|Tema|Description|  
|-----------|-----------------|  
|[Propiedades de elemento de servidor de informes](../../../reporting-services/report-server-web-service/net-framework/reporting-services-properties-report-server-item-properties.md)|Describe las propiedades específicas del elemento en [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].|  
|[Propiedades de sistema del servidor de informes](../../../reporting-services/report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md)|Describe las propiedades específicas del sistema en [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].|  
  
## <a name="see-also"></a>Vea también  
 [Creación de aplicaciones con el servicio Web y .NET Framework](../../../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)   
 [Servicio Web de servidor de informes](../../../reporting-services/report-server-web-service/report-server-web-service.md)   
 [Referencia técnica de &#40; SSRS &#41;](../../../reporting-services/technical-reference-ssrs.md)  
  
  