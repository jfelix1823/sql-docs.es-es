---
title: CLOSE (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- CLOSE_TSQL
- CLOSE
dev_langs:
- TSQL
helpviewer_keywords:
- closing cursors
- cursors [SQL Server], closing
- CLOSE statement
ms.assetid: 21546874-97e3-4b93-970f-87c27f6b78c7
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 778c3bdb9fc17a27af4fbc3a7b0fd6e2aa89f402
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47629119"
---
# <a name="close-transact-sql"></a>CLOSE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Cierra un cursor abierto mediante la liberación del conjunto de resultados actual y todos los bloqueos de cursor mantenidos en las filas en las que está colocado. CLOSE deja las estructuras de datos accesibles para que se puedan volver a abrir, pero las capturas y las actualizaciones posicionadas no se permiten hasta que se vuelva a abrir el cursor. CLOSE debe ejecutarse en un cursor abierto, por lo que no se permite en cursores que solo están declarados o que ya están cerrados.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
CLOSE { { [ GLOBAL ] cursor_name } | cursor_variable_name }  
```  
  
## <a name="arguments"></a>Argumentos  
 GLOBAL  
 Especifica que *cursor_name* hace referencia a un cursor global.  
  
 *cursor_name*  
 Es el nombre de un cursor abierto. Si existen un cursor global y otro local denominados *cursor_name*, *cursor_name* hace referencia al cursor global cuando se especifica GLOBAL; en caso contrario, *cursor_name* hace referencia al cursor local.  
  
 *cursor_variable_name*  
 Es el nombre de una variable de cursor asociada a un cursor abierto.  
  
## <a name="examples"></a>Ejemplos  
 En el ejemplo siguiente se muestra la posición correcta de la instrucción `CLOSE` en un proceso de cursores.  
  
```  
DECLARE Employee_Cursor CURSOR FOR  
SELECT EmployeeID, Title FROM AdventureWorks2012.HumanResources.Employee;  
OPEN Employee_Cursor;  
FETCH NEXT FROM Employee_Cursor;  
WHILE @@FETCH_STATUS = 0  
   BEGIN  
      FETCH NEXT FROM Employee_Cursor;  
   END;  
CLOSE Employee_Cursor;  
DEALLOCATE Employee_Cursor;  
GO  
```  
  
## <a name="see-also"></a>Ver también  
 [Cursores](../../relational-databases/cursors.md)   
 [Cursores &#40;Transact-SQL&#41;](../../t-sql/language-elements/cursors-transact-sql.md)   
 [DEALLOCATE &#40;Transact-SQL&#41;](../../t-sql/language-elements/deallocate-transact-sql.md)   
 [FETCH &#40;Transact-SQL&#41;](../../t-sql/language-elements/fetch-transact-sql.md)   
 [OPEN &#40;Transact-SQL&#41;](../../t-sql/language-elements/open-transact-sql.md)  
  
  
