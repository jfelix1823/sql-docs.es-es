---
title: Recuperar datos mediante XmlReader | Documentos de Microsoft
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- retrieving data
- XmlReader object
- data retrieval [ADOMD.NET], XmlReader object
ms.assetid: 420ec40e-be2d-413a-b4b2-6d2b1756e270
caps.latest.revision: 34
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 257777c40c829921680b8fce333bd6e44f6f57fd
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36108215"
---
# <a name="retrieving-data-using-the-xmlreader"></a>Recuperar datos mediante XmlReader
  La clase `XmlReader`, parte del espacio de nombres `System.Xml` para la Biblioteca de clases de Microsoft .NET Framework, es similar a la clase <xref:Microsoft.AnalysisServices.AdomdClient.AdomdDataReader> en que la clase `XmlReader` también proporciona acceso rápido, sin caché y de solo avance a los datos. Si no es necesaria una vista en memoria y analítica de los datos mediante el objeto <xref:Microsoft.AnalysisServices.AdomdClient.CellSet>, el objeto `XmlReader` es perfecto para recuperar datos XML, especialmente grandes cantidades de datos. Dado que `XmlReader` transmite datos por secuencias, `XmlReader` no tiene que recuperar y almacenar en caché todos los datos antes de exponerlos al autor de las llamada, que sería el caso si se utilizara un objeto <xref:Microsoft.AnalysisServices.AdomdClient.CellSet> para convertir la respuesta de XML for Analysis en una representación de modelo de objetos analítico.  
  
 La clase `XmlReader` proporciona acceso directo a la respuesta de XML for Analysis que recibe ADOMD.NET cuando se llama al método <xref:Microsoft.AnalysisServices.AdomdClient.AdomdCommand.ExecuteXmlReader%2A> del objeto <xref:Microsoft.AnalysisServices.AdomdClient.AdomdCommand>. Debido a que los datos recuperados son XML sin formato, debe analizar los datos y metadatos de forma manual. En cuanto se hayan recuperado los datos, se debería cerrar el objeto `XmlReader`.  
  
## <a name="retrieving-data-and-metadata"></a>Recuperar datos y metadatos  
 Si desea usar la clase `XmlReader` para recuperar datos, siga estos pasos:  
  
1.  **Crear una nueva instancia del objeto.**  
  
     Para crear una nueva instancia de la clase `XmlReader`, llame al método <xref:Microsoft.AnalysisServices.AdomdClient.AdomdCommand.Execute%2A> o <xref:Microsoft.AnalysisServices.AdomdClient.AdomdCommand.ExecuteXmlReader%2A> del objeto <xref:Microsoft.AnalysisServices.AdomdClient.AdomdCommand>.  
  
2.  **Recuperar los datos.**  
  
     Una vez que el comando ejecuta la consulta y devuelve `XmlReader`, debe analizar los datos y metadatos. Los datos y metadatos XML se presentan en el formato nativo que utiliza el proveedor XML for Analysis. Para la mayoría de los proveedores XML for Analysis, el formato nativo es el formato `MDDataSet`. El formato `MDDataSet` proporciona datos y metadatos para conjuntos de celdas en un formato estructurado. Para obtener más información acerca del formato `MDDataSet`, vea la especificación de XML for Analysis.  
  
3.  **Cierre el lector.**  
  
     Siempre se debe llamar al método <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.Close%2A> cuando se haya terminado de utilizar el objeto `XmlReader`. Mientras `XmlReader` está abierto, `XmlReader` tiene uso exclusivo del objeto <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection> que se utilizó para ejecutar el comando. No podrá ejecutar cualquier comando mediante <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection>, incluido crear otro `XmlReader` o <xref:Microsoft.AnalysisServices.AdomdClient.AdomdDataReader>, hasta que cierre el `XmlReader`original.  
  
### <a name="example-of-retrieving-data-from-the-xmlreader"></a>Ejemplo de recuperación de datos desde XmlReader  
 En el ejemplo siguiente se ejecuta un comando y se recuperan los datos como `XmlReader`, generando el contenido del archivo a la consola.  
  
 [!code-csharp[Adomd.NetClient#OutputDataWithXML](../../snippets/csharp/SQL14/adomd.net/adomd.netclient/cs/adomdexample.cs#outputdatawithxml)]  
  
## <a name="see-also"></a>Vea también  
 [Recuperar datos de un origen de datos analíticos](retrieving-data-from-an-analytical-data-source.md)   
 [Recuperar datos mediante el conjunto de celdas](retrieving-data-using-the-cellset.md)   
 [Recuperación de datos mediante AdomdDataReader](retrieving-data-using-the-adomddatareader.md)  
  
  