---
title: Suscripción, Comandos sin distribuir (Suscripción transaccional) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql13.rep.monitor.subscription.performance.f1
ms.assetid: 5451561e-0ce3-4bb5-844a-88cd15b0b371
author: MashaMSFT
ms.author: mathoma
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 6aa7f22cfbc05938b3ff8cf12495fa03b7c8cb4b
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47813973"
---
# <a name="subscription-undistributed-commands-transactional-subscription"></a>Suscripción, Comandos sin distribuir (Suscripción transaccional)
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
  En la pestaña **Comandos sin distribuir** se muestra información sobre le número de comandos de la base de datos de distribución que no se han entregado al suscriptor seleccionado y el tiempo estimado para entregar esos comandos. Para información sobre cómo ver los comandos en la base de datos de distribución, vea [sp_replshowcmds &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-replshowcmds-transact-sql.md).  
  
## <a name="options"></a>Opciones  
 **Número de comandos en la base de datos de distribución en espera de ser aplicados al suscriptor**  
 Número de comandos de la base de datos de distribución que no se han entregado al suscriptor seleccionado. Un comando se compone de una instrucción de lenguaje de manipulación de datos (DML) de Transact-SQL o una instrucción de lenguaje de definición de datos (DDL).  
  
 **Tiempo estimado para aplicar estos comandos según las últimas operaciones**  
 Cantidad estimada de tiempo para entregar comandos al suscriptor. Si este valor es superior al tiempo necesario para generar y aplicar una instantánea en el suscriptor, considere la posibilidad de volver a reinicializar el suscriptor. Para obtener más información, vea [Reinicializar suscripciones](../../relational-databases/replication/reinitialize-subscriptions.md).  
  
## <a name="see-also"></a>Ver también  
 [Iniciar el Monitor de replicación](../../relational-databases/replication/monitor/start-the-replication-monitor.md)   
 [Supervisar el rendimiento con el Monitor de replicación](../../relational-databases/replication/monitor/monitor-performance-with-replication-monitor.md)   
 [Supervisar la replicación](../../relational-databases/replication/monitor/monitoring-replication-overview.md)  
  
  
