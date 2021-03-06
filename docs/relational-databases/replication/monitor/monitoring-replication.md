---
title: Supervisión (replicación) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], about monitoring replication
- transactional replication, monitoring
- monitoring [SQL Server replication]
- merge replication monitoring [SQL Server replication]
- snapshot replication [SQL Server], monitoring
- replication [SQL Server], monitoring
- administering replication, monitoring
ms.assetid: f182f43a-6af8-45bc-a708-08d5f7a6984a
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: d3e1b64c1c03a1e81fa83983427efbb60a399418
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47810943"
---
# <a name="monitoring-replication"></a>Supervisar (replicación)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Supervisar una topología de replicación es un aspecto importante en la implementación de la replicación. Debido a que la actividad de replicación se distribuye, es fundamental realizar un seguimiento de la actividad y el estado de todos los equipos que participan en la replicación. Para supervisar la replicación se pueden utilizar las siguientes herramientas:  
  
-   Monitor de replicación de[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]   
  
     El Monitor de replicación es la herramienta más importante para supervisar la replicación, ya que presenta una vista de la actividad de la replicación centrada en el publicador. Para más información, consulte [Monitoring Replication](../../../relational-databases/replication/monitor/monitoring-replication-overview.md).  
  
-   [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]  
  
     [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] proporciona acceso al Monitor de replicación. También permite ver el estado actual y el último mensaje registrado por los siguientes agentes, además de permitir iniciar y detener cada agente: Agente de registro del LOG, Agente de instantáneas, Agente de mezcla y Agente de distribución. Para más información, consulte [Monitor Replication Agents](../../../relational-databases/replication/monitor/monitor-replication-agents.md).  
  
-   [!INCLUDE[tsql](../../../includes/tsql-md.md)] y Replication Management Objects (RMO)  
  
     Ambas interfaces le permiten supervisar todos los tipos de replicación desde el distribuidor. La replicación de mezcla también ofrece la posibilidad de supervisar la replicación desde el suscriptor.  
  
-   Alertas para eventos de agentes de replicación  
  
     La replicación proporciona una serie de alertas predefinidas para los eventos de los agentes de replicación y se pueden crear alertas adicionales si es necesario. Las alertas se pueden utilizar para desencadenar una respuesta automática a un evento y para notificar a un administrador. Para obtener más información, vea [Usar alertas para eventos del Agente de replicación](../../../relational-databases/replication/agents/use-alerts-for-replication-agent-events.md).  
  
-   Monitor de sistema  
  
     El Monitor de sistema puede resultar útil para supervisar el rendimiento, ya que proporciona una serie de contadores para la replicación. Para más información, consulte [Monitoring Replication with System Monitor](../../../relational-databases/replication/monitor/monitoring-replication-with-system-monitor.md).  
  
## <a name="see-also"></a>Ver también  
 [Administración &#40;replicación&#41;](../../../relational-databases/replication/administration/administration-replication.md)   
 [Best Practices for Replication Administration](../../../relational-databases/replication/administration/best-practices-for-replication-administration.md)   
 [Supervisar la replicación](../../../relational-databases/replication/monitor/monitoring-replication-overview.md)  
  
  
