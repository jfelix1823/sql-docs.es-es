---
title: Trabajar con conjuntos de filas de esquema en ADOMD.NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
helpviewer_keywords:
- metadata [ADOMD.NET]
- retrieving metadata
- schema rowsets [ADOMD.NET]
ms.assetid: 7bf75bf8-f1e1-44f6-ac42-c38a681654cf
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: f00e4e22549cf73bf95f538b1d26797d6a8509f1
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48051929"
---
# <a name="working-with-schema-rowsets-in-adomdnet"></a>Trabajar con conjuntos de filas de esquema en ADOMD.NET
  Si necesita más metadatos de los que hay disponibles en el modelo de objetos ADOMD.NET, ADOMD.NET proporciona la capacidad de recuperar toda la variedad disponible de conjuntos de filas de esquema de XML for Analysis (XMLA), OLE DB, OLE DB para OLAP y OLE DB para minería de datos:  
  
 **XML de metadatos de análisis**  
 Los conjuntos de filas de esquema de XML for Analysis proporcionan un método para recuperar información de bajo nivel sobre el servidor. Entre la información disponible se incluyen los orígenes de datos disponibles en el servidor, las palabras clave reservadas por el proveedor, los literales admitidos por el proveedor, etc. Incluso puede utilizar un conjunto de filas de esquema de XML for Analysis para detectar todos los conjuntos de filas de esquema admitidos por el proveedor.  
  
 Para obtener más información: [XML para conjuntos de filas de esquema de análisis](../schema-rowsets/xml/xml-for-analysis-schema-rowsets.md)  
  
 **Metadatos de OLE DB**  
 Los conjuntos de filas de esquema de OLE DB proporcionan un método estándar del sector para recuperar información de diversos proveedores.  
  
 Para obtener más información: [OLE DB Schema Rowsets](../schema-rowsets/ole-db/ole-db-schema-rowsets.md)  
  
 **Metadatos de OLAP**  
 La información de esquema proporcionada para un origen de datos analíticos incluye las bases de datos o los catálogos disponibles en dicho origen de datos, los cubos y los modelos de minería de datos de una base de datos, los roles que existen para los cubos en el origen de datos, etc.  
  
 Para obtener más información: [OLE DB para OLAP Schema Rowsets](../schema-rowsets/ole-db-olap/ole-db-for-olap-schema-rowsets.md)  
  
 **Metadatos de minería de datos**  
 Además de los metadatos de OLAP, pueden recuperarse metadatos de minería de datos mediante conjuntos de filas de esquema. Los conjuntos de filas disponibles muestran información sobre los modelos de minería de datos disponibles en la base de datos, los algoritmos de minería de datos disponibles, los parámetros requeridos por el algoritmo, las estructuras de minería de datos, etc.  
  
 Para obtener más información: [Data Mining Schema Rowsets](../schema-rowsets/data-mining/data-mining-schema-rowsets.md)  
  
 Para recuperar metadatos de cada uno de estos conjuntos de filas de esquema, pase un GUID o un nombre XMLA con el método <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.GetSchemaDataSet%2A> del objeto <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection>.  
  
## <a name="retrieving-metadata-by-passing-guids"></a>Recuperar metadatos al pasar identificadores GUID  
 La clase <xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid> contiene una lista de campos que representan los conjuntos de filas de esquema que suelen admitir con más frecuencia los proveedores y los orígenes de datos analíticos. Para recuperar metadatos generales y específicos de un proveedor a partir de un proveedor u origen de datos analíticos, utilice los GUID incluidos en el objeto <xref:Microsoft.AnalysisServices.AdomdClient.AdomdSchemaGuid> con cualquiera de los métodos siguientes:  
  
-   <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.GetSchemaDataSet%2A>  
  
-   <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.GetSchemaDataSet%2A>  
  
> [!NOTE]  
>  El proveedor de datos de ADOMD.NET expone la información de esquema a través de la funcionalidad proporcionada por su proveedor específico y el origen de datos analíticos. Cada proveedor y origen de datos pueden proporcionar metadatos distintos.  
  
## <a name="retrieving-metadata-by-passing-xmla-names"></a>Recuperar metadatos al pasar nombres XMLA  
 Los métodos siguientes toman como argumentos el nombre de esquema XMLA que identifica la información de esquema que se va a devolver y una matriz de restricciones para las columnas devueltas:  
  
-   <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.GetSchemaDataSet%2A>  
  
-   <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.GetSchemaDataSet%2A>  
  
-   <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.GetSchemaDataSet%2A>  
  
-   <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.GetSchemaDataSet%2A>  
  
 Cada uno de estos métodos devuelve una instancia de un objeto `DataSet` que se rellena con la información de esquema. El objeto `DataSet` pertenece al espacio de nombres `System.Data` de la biblioteca de clases Microsoft .NET Framework.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la función GetActions toma una conexión, el nombre del cubo, una coordenada y un tipo de coordenada, recupera una [de filas MDSCHEMA_ACTIONS](../schema-rowsets/ole-db-olap/mdschema-actions-rowset.md)y devuelve las acciones disponibles en la coordenada seleccionada.  
  
 [!code-csharp[Adomd.NetClient#GetActions](../../snippets/csharp/SQL14/adomd.net/adomd.netclient/cs/adomdexample.cs#getactions)]  
  
## <a name="see-also"></a>Vea también  
 [Recuperación de metadatos de un origen de datos analíticos](retrieving-metadata-from-an-analytical-data-source.md)  
  
  
