---
title: Transferir instantáneas mediante FTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- replication
ms.topic: conceptual
helpviewer_keywords:
- snapshots [SQL Server replication], FTP snapshots
- FTP snapshots [SQL Server replication]
- snapshot replication [SQL Server], FTP
ms.assetid: 55c30791-cd2a-420b-8ba7-5700e005cb45
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 34cb32b12913f912154ed8fb03f914a6e1abab74
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48225615"
---
# <a name="transfer-snapshots-through-ftp"></a>Transferir instantáneas mediante FTP
  De manera predeterminada, las instantáneas se almacenan en carpetas definidas como recursos compartidos UNC. La replicación también permite especificar un recurso compartido FTP (Protocolo de transferencia de archivos) en lugar de UNC. Para utilizar FTP, debe configurar un servidor FTP y, a continuación, configurar una publicación y una o varias suscripciones para que utilicen FTP. Para obtener información sobre cómo configurar un servidor FTP, vea la documentación de Internet Information Services (IIS). Si especifica información FTP para una publicación, las suscripciones a la misma utilizarán FTP de forma predeterminada. FTP solamente se utiliza con la sincronización web cuando el equipo en que se ejecuta IIS se encuentra separado del distribuidor mediante un firewall. En este caso, FTP se puede utilizar para transferir la instantánea del distribuidor y el equipo que está ejecutando IIS. (La instantánea siempre se transfiere al suscriptor utilizando HTTPS).  
  
> [!IMPORTANT]  
>  Recomendamos utilizar la autenticación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows y un recurso compartido UNC en lugar de un recurso compartido FTP porque las contraseñas de FTP deben guardarse, y dichas contraseñas se envían desde el suscriptor (o el equipo donde se ejecuta IIS cuando se utiliza la sincronización web) al servidor FTP en texto simple. Además, debido a que una sola cuenta controla el acceso al recurso compartido de instantáneas, no es posible garantizar que un suscriptor de una publicación de combinación filtrada tenga acceso únicamente a los archivos de instantáneas de su partición de datos.  
  
 Para entregar una instantánea mediante FTP, vea [Deliver a Snapshot Through FTP](publish/deliver-a-snapshot-through-ftp.md).  
  
## <a name="see-also"></a>Vea también  
 [Sincronización web para la replicación de mezcla](web-synchronization-for-merge-replication.md)   
 [Inicializar una suscripción con una instantánea](initialize-a-subscription-with-a-snapshot.md)   
 [Opciones de instantánea](snapshot-options.md)  
  
  
