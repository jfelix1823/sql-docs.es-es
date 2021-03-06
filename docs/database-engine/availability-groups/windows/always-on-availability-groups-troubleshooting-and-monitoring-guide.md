---
title: Guía de solución de problemas y supervisión de grupos de disponibilidad Always On (SQL Server) | Microsoft Docs
ms.custom: ag-guide
ms.date: 05/10/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 8d6d9954-ff6b-4e58-882e-eff0174f0d07
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 6a1f55ad47ee17504118b3db5c00e61f39092e34
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47841013"
---
# <a name="always-on-availability-groups-troubleshooting-and-monitoring-guide"></a>Guía de solución de problemas y supervisión de grupos de disponibilidad Always On
 Esta guía le ayudará a empezar a trabajar en la supervisión de grupos de disponibilidad Always On y en la solución de problemas de algunos de los problemas comunes en los grupos de disponibilidad. Proporciona contenido original, así como una página de aterrizaje con información útil que está publicada en otra parte. Aunque esta guía no puede analizar completamente todos los problemas que pueden producirse en todo el área de grupos de disponibilidad, puede orientarle en la dirección correcta en el análisis de la causa principal de los problemas y en su resolución. 
 
 Dado que los grupos de disponibilidad son una tecnología integrada, muchos problemas pueden ser síntomas de otros problemas del sistema de base de datos. Algunos problemas se deben a valores de configuración de un grupo de disponibilidad, como la suspensión de una base de datos de disponibilidad. Otros problemas pueden estar relacionados con otros aspectos de SQL Server, como la configuración, las implementaciones de los archivos de base de datos y los problemas de rendimiento sistémico no relacionados con la disponibilidad de SQL Server. Todavía pueden existir otros problemas fuera de SQL Server, como problemas de la E/S de red, TCP/IP, Active Directory y clústeres de conmutación por error de Windows Server (WSFC). A menudo, los problemas que surgen en un grupo de disponibilidad, una réplica o una base de datos requieren que ejecute la solución de problemas en varias tecnologías para identificar la causa principal.  
  

  
##  <a name="BKMK_SCENARIOS"></a> Escenarios de solución de problemas  
 En la tabla siguiente puede acceder a vínculos a los escenarios de solución de problemas comunes para los grupos de disponibilidad. Se clasifican por sus tipos de escenario, por ejemplo, configuración, conectividad de cliente, conmutación por error y rendimiento.  
  
