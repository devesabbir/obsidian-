# Introduction to the PHP type casting

| Cast Operator | Conversion |
| ---------------- | ------------- |
| (array) | Array |
| (bool) or (boolean) | Boolean  |
| (int) or (integer) | Integer |
| (object) | Object  |
| (real), (double), or (float) | Float |
| (string) | String |

#typecasting #php 

# Cast Integer

```PHP 
<?php
 $cell_number = "01744518886"; 
 $amount = (int) '100 USD';  // cast in integer

 var_dump((int)$cell_number); // cast in integer
 var_dump($amount);

?>
```


#cast_integer #type_casting

# Cast String 

```PHP 
<?php
 $doller = 200;
 var_dump((string)$doller. ' USD'); // cast to string
?>
```


