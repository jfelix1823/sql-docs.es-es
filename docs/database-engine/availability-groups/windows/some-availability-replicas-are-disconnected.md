---
title: Algunas réplicas de disponibilidad están desconectadas | Microsoft Docs
ms.custom: ''
ms.date: 05/17/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql13.swb.agdashboard.agp7allconnected.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: aea808be-6f0f-40c2-9aa2-a2a435ec6443
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: eb026260219ce3f3b258a640ac170280540bbdac
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47640499"
---
# <a name="some-availability-replicas-are-disconnected"></a>Algunas réplicas de disponibilidad están desconectadas
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
## <a name="introduction"></a>Introducción  
  
|||  
|-|-|  
|**Nombre de directiva**|Estado de conexión de las réplicas de disponibilidad|  
|**Problema**|Algunas réplicas de disponibilidad están desconectadas.|  
|**Categoría**|**Advertencia**|  
|**Faceta**|grupo de disponibilidad|  
  
## <a name="description"></a>Descripción  
 Esta directiva acumula el estado de todas las réplicas de disponibilidad y comprueba las que están en estado DISCONNECTED. La directiva está en mal estado cuando cualquier réplica de disponibilidad está en estado DISCONNECTED. De lo contrario, la directiva está en un estado correcto.  
  
> [!NOTE]  
>  Para esta versión de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], la información sobre las posibles causas y soluciones se encuentra en el artículo [Algunas réplicas de disponibilidad están desconectadas](http://go.microsoft.com/fwlink/p/?LinkId=220855) en TechNet Wiki.  
  
## <a name="possible-causes"></a>Posibles causas  
 En este grupo de disponibilidad, al menos una réplica secundaria no está conectada con la réplica principal. El estado de conexión es DISCONNECTED.  
  
## <a name="possible-solution"></a>Solución posible  
 Use el estado de directiva de la réplica de disponibilidad para buscar la réplica de disponibilidad que está en estado DISCONNECTED y, a continuación, resuelva el problema en la réplica de disponibilidad.  
  
## <a name="see-also"></a>Ver también  
 [Información general de los grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](../../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)   
 [Usar el Panel de AlwaysOn &#40;SQL Server Management Studio&#41;](../../../database-engine/availability-groups/windows/use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