|Escenario|Tipo de escenario|Descripción|  
|--------------|-------------------|-----------------|  
|[Solucionar problemas de configuración de grupos de disponibilidad Always On &#40;SQL Server&#41;](troubleshoot-always-on-availability-groups-configuration-sql-server.md)|Configuración|Se proporciona información para ayudarle a solucionar los problemas más habituales relacionados con la configuración de las instancias de servidor para grupos de disponibilidad. Algunos de los problemas de configuración más habituales son que los grupos de disponibilidad están deshabilitado, las cuentas no están configuradas correctamente, el extremo de creación de reflejo de la base de datos no existe, el extremo no es accesible (error 1418 de SQL Server), el acceso de red no existe y un comando de unión genera el error 35250 de SQL Server.|  
|[Solucionar problemas relativos a una operación de agregar archivos con error &#40;grupos de disponibilidad Always On&#41;](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)|Configuración|Una operación de agregar archivos ha provocado que la base de datos secundaria se suspenda y esté en el estado NOT SYNCHRONIZING.|  
|[No se puede conectar a la escucha de grupo de disponibilidad en un entorno de varias subredes](http://support.microsoft.com/kb/2792139/en-us)|Conectividad de cliente|Después de configurar la escucha de grupo de disponibilidad, no se puede hacer ping en la escucha ni conectarse a ella desde una aplicación.|  
|[No se han podido solucionar los problemas relacionados con los errores de conmutación por error automática](http://support.microsoft.com/kb/2833707)|Conmutación por error|La conmutación automática por error no se completó correctamente.|  
|[Solución de problemas: el grupo de disponibilidad superó el RTO](troubleshoot-availability-group-exceeded-rto.md)|Rendimiento|Después de una conmutación por error automática o una manual planeada sin pérdida de datos, el tiempo de conmutación por error supera el RTO. O bien, al estimar el tiempo de conmutación por error de una réplica secundaria de confirmación sincrónica (por ejemplo, un asociado de conmutación automática por error), descubre que supera el RTO.|  
|[Solución de problemas: el grupo de disponibilidad superó el RPO](troubleshoot-availability-group-exceeded-rpo.md)|Rendimiento|Después de realizar una conmutación por error manual forzada, la pérdida de datos supera la RPO. O bien, al calcular la posible pérdida de datos de una réplica secundaria de confirmación asincrónica, descubre que supera la RPO.|  
|[Solución de problemas: cambios en la réplica principal que no se reflejan en la réplica secundaria](troubleshoot-primary-changes-not-reflected-on-secondary.md)|Rendimiento|La aplicación cliente finaliza una actualización en la réplica principal correctamente, pero una consulta a la réplica secundaria muestra que el cambio no se ha reflejado.|  
|[Solución de problemas: tipo de espera HADR_SYNC_COMMIT alto con grupos de disponibilidad Always On](https://blogs.msdn.microsoft.com/sql_server_team/troubleshooting-high-hadr_sync_commit-wait-type-with-always-on-availability-groups/)|Rendimiento|Si HADR_SYNC_COMMIT es demasiado largo, hay un problema de rendimiento en el flujo de movimiento de datos o en el refuerzo del registro de réplica secundaria.|  

##  <a name="BKMK_TOOLS"></a> Herramientas útiles para solucionar problemas  
 Al configurar o ejecutar grupos de disponibilidad, las diferentes herramientas pueden ayudarle a diagnosticar diferentes tipos de problemas. En la tabla siguiente se proporcionan vínculos a información útil sobre las herramientas.  
  
|Herramienta|Descripción|  
|----------|-----------------|  
|[Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md)|Ofrece un vistazo al estado del grupo de disponibilidad en una interfaz fácil de usar.|  
|[Directivas de Always On](always-on-policies.md)|Usada por el panel Always On.|  
|[Registro de errores de SQL Server &#40;Grupos de disponibilidad Always On&#41;](sql-server-error-log-always-on-availability-groups.md)|Registra los eventos de transición de estado de kis grupos de disponibilidad, réplicas y bases de datos; estados de otros componentes de Always On y errores de Always On.|  
|[CLUSTER.LOG &#40;Grupos de disponibilidad Always On&#41;](cluster-log-always-on-availability-groups.md)|Registra los eventos de clúster, incluidas las transiciones de estado del recurso del grupo de disponibilidad, así como los eventos y errores del DLL de recursos de SQL Server.|  
|[Registro de diagnóstico de mantenimiento de Always On](always-on-health-diagnostics-log.md)|Registra los diagnósticos de mantenimiento de SQL Server tal y como se notifica al clúster de WSFC (DLL de recursos de SQL Server) y [sp_server_diagnostics &#40;Transact-SQL&#41;](~/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql.md).|  
|[Vistas de administración dinámica y vistas de catálogo del sistema &#40;Grupos de disponibilidad Always On &#40;Transact-SQL&#41;](dynamic-management-views-and-system-catalog-views-always-on-availability-groups.md)|Ofrece información sobre los grupos de disponibilidad, como la configuración, el estado de mantenimiento y las métricas de rendimiento.|  
|[Eventos extendidos de Always On](always-on-extended-events.md)|Proporciona un diagnóstico detallado de los grupos de disponibilidad y un análisis útil para descubrir la causa principal.|  
|[Tipos de espera de Always On](always-on-wait-types.md)|Proporciona estadísticas de espera específicas de los grupos de disponibilidad y útiles para ajustar el rendimiento.|  
|Contadores de rendimiento de Always On|Supervisa la actividad de los grupos de disponibilidad, se reflejan en el monitor de sistema y son útiles para ajustar el rendimiento. Para obtener más información, consulte [SQL Server, réplica de base de datos](~/relational-databases/performance-monitor/sql-server-availability-replica.md) y [SQL Server, réplica de base de datos](~/relational-databases/performance-monitor/sql-server-database-replica.md).|  
|[Búferes de anillo de Always On](always-on-ring-buffers.md)|Registra las alertas del sistema de SQL Server para ofrecer un diagnóstico interno y se puede utilizar para depurar los problemas relacionados con los grupos de disponibilidad.|  
  
##  <a name="BKMK_MONITOR"></a> Supervisar grupos de disponibilidad  
 El momento ideal para solucionar problemas de un grupo de disponibilidad es antes de que un problema necesite una conmutación por error, ya sea automática o manual. Esto puede hacerse supervisando las métricas de rendimiento del grupo de disponibilidad y enviando alertas cuando las réplicas de disponibilidad se realizan fuera de los límites de su contrato de nivel de servicio (SLA). Por ejemplo, si una réplica secundaria sincrónica presenta problemas de rendimiento que hacen aumentar el tiempo estimado de conmutación por error, no le interesa esperar hasta que se produzca una conmutación por error automática y descubra que el tiempo de conmutación por error supera su objetivo de tiempo de recuperación.  
  
 Dado que los grupos de disponibilidad son una solución de alta disponibilidad y recuperación ante desastres, las métricas de rendimiento más importantes para supervisar son el tiempo estimado de conmutación por error, que repercute en su objetivo de tiempo de recuperación (RTO), y la posible pérdida de datos en caso de desastre, que repercute en su objetivo de punto de recuperación (RPO). Puede recopilar estas métricas a partir de los datos que SQL Server expone en un momento dado, por lo que puede recibir alertas de un problema en las capacidades de recuperación de desastres de alta disponibilidad (HADR) del sistema antes de que se produzcan eventos de errores reales. Por lo tanto, es importante familiarizarse con el proceso de sincronización de datos de los grupos de disponibilidad y recopilar las métricas en consecuencia.  
  
 En la siguiente tabla se dirige a temas que pueden ayudarle a supervisar el mantenimiento de su solución para los grupos de disponibilidad.  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[Monitor performance for Always On Availability Groups](monitor-performance-for-always-on-availability-groups.md) (Supervisar el rendimiento de los grupos de disponibilidad Always On)|Describe el proceso de sincronización de datos para los grupos de disponibilidad, puertas de control de flujo y métricas útiles al supervisar un grupo de disponibilidad; y también muestra cómo recopilar métricas de RTO y RPO.|  
|[Supervisión de los grupos de disponibilidad &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md)|Proporciona información sobre herramientas para supervisar un grupo de disponibilidad.|  
|[The Always On health model, part 1: Health model architecture](http://blogs.msdn.com/b/sqlalwayson/archive/2012/02/09/overview-of-the-alwayson-manageability-health-model.aspx) (Modelo de mantenimiento de Always On, parte 1: arquitectura del modelo de mantenimiento)|Proporciona información general sobre el modelo de estado de Always On.|  
|[The Always On health model, part 2: Extending the health model](http://blogs.msdn.com/b/sqlalwayson/archive/2012/02/13/extending-the-alwayson-health-model.aspx) (Modelo de mantenimiento de Always On, parte 2: extender el modelo de mantenimiento)|Muestra cómo personalizar el modelo de mantenimiento de Always On y personalizar el panel de Always On para mostrar información adicional.|  
|[Monitoring Always On health with PowerShell, part 1: Basic cmdlet overview](http://blogs.msdn.com/b/sqlalwayson/archive/2012/02/13/monitoring-alwayson-health-with-powershell-part-1.aspx) (Supervisar el mantenimiento de Always On con PowerShell, parte 1: información general básica de los cmdlets)|Proporciona una introducción básica a los cmdlets de PowerShell en Always On que puede usarse para supervisar el mantenimiento de un grupo de disponibilidad.|  
|[Monitoring Always On health with PowerShell, part 2: Advanced cmdlet usage](http://blogs.msdn.com/b/sqlalwayson/archive/2012/02/13/monitoring-alwayson-health-with-powershell-part-2.aspx) (Supervisar el mantenimiento de Always On con PowerShell, parte 2: uso avanzado de cmdlets)|Proporciona información sobre el uso avanzado de los cmdlets de PowerShell en Always On para supervisar el mantenimiento de un grupo de disponibilidad.|  
|[Monitoring Always On health with PowerShell, part 3: A simple monitoring application](http://blogs.msdn.com/b/sqlalwayson/archive/2012/02/15/monitoring-alwayson-health-with-powershell-part-3.aspx) (Supervisar el mantenimiento de Always On con PowerShell, parte 3: una aplicación de supervisión sencilla)|Muestra cómo supervisar automáticamente un grupo de disponibilidad con una aplicación.|  
|[Monitoring Always On health with PowerShell, part 4: Integration with SQL Server Agent](http://blogs.msdn.com/b/sqlalwayson/archive/2012/02/15/the-always-on-health-model-part-4.aspx) (Supervisar el mantenimiento de Always On con PowerShell, parte 4: integración con el agente SQL Server)|Proporciona información sobre cómo integrar la supervisión del grupo de disponibilidad con el agente SQL Server y cómo configurar notificaciones a las personas adecuadas cuando surjan problemas.|  

## <a name="next-steps"></a>Pasos siguientes  
 [SQL Server Always On Team Blog](http://blogs.msdn.com/b/sqlalwayson/)  (Blog del equipo Always On de SQL Server)  
 [Blogs de los ingenieros de SQL Server de CSS](http://blogs.msdn.com/b/psssql/)  
  
  
