---
title: 'Paso 1: Generar la utilidad de implementación | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
ms.assetid: 1ff4dcff-89b3-4b99-a725-5f7963e98abf
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: b2bbae058a0e3ecacaa4be9204a822451e1a0602
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48216016"
---
# <a name="step-1-building-the-deployment-utility"></a>Paso 1: generar la utilidad de implementación
  En esta tarea, configurará y generará una utilidad de implementación para el proyecto Deployment Tutorial.  
  
 Antes de generar la utilidad de implementación, debe modificar las propiedades del proyecto Deployment Tutorial. Usará el cuadro de diálogo **Deployment Tutorial Property Pages** (Páginas de propiedades de Deployment Tutorial) para configurar estas propiedades. En este cuadro de diálogo, debe habilitar la capacidad de actualizar configuraciones durante la implementación y especificar que el proceso de creación crea una utilidad de implementación. Después de establecer las propiedades, generará el proyecto.  
  
 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] proporciona un conjunto de ventanas que puede usar para depurar paquetes. Puede ver mensajes de errores, advertencias e información, realizar el seguimiento del estado de paquetes en tiempo de ejecución o ver el progreso y los resultados de los procesos de generación. En esta lección, usará la ventana de resultados para ver el progreso y el resultado de la generación de la utilidad de implementación.  
  
### <a name="to-set-the-deployment-utility-properties"></a>Para establecer las propiedades de la utilidad de implementación  
  
1.  Si [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] no está abierto todavía, haga clic en **Inicio**, seleccione **Todos los programas**, **Microsoft SQL Server**y, después, haga clic en **Business Intelligence Development Studio**.  
  
2.  En el menú **Archivo** , haga clic en **Abrir**y, en **Proyecto o solución**, haga clic en la carpeta **Deployment Tutorial** a continuación, haga clic en **Abrir**y, después, haga doble clic en **Deployment Tutorial.sln**.  
  
3.  En el Explorador de soluciones, haga clic con el botón derecho en Deployment Tutorial y haga clic en **Propiedades**.  
  
4.  En el cuadro de diálogo **Deployment Tutorial Property Pages** (Páginas de propiedades de Deployment Tutorial), expanda Propiedades de configuración y haga clic en Utilidad de implementación.  
  
5.  En el panel derecho de la **Deployment Tutorial Property Pages** diálogo cuadro, compruebe que `AllowConfigurationChanges` está establecido en `true`, establezca `CreateDeploymentUtility` a `true`y, opcionalmente, actualice el valor predeterminado de `DeploymentOutputPath`.  
  
6.  Haga clic en **Aceptar**.  
  
### <a name="to-build-the-deployment-utility"></a>Para generar las propiedades de la utilidad de implementación  
  
1.  En el Explorador de soluciones, haga clic en **Deployment Tutorial**.  
  
2.  En el menú **Ver** , haga clic en **Salida**. De forma predeterminada, la ventana de resultados se encuentra en la esquina inferior izquierda de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].  
  
3.  En el menú **Generar** , haga clic en **Build Deployment Tutorial**(Generar Deployment Tutorial).  
  
4.  En la ventana de resultados, compruebe la siguiente información:  
  
     Generación iniciada: proyecto de SQL Integration Services: Incremental...  
  
     Creando la utilidad de implementación...  
  
     Utilidad de implementación creada.  
  
     Generación completa -- 0 errores, 0 advertencias  
  
     ========== Compilación: 0 correcto, 0 errores, 1 actualizados, 0 omitidos ==========  
  
5.  En el menú **Archivo** , haga clic en **Salir**. Si se le pregunta si quiere guardar los cambios en los elementos de Deployment Tutorial, haga clic en **Sí**.  
  
## <a name="next-task-in-lesson"></a>Siguiente tarea de la lección  
 [Paso 2: Comprobar el paquete de implementación](../integration-services/lesson-2-2-verifying-the-deployment-bundle.md)  
  
![Icono de Integration Services (pequeño)](media/dts-16.gif "icono de Integration Services (pequeño)")**mantenerse actualizado con Integration Services** <br /> Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en MSDN:<br /><br /> [Visite la página de Integration Services en MSDN](http://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.  
  
## <a name="see-also"></a>Vea también  
 [Crear una utilidad de implementación](../../2014/integration-services/create-a-deployment-utility.md)  
  
  
