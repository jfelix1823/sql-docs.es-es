---
title: 'Pdostatement:: Bindparam | Microsoft Docs'
ms.custom: ''
ms.date: 05/22/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 65212058-2632-47a4-ba7d-2206883abf09
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 9471c0c86edd9ff5a8357b797014036bd60fec83
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47647672"
---
# <a name="pdostatementbindparam"></a>PDOStatement::bindParam
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Enlaza un parámetro a un marcador de posición con nombre o signo de interrogación en la instrucción SQL.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
bool PDOStatement::bindParam($parameter, &$variable[, $data_type[, $length[, $driver_options]]]);  
```  
  
#### <a name="parameters"></a>Parámetros  
$*parameter*: identificador de parámetro (mixto). En una instrucción que use marcadores de posición con nombre, emplee un nombre de parámetro (:name). En una instrucción preparada mediante la sintaxis de signos de interrogación, es el índice basado en 1 del parámetro.  
  
&$*variable*: nombre (mixto) de la variable PHP para enlazar con el parámetro de instrucción SQL.  
  
$*data_type*: constante PDO::PARAM_* opcional (entero). El valor predeterminado es PDO::PARAM_STR.  
  
$*length*: longitud opcional (entero) del tipo de datos. Puede especificar PDO::SQLSRV_PARAM_OUT_DEFAULT_SIZE para indicar el tamaño predeterminado al usar PDO::PARAM_INT o PDO::PARAM_BOOL en $*data_type*.  
  
$*driver_options*: las opciones de específicas del controlador opcionales (mixtas). Por ejemplo, podría especificar PDO::SQLSRV_ENCODING_UTF8 para enlazar la columna a una variable como una cadena codificada en UTF-8.  
  
## <a name="return-value"></a>Valor devuelto  
Se devuelve True si la operación se realiza correctamente; de lo contrario, False.  
  
## <a name="remarks"></a>Notas  
Cuando se enlazan datos null a las columnas de servidor de tipo varbinary, binary o varbinary(max), debe especificar la codificación binaria (PDO::SQLSRV_ENCODING_BINARY) con $*driver_options*. Para obtener más información sobre la codificación de constantes, vea [Constantes](../../connect/php/constants-microsoft-drivers-for-php-for-sql-server.md).  
  
En la versión 2.0 de los [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)], se agregó compatibilidad con PDO.  

## <a name="example"></a>Ejemplo  
En este ejemplo de código se muestra que después de que $contact se enlace al parámetro, al cambiar el valor, se modifica el valor transmitido en la consulta.  
  
```  
<?php  
$database = "AdventureWorks";  
$server = "(local)";  
$conn = new PDO("sqlsrv:server=$server ; Database = $database", "", "");  
  
$contact = "Sales Agent";  
$stmt = $conn->prepare("select * from Person.ContactType where name = ?");  
$stmt->bindParam(1, $contact);  
$contact = "Owner";  
$stmt->execute();  
  
while ($row = $stmt->fetch(PDO::FETCH_ASSOC)) {  
   print "$row[Name]\n\n";  
}  
  
$stmt = null;  
$contact = "Sales Agent";  
$stmt = $conn->prepare("select * from Person.ContactType where name = :contact");  
$stmt->bindParam(':contact', $contact);  
$contact = "Owner";  
$stmt->execute();  
  
while ($row = $stmt->fetch(PDO::FETCH_ASSOC)) {  
   print "$row[Name]\n\n";  
}  
?>  
```  
  
## <a name="example"></a>Ejemplo  
En este ejemplo de código se muestra cómo obtener acceso a un parámetro de salida.  
  
```  
<?php  
$database = "Test";  
$server = "(local)";  
$conn = new PDO("sqlsrv:server=$server ; Database = $database", "", "");  
  
$input1 = 'bb';  
  
$stmt = $conn->prepare("select ? = count(*) from Sys.tables");  
$stmt->bindParam(1, $input1, PDO::PARAM_STR, 10);  
$stmt->execute();  
echo $input1;  
?>  
```  
  
> [!NOTE]
> Al enlazar un parámetro de salida a un tipo bigint, si el valor puede acabar fuera del intervalo de un [entero](../../t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql.md), usar PDO:: param_int con PDO:: sqlsrv_param_out_default_size puede producir una excepción de "valor fuera del intervalo". Por lo tanto, use el valor predeterminado de PDO:: param_str y proporcione el tamaño de la cadena resultante, que es a lo sumo 21. Es el número máximo de dígitos, incluidos el signo negativo de cualquier valor bigint. 

## <a name="example"></a>Ejemplo  
En este ejemplo de código se muestra cómo utilizar un parámetro de entrada/salida.  
  
```  
<?php  
   $database = "AdventureWorks";  
   $server = "(local)";  
   $dbh = new PDO("sqlsrv:server=$server ; Database = $database", "", "");  
  
   $dbh->query("IF OBJECT_ID('dbo.sp_ReverseString', 'P') IS NOT NULL DROP PROCEDURE dbo.sp_ReverseString");  
   $dbh->query("CREATE PROCEDURE dbo.sp_ReverseString @String as VARCHAR(2048) OUTPUT as SELECT @String = REVERSE(@String)");  
   $stmt = $dbh->prepare("EXEC dbo.sp_ReverseString ?");  
   $string = "123456789";  
   $stmt->bindParam(1, $string, PDO::PARAM_STR | PDO::PARAM_INPUT_OUTPUT, 2048);  
   $stmt->execute();  
   print $string;   // Expect 987654321  
?>  
```  

> [!NOTE]
> Se recomienda usar cadenas como entradas al enlazar los valores para un [columna decimal o numeric](../../t-sql/data-types/decimal-and-numeric-transact-sql.md) para garantizar la precisión y la precisión PHP tiene limitada la precisión para [números de punto flotante](http://php.net/manual/en/language.types.float.php). Lo mismo se aplica a las columnas de tipo bigint, especialmente cuando los valores que están fuera del intervalo de un [entero](../../t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql.md).

## <a name="example"></a>Ejemplo  
Este ejemplo de código muestra cómo enlazar un valor decimal como un parámetro de entrada.  

```
<?php  
$database = "Test";  
$server = "(local)";  
$conn = new PDO("sqlsrv:server=$server ; Database = $database", "", "");  

// Assume TestTable exists with a decimal field 
$input = 9223372036854.80000;
$stmt = $conn->prepare("INSERT INTO TestTable (DecimalCol) VALUES (?)");
// by default it is PDO::PARAM_STR, rounding of a large input value may
// occur if PDO::PARAM_INT is specified
$stmt->bindParam(1, $input, PDO::PARAM_STR);
$stmt->execute();
```


## <a name="see-also"></a>Ver también  
[Clase PDOStatement](../../connect/php/pdostatement-class.md)

[PDO](http://php.net/manual/book.pdo.php)  
  
