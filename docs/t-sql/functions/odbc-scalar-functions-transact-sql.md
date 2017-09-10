---
title: Funciones escalares de ODBC (Transact-SQL) | Documentos de Microsoft
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- CURDATE ODBC function
- DAYOFMONTH ODBC function
- WEEK ODBC function
- functions, ODBC CONCAT
- SECOND ODBC function
- functions, ODBC CURRENT_TIME
- functions, ODBC HOUR
- functions, ODBC QUARTER
- TRUNCATE ODBC function
- functions, ODBC SECOND
- DAYOFWEEK ODBC function
- CURRENT_DATE ODBC function
- DAYNAME ODBC function
- CURTIME ODBC function
- functions, ODBC CURRENT_DATE
- MINUTE ODBC function
- functions, ODBC BIT_LENGTH
- functions, ODBC OCTET_LENGTH
- CONCAT ODBC function
- MONTHNAME ODBC function
- functions, ODBC DAYOFYEAR
- OCTET_LENGTH ODBC function
- functions [SQL Server], ODBC scalar functions
- BIT_LENGTH ODBC function
- functions, ODBC DAYOFMONTH
- CURRENT_TIME ODBC function
- functions, ODBC CURDATE
- functions, ODBC CURTIME
- functions, ODBC TRUNCATE
- functions, ODBC MONTHNAME
- functions, ODBC DAYNAME
- ODBC scalar functions
- functions, ODBC MINUTE
- functions, ODBC DAYOFWEEK
- QUARTER ODBC function
- DAYOFYEAR ODBC function
- functions, ODBC WEEK
- HOUR ODBC function
ms.assetid: a0df1ac2-6699-4ac0-8f79-f362f23496f1
caps.latest.revision: 17
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: b248e52c25e3c4a7cdbb0e52b1df50623e048189
ms.contentlocale: es-es
ms.lasthandoff: 09/01/2017

---
# <a name="odbc-scalar-functions-transact-sql"></a>Funciones escalares de ODBC (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Puede usar [funciones escalares de ODBC](http://go.microsoft.com/fwlink/?LinkID=88579) en [!INCLUDE[tsql](../../includes/tsql-md.md)] instrucciones. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interpreta estas instrucciones. Se pueden utilizar en procedimientos almacenados y funciones definidas por el usuario. Entre estas últimas se incluyen funciones de cadena, de número, de hora, de fecha, de intervalo y de sistema.  
  
## <a name="usage"></a>Uso  
 `SELECT {fn <function_name> [ (<argument>,....n) ] }`  
  
