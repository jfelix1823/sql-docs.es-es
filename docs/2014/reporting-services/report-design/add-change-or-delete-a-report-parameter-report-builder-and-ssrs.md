---
title: Agregar, cambiar o eliminar parámetros de informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- reporting-services-native
ms.topic: conceptual
ms.assetid: d44a8e0a-10cf-4502-9391-09743ffc9bad
author: maggiesMSFT
ms.author: maggies
manager: craigg
ms.openlocfilehash: c047f968e6fae34b7f4a02d57dbedad38b6d7465
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48082625"
---
# <a name="add-change-or-delete-a-report-parameter-report-builder-and-ssrs"></a>Agregar, cambiar o eliminar parámetros de informe (Generador de informes y SSRS)
  Los parámetros de informe permiten elegir datos de informe, conectar informes relacionados y cambiar la presentación de los informes. Puede proporcionar un valor predeterminado y una lista de valores disponibles, y el usuario puede cambiar la selección.  
  
 Una vez publicado el informe, puede cambiar los valores predeterminados, los valores disponibles y otras propiedades del parámetro en el servidor de informes. Puede proporcionar varios conjuntos de valores de parámetros predeterminados creando informes vinculados. Para obtener más información, vea "Establecer parámetro de propiedades para un informe publicado" en el [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] documentación en [libros en pantalla de SQL Server](http://go.microsoft.com/fwlink/?linkid=120955).  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-or-edit-a-report-parameter"></a>Para agregar o modificar un parámetro de informe  
  
1.  En el panel **Datos de informe** , haga clic con el botón secundario en el nodo **Parámetros** y haga clic en **Agregar parámetro**. Se abrirá el cuadro de diálogo **Propiedades de parámetro de informe** .  
  
2.  En **Nombre**, escriba el nombre del parámetro o acepte el nombre predeterminado.  
  
3.  En **Pedir datos**, escriba el texto que se mostrará junto al cuadro de texto del parámetro cuando el usuario ejecute el informe.  
  
4.  En **Tipo de datos**, seleccione el tipo de datos del valor del parámetro.  
  
5.  Si el parámetro puede contener un valor en blanco, seleccione **Permitir valor en blanco**.  
  
6.  Si el parámetro puede contener un valor NULL, seleccione **Permitir valor NULL**.  
  
7.  Para permitir a los usuarios seleccionar más de un valor para el parámetro, seleccione **Permitir varios valores**.  
  
8.  Establezca la opción de visibilidad.  
  
    -   Para mostrar el parámetro en la barra de herramientas de la parte superior del informe, seleccione **Visible**.  
  
    -   Para ocultar el parámetro con objeto de que no se muestre en la barra de herramientas, seleccione **Oculto**.  
  
    -   Para ocultar el parámetro y evitar que pueda modificarse en el servidor de informes una vez publicado el informe, seleccione **Interno**. De esta forma, el parámetro de informe solamente podrá verse en la definición de informe. Si elige esta opción, debe establecer un valor predeterminado o permitir que el parámetro acepte un valor NULL.  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-report-parameter"></a>Para eliminar un parámetro de informe  
  
1.  En el panel **Datos de informe** , expanda el nodo **Parámetros** .  
  
2.  Haga clic con el botón derecho en el parámetro de informe y, después, haga clic en **Eliminar**.  
  
## <a name="see-also"></a>Vea también  
 [Agregar, cambiar o eliminar valores disponibles para un parámetro de informe &#40;generador de informes y SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md)   
 [Agregar, cambiar o eliminar valores predeterminados para un parámetro de informe &#40;Generador de informes y SSRS&#41;](add-change-or-delete-default-values-for-a-report-parameter.md)   
 [Cambiar el orden de un parámetro de informe &#40;generador de informes y SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)   
 [Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](report-parameters-report-builder-and-report-designer.md)   
 [Ayuda del Generador de informes para cuadros de diálogo, paneles y asistentes](../report-builder-help-for-dialog-boxes-panes-and-wizards.md)   
 [Agregar parámetros en cascada a un informe &#40;generador de informes y SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md)   
 [Tutorial: Agregar un parámetro a un informe &#40;Generador de informes&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md)   
 [Tutoriales &#40;generador de informes&#41;](../report-builder-tutorials.md)   
 [Agregar filtros de conjunto de datos, filtros de región de datos y filtros de grupo &#40;Generador de informes y SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md)   
 [Usar referencias a la colección de parámetros &#40;generador de informes y SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md)   
 [Incorporación de un parámetro de varios valores a un informe](add-a-multi-value-parameter-to-a-report.md)  
  
  
