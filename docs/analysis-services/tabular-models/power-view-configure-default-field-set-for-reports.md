---
title: Configurar un conjunto de campos predeterminado para informes de Power View (SSAS Tabular) | Documentos de Microsoft
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ql12.asvs.bidtoolset.deffieldset.f1
ms.assetid: 6836b42f-28b8-4a98-a86d-2c3c109f0189
caps.latest.revision: 7
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: bc0a2fd4178189a072a9b194e502ae1c58de3f92
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="power-view---configure-default-field-set-for-reports"></a>Power View: configurar el conjunto de campos predeterminado para informes
  Un conjunto de campos predeterminado es una lista predefinida de columnas y medidas que se agregan automáticamente a un lienzo de informe [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] cuando se selecciona la tabla en la lista de campos de informes. Los autores de modelos tabulares pueden crear un conjunto de campos predeterminado para eliminar pasos redundantes para los autores de informes que usan el modelo en sus informes. Por ejemplo, si sabe que la mayoría de los autores del informe que trabajan con información de contacto del cliente siempre desean ver un nombre de contacto, un número del teléfono principal, una dirección de correo electrónico y un nombre de compañía, puede pre-seleccionar esas columnas para que siempre se agreguen al lienzo del informe cuando el autor haga clic en la tabla Customer Contact.  
  
> [!NOTE]  
>  Un conjunto de campos predeterminado solo se aplica a un modelo tabular utilizado como modelo de datos en [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)]. Los conjuntos de campos predeterminados no se admiten en los informes dinámicos de Excel.  
  
## <a name="creating-a-default-field-set"></a>Crear un conjunto de campos predeterminado  
 Puede determinar qué campos, si los hay, se incluirán de forma predeterminada cada vez que se seleccione una tabla específica en [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)]. También puede determinar el orden en el que aparecen los campos en la lista. Para especificar un conjunto de campos predeterminado, establezca las propiedades del proyecto de modelo tabular.  
  
#### <a name="to-add-a-default-field-set"></a>Para agregar un conjunto de campos predeterminado  
  
1.  En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], haga clic en la tabla (pestaña) para la que esté configurando una lista de campos predeterminada.  
  
2.  En la ventana **Propiedades** , en la propiedad **Conjunto de campos predeterminado** , haga clic en **Haga clic para editar**.  
  
3.  En el cuadro de diálogo Conjunto de campos predeterminado, seleccione uno o más campos. Puede elegir cualquier campo de la tabla, incluidas las medidas. Mantenga presionada la tecla Mayús para seleccionar un rango, o la tecla Ctrl para seleccionar campos individuales.  
  
4.  Haga clic en **Agregar** para agregarlos al conjunto de campos predeterminado.  
  
5.  Utilice los botones Arriba y Abajo para especificar un orden de la lista de campos. Los campos se agregarán al informe en el orden definido para el conjunto de campos.  
  
6.  Repita estos pasos para otras tablas del libro.  
  
## <a name="next-step"></a>Paso siguiente  
 Después de crear un conjunto de campos predeterminado, puede influir aún más en la experiencia de diseño de informes especificando etiquetas predeterminadas, imágenes predeterminadas, el comportamiento del grupo predeterminado o si las filas que contienen el mismo valor se agrupan en una fila o se enumeran individualmente. Para más información, vea [Configurar las propiedades de comportamiento de las tablas para informes de Power View &#40;SSAS tabular&#41;](../../analysis-services/tabular-models/power-view-configure-table-behavior-properties-for-reports.md).  
  
  