## <a name="functions"></a>Funciones  
 Las tablas siguientes enumeran las funciones escalares de ODBC que no se duplican en [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
### <a name="string-functions"></a>Funciones de cadena  
  
|Función|Description|  
|--------------|-----------------|  
|BIT_LENGTH( string_exp ) (ODBC 3.0)|Devuelve la longitud en bits de la expresión de cadena.<br /><br /> No funciona únicamente para los tipos de datos de cadena. Por consiguiente, no convertirá implícitamente string_exp en una cadena sino que, en su lugar, devolverá el tamaño (interno) del tipo de datos que se proporcione.|  
|CONCAT( string_exp1,string_exp2) (ODBC 1.0)|Devuelve una cadena de caracteres que es el resultado de concatenar string_exp2 con string_exp1. La cadena resultante es dependiente de DBMS. Por ejemplo, si la columna representada por string_exp1 contenía un valor NULL, DB2 devolvería NULL, pero [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devolvería la cadena distinta de NULL.|  
|OCTET_LENGTH( string_exp ) (ODBC 3.0)|Devuelve la longitud en bytes de la expresión de cadena. El resultado es el entero más pequeño que no es inferior al número de bits dividido por 8.<br /><br /> No funciona únicamente para los tipos de datos de cadena. Por consiguiente, no convertirá implícitamente string_exp en una cadena sino que, en su lugar, devolverá el tamaño (interno) del tipo de datos que se proporcione.|  
  
### <a name="numeric-function"></a>Función numéricas  
  
|Función|Description|  
|--------------|-----------------|  
|TRUNCATE( numeric_exp, integer_exp) (ODBC 2.0)|Devuelve numeric_exp truncado en posiciones de integer_exp a la derecha del separador decimal. Si integer_exp es negativo, numeric_exp se trunca a &#124; integer_exp &#124; posiciones a la izquierda del separador decimal.|  
  
### <a name="time-date-and-interval-functions"></a>Funciones de hora, fecha e intervalo  
  
|Función|Description|  
|--------------|-----------------|  
|CURRENT_DATE( ) (ODBC 3.0)|Devuelve la fecha actual.|  
|CURDATE( ) (ODBC 3.0)|Devuelve la fecha actual.|  
|CURRENT_TIME`[( time-precision )]` (ODBC 3.0)|Devuelve la hora local actual. El argumento de precisión de la hora determina la precisión en segundos del valor devuelto|  
|CURTIME() (ODBC 3.0)|Devuelve la hora local actual.|  
|DAYNAME( date_exp ) (ODBC 2.0)|Devuelve una cadena de caracteres que contiene el nombre específico del origen de datos del día (por ejemplo, Sunday a Saturday o Sun. a Sat. para un origen de datos que utiliza inglés, o bien Sonntag a Samstag para un origen de datos que utiliza alemán) para la parte del día de date_exp.|  
|DAYOFMONTH( date_exp ) (ODBC 1.0)|Devuelve el día del mes basado en el campo de mes en date_exp como un valor entero en el intervalo de 1 a 31.|  
|DAYOFWEEK( date_exp ) (ODBC 1.0)|Devuelve el día de la semana basado en el campo de semana en date_exp como un valor entero en el intervalo de 1 a 7, donde 1 representa el domingo.|  
|HOUR( time_exp ) (ODBC 1.0)|Devuelve la hora basada en el campo de hora en time_exp como un valor entero en el intervalo de 0 a 23.|  
|MINUTE( time_exp ) (ODBC 1.0)|Devuelve los minutos basados en el campo de miuntos en time_exp como un valor entero en el intervalo de 0 a 59.|  
|SECOND( time_exp ) (ODBC 1.0)|Devuelve los segundos basados en el campo de segundos en time_exp como un valor entero en el intervalo de 0 a 59.|  
|MONTHNAME( date_exp ) (ODBC 2.0)|Devuelve una cadena de caracteres que contiene el nombre específico del origen de datos del mes (por ejemplo, January a December o Jan. a Dec. para un origen de datos que utiliza inglés, o bien Januar a Dezember para un origen de datos que utiliza alemán) para la parte del mes de date_exp.|  
|QUARTER( date_exp ) (ODBC 1.0)|Devuelve el trimestre en date_exp como un valor entero en el intervalo de 1 a 4, donde 1 representa el trimestre del 1 de enero al 31 de marzo.|  
|WEEK( date_exp ) (ODBC 1.0)|Devuelve la semana del año basado en el campo de semana en date_exp como un valor entero en el intervalo de 1 a 53.|  
  
## <a name="examples"></a>Ejemplos  
  
### <a name="a-using-an-odbc-function-in-a-stored-procedure"></a>A. Utilizar una función ODBC en un procedimiento almacenado  
 En el siguiente ejemplo se utiliza una función ODBC en un procedimiento almacenado:  
  
```  
CREATE PROCEDURE dbo.ODBCprocedure  
    (  
    @string_exp nvarchar(4000)  
    )  
AS  
SELECT {fn OCTET_LENGTH( @string_exp )};  
```  
  
### <a name="b-using-an-odbc-function-in-a-user-defined-function"></a>B. Utilizar una función ODBC en una función definida por el usuario  
 El siguiente ejemplo utiliza una función ODBC en una función definida por el usuario:  
  
```  
CREATE FUNCTION dbo.ODBCudf  
    (  
    @string_exp nvarchar(4000)  
    )  
RETURNS int  
AS  
BEGIN  
DECLARE @len int  
SET @len = (SELECT {fn OCTET_LENGTH( @string_exp )})  
RETURN(@len)  
END ;  
  
SELECT dbo.ODBCudf('Returns the length.');  
--Returns 38  
  
```  
  
### <a name="c-using-an-odbc-functions-in-select-statements"></a>C. Utilizar funciones ODBC en instrucciones SELECT  
 Las siguientes instrucciones SELECT utilizan funciones ODBC:  
  
```  
DECLARE @string_exp nvarchar(4000) = 'Returns the length.';  
SELECT {fn BIT_LENGTH( @string_exp )};  
-- Returns 304  
SELECT {fn OCTET_LENGTH( @string_exp )};  
-- Returns 38  
  
SELECT {fn CONCAT( 'CONCAT ','returns a character string')};  
-- Returns CONCAT returns a character string  
SELECT {fn TRUNCATE( 100.123456, 4)};  
-- Returns 100.123400  
SELECT {fn CURRENT_DATE( )};  
-- Returns 2007-04-20  
SELECT {fn CURRENT_TIME(6)};  
-- Returns 10:27:11.973000  
  
DECLARE @date_exp nvarchar(30) = '2007-04-21 01:01:01.1234567';  
SELECT {fn DAYNAME( @date_exp )};  
-- Returns Saturday  
SELECT {fn DAYOFMONTH( @date_exp )};  
-- Returns 21  
SELECT {fn DAYOFWEEK( @date_exp )};  
-- Returns 7  
SELECT {fn HOUR( @date_exp)};  
-- Returns 1   
SELECT {fn MINUTE( @date_exp )};  
-- Returns 1  
SELECT {fn SECOND( @date_exp )};  
-- Returns 1  
SELECT {fn MONTHNAME( @date_exp )};  
-- Returns April  
SELECT {fn QUARTER( @date_exp )};  
-- Returns 2  
SELECT {fn WEEK( @date_exp )};  
-- Returns 16  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Ejemplos: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] y[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="d-using-an-odbc-function-in-a-stored-procedure"></a>D. Utilizar una función ODBC en un procedimiento almacenado  
 En el siguiente ejemplo se utiliza una función ODBC en un procedimiento almacenado:  
  
```  
CREATE PROCEDURE dbo.ODBCprocedure  
    (  
    @string_exp nvarchar(4000)  
    )  
AS  
SELECT {fn BIT_LENGTH( @string_exp )};  
```  
  
### <a name="e-using-an-odbc-function-in-a-user-defined-function"></a>E. Utilizar una función ODBC en una función definida por el usuario  
 El siguiente ejemplo utiliza una función ODBC en una función definida por el usuario:  
  
```  
CREATE FUNCTION dbo.ODBCudf  
    (  
    @string_exp nvarchar(4000)  
    )  
RETURNS int  
AS  
BEGIN  
DECLARE @len int  
SET @len = (SELECT {fn BIT_LENGTH( @string_exp )})  
RETURN(@len)  
END ;  
  
SELECT dbo.ODBCudf('Returns the length in bits.');  
--Returns 432  
  
```  
  
### <a name="f-using-an-odbc-functions-in-select-statements"></a>F. Utilizar funciones ODBC en instrucciones SELECT  
 Las siguientes instrucciones SELECT utilizan funciones ODBC:  
  
```  
DECLARE @string_exp nvarchar(4000) = 'Returns the length.';  
SELECT {fn BIT_LENGTH( @string_exp )};  
-- Returns 304  
  
SELECT {fn CONCAT( 'CONCAT ','returns a character string')};  
-- Returns CONCAT returns a character string  
SELECT {fn CURRENT_DATE( )};  
-- Returns todays date  
SELECT {fn CURRENT_TIME(6)};  
-- Returns the time  
  
DECLARE @date_exp nvarchar(30) = '2007-04-21 01:01:01.1234567';  
SELECT {fn DAYNAME( @date_exp )};  
-- Returns Saturday  
SELECT {fn DAYOFMONTH( @date_exp )};  
-- Returns 21  
SELECT {fn DAYOFWEEK( @date_exp )};  
-- Returns 7  
SELECT {fn HOUR( @date_exp)};  
-- Returns 1   
SELECT {fn MINUTE( @date_exp )};  
-- Returns 1  
SELECT {fn SECOND( @date_exp )};  
-- Returns 1  
SELECT {fn MONTHNAME( @date_exp )};  
-- Returns April  
SELECT {fn QUARTER( @date_exp )};  
-- Returns 2  
SELECT {fn WEEK( @date_exp )};  
-- Returns 16  
```  
  
## <a name="see-also"></a>Vea también  
 [Funciones integradas &#40;Transact-SQL&#41;](~/t-sql/functions/functions.md)  
  
  



