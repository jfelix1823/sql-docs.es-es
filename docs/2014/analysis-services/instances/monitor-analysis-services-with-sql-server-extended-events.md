---
title: Usar SQL Server extendida Events (XEvents) para supervisar Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
ms.assetid: b57cc2fe-52dc-4fa9-8554-5a866e25c6d7
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 5716541be57191cd6bb3e6e6399a354889b2cf58
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48179675"
---
# <a name="use-sql-server-extended-events-xevents-to-monitor-analysis-services"></a>Usar SQL Server Extended Events (XEvents) para supervisar Analysis Services
  Analysis Services proporciona capacidades de seguimiento mediante el uso de [Extended Events](../../relational-databases/extended-events/extended-events.md).  
  
 Eventos extendidos es una infraestructura de eventos con un alto nivel de escalabilidad y configurabilidad para sistemas de servidor. Extended Events es un sistema ligero de supervisión de rendimiento que usa muy pocos recursos de rendimiento.  
  
 Todos los Analysis Services, los eventos se pueden capturar y destinar a usuarios específicos, como se define en [Extended Events](../../relational-databases/extended-events/extended-events.md), con XEvents.  
  
## <a name="initiating-extended-events-in-analysis-services"></a>Iniciar Eventos extendidos en Analysis Services  
 El seguimiento de Eventos extendidos se habilita mediante un comando de script de objeto de creación XMLA similar como se muestra a continuación:  
  
```  
<Execute …>  
   <Command>  
      <Batch …>  
         <Create …>  
            <ObjectDefinition>  
               <Trace>  
                  <ID>trace_id</ID>  
                  <Name>trace_name</Name>  
                  <ddl300_300:XEvent>  
                     <event_session …>  
                        <event package="AS" name="AS_event">  
                           <action package="PACKAGE0" …/>  
                        </event>  
                        <target package="PACKAGE0" name="asynchronous_file_target">  
                           <parameter name="filename" value="data_filename.xel"/>  
                           <parameter name="metadatafile" value="metadata_filename.xem"/>  
                        </target>  
                     </event_session>  
                  </ddl300_300:XEvent>  
               </Trace>  
            </ObjectDefinition>  
         </Create>  
      </Batch>  
   </Command>  
   <Properties></Properties>  
</Execute>  
  
```  
  
 Donde el usuario definirá los siguientes elementos, según las necesidades del seguimiento:  
  
 *trace_id*  
 Define el identificador único de este seguimiento.  
  
 *trace_name*  
 El nombre proporcionado a este seguimiento; normalmente una definición legible del mismo. Es una práctica común usar el valor de *trace_id* como nombre.  
  
 *AS_event*  
 El evento de Analysis Services que se expondrá. Consulte [Eventos de seguimiento de Analysis Services](../trace-events/analysis-services-trace-events.md) para ver los nombres de los eventos.  
  
 *data_filename*  
 El nombre del archivo de datos que contiene los datos de los eventos. Este nombre se añade como sufijo con una marca de tiempo para evitar sobrescribir los datos si el seguimiento se envía repetidamente.  
  
 *metadata_filename*  
 El nombre del archivo de datos que contiene los metadatos de los eventos. Este nombre se añade como sufijo con una marca de tiempo para evitar sobrescribir los datos si el seguimiento se envía repetidamente.  
  
## <a name="stopping-extended-events-in-analysis-services"></a>Detener Eventos extendidos en Analysis Services  
 Para detener el objeto de seguimiento de Eventos extendidos, debe eliminar el objeto utilizando un comando de script de objeto de eliminación XMLA como se muestra a continuación:  
  
```  
<Execute xmlns="urn:schemas-microsoft-com:xml-analysis">  
   <Command>  
      <Batch …>  
         <Delete …>  
            <Object>  
               <TraceID>trace_id</TraceID>  
            </Object>  
         </Delete>  
      </Batch>  
   </Command>  
   <Properties></Properties>  
</Execute>  
  
```  
  
 Donde el usuario definirá los siguientes elementos, según las necesidades del seguimiento:  
  
 *trace_id*  
 Define el identificador único para el seguimiento que se va a eliminar.  
  
## <a name="see-also"></a>Vea también  
 [Eventos extendidos](../../relational-databases/extended-events/extended-events.md)  
  
  
