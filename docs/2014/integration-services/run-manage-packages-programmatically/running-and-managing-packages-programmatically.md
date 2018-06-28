---
title: Ejecutar y administrar paquetes mediante programación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- integration-services
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 1a08c75e-ce8c-45ee-81bd-32248bbdb2b2
caps.latest.revision: 24
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: e3e7721296c0d436ad484a1d4bad96caeef83e39
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36112786"
---
# <a name="running-and-managing-packages-programmatically"></a>Ejecutar y administrar paquetes mediante programación
  Si tiene que administrar y ejecutar paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] fuera del entorno de desarrollo, puede manipular los paquetes mediante programación. En este enfoque cuenta con varias opciones:  
  
-   Cargar y ejecutar un paquete existente sin modificarlo.  
  
-   Cargar un paquete existente, volver a configurarlo (por ejemplo, para un origen de datos diferente) y ejecutarlo.  
  
-   Crear un nuevo paquete, agregar y configurar componentes objeto por objeto y propiedad por propiedad, guardarlo y ejecutarlo.  
  
 Puede cargar y ejecutar un paquete existente desde una aplicación cliente con solo escribir unas cuantas líneas de código.  
  
 En esta sección se describe y se muestra cómo ejecutar un paquete existente mediante programación y cómo obtener acceso a la salida del flujo de datos desde otras aplicaciones. Como opción de programación avanzada, puede crear un paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] línea por línea mediante programación como se describe en el tema [Building Packages Programmatically](../building-packages-programmatically/building-packages-programmatically.md) (Generar paquetes mediante programación).  
  
 En esta sección también se tratan otras tareas administrativas que puede realizar mediante programación para administrar paquetes almacenados, paquetes en ejecución y roles de paquete.  
  
## <a name="running-packages-on-the-integration-services-server"></a>Ejecutar paquetes en el Servidor de Integration Services  
 Cuando implemente paquetes en el servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], puede ejecutar paquetes utilizando el espacio de nombres <xref:Microsoft.SqlServer.Management.IntegrationServices>. El ensamblado de Microsoft.SqlServer.Management.IntegrationServices se compila con .NET Framework 3.5. Si está generando una aplicación.NET Framework 4.0, puede que tenga que agregar la referencia de ensamblado directamente al archivo de proyecto.  
  
 También puede utilizar el espacio de nombres para implementar y administrar proyectos de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en el servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]. Para obtener información general de espacio de nombres y los fragmentos de código, vea la entrada del blog sobre [el modelo de objetos administrados de catálogo SSIS](http://go.microsoft.com/fwlink/?LinkId=253122), en blogs.msdn.com.  
  
## <a name="in-this-section"></a>En esta sección  
 [Descripción de las diferencias entre la ejecución local y remota](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md)  
 Describe las diferencias críticas entre ejecutar un paquete localmente o en el servidor.  
  
 [Cargar y ejecutar un paquete local mediante programación](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md)  
 Describe cómo ejecutar un paquete existente desde una aplicación cliente en el equipo local.  
  
 [Cargar y ejecutar un paquete remoto mediante programación](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)  
 Describe cómo ejecutar un paquete existente desde una aplicación cliente y asegurarse de que el paquete se ejecuta en el servidor.  
  
 [Cargar la salida de un paquete local](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
 Describe cómo ejecutar un paquete en el equipo local y cargar la salida del flujo de datos en una aplicación cliente mediante el destino de DataReader y el espacio de nombres DtsClient.  
  
 [Enumerar los paquetes disponibles mediante programación](../run-manage-packages-programmatically/enumerating-available-packages-programmatically.md)  
 Describe cómo detectar los paquetes disponibles administrados por el servicio [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].  
  
 [Administrar paquetes y carpetas mediante programación](../run-manage-packages-programmatically/managing-packages-and-folders-programmatically.md)  
 Describe cómo crear, cambiar de nombre y eliminar paquetes y carpetas.  
  
 [Administrar los paquetes en ejecución mediante programación](../run-manage-packages-programmatically/managing-running-packages-programmatically.md)  
 Describe cómo enumerar los paquetes que se están ejecutando actualmente, examinar sus propiedades y detener un paquete en ejecución.  
  
 [Managing Package Roles Programmatically &#40;SSIS Service&#41;](../run-manage-packages-programmatically/managing-package-roles-programmatically-ssis-service.md) (Administrar roles de paquete mediante programación &#40;servicio SSIS&#41;)  
 Describe cómo obtener o establecer información sobre los roles asignados a un paquete o una carpeta.  
  
## <a name="reference"></a>Referencia  
 [Referencia de errores y mensajes de Integration Services](../integration-services-error-and-message-reference.md)  
 Muestra los códigos de error predefinidos de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] con sus nombres simbólicos y sus descripciones.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Ampliar paquetes con scripting](../extending-packages-scripting/extending-packages-with-scripting.md)  
 Explica cómo extender el flujo de control mediante la tarea Script y cómo extender el flujo de datos mediante el componente de script.  
  
 [Ampliar paquetes con objetos personalizados](../extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
 Explica cómo crear tareas personalizadas de programa, componentes de flujo de datos y otros objetos de paquete para su uso en varios paquetes.  
  
 [Compilar paquetes mediante programación](../building-packages-programmatically/building-packages-programmatically.md)  
 Explica cómo crear, configurar y guardar los paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] mediante programación.  
  
![Icono de Integration Services (pequeño)](../media/dts-16.gif "el icono de Integration Services (pequeño)")**mantenerse actualizado con Integration Services** <br /> Para las últimas descargas, artículos, ejemplos y los vídeos de [!INCLUDE[msCoName](../../includes/msconame-md.md)], así como soluciones seleccionadas de la Comunidad, visite la [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] página en MSDN:<br /><br /> [Visite la página de Integration Services en MSDN](http://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.  
  
## <a name="see-also"></a>Vea también  
 [SQL Server Integration Services](../sql-server-integration-services.md)  
  
  