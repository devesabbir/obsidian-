
# PHP Operators

- Arithmetic Operators
- Assignment Operators
- Bitwise Operators
- Comparison Operators
- Increment/Decrement Operators
- Logical Operators
- Concatenating Operators


##### Arithmetic Operators

| Operator | Name | Description |
| ---- | ---- | ---- |
| + | Addition | Return the sum of two operands |
| - | Subtraction | Return the difference between two operands |
| * | Multiplication | Return the product of two operands |
| / | Division | Return the quotient of two operands |
| % | Modulus | Return the reminder of the division of the first operand by the second one |


#php_operators #Arithmetic_operators

##### Comparison Operators

| Operator | Name | Description |
| ---- | ---- | ---- |
| == | Equal to | Return `true` if both operands are equal; otherwise, it returns `false`. |
| !=, <> | Not equal to | Return `true` if both operands are equal; otherwise, it returns `false`. |
| ===  | Identical to | Return `true` if both operands have the same data type and equal; otherwise, it returns `false`. |
| !=== | Not Identical to | Return `true` if both operands are not equal or not have the same data type; otherwise, it returns `false`. |
|  >   | Greater than  | Return `true` if the operand on the left  is greater than the operand on the right; otherwise, it returns `false`. |
|  >=  | Greater than or equal to | Return `true` if the operand on the left  is greater than or equal to the operand on the right; otherwise, it returns `false`.|
|  <   | Less than | Return `true` if the operand on the left is less than the operand on the right; otherwise, it returns `false`.|
|  <=  | Less than or equal to | Return `true` if the operand on the left  is less than or equal to the operand on the right; otherwise, it returns `false`.|

#php  #php_operators  #comparison_operators


```PHP
<?php
  $num = 10;
  $str_value = '10';
  
  var_dump($str_value == $num); // return true
  var_dump($str_value === $num); // return false
?>
```



####  Logical Operator's 


|Operator|Name|Description|
|---|---|---|
|&&|Logical AND|Return `true` if both operands are `true`, otherwise return `false`. If the first operand is `false`, it will not evaluate the second operand because it knows for sure that the result is going to be `false`. This is known as short-circuiting.|
|\||Logical OR|Return `true` if one of the operands is `true`, otherwise returns `false`. If the first operand is `true`, it will not evaluate the second one.|
|xor|Logical XOR|Return `true` if either operand, not both, is `true`_,_ otherwise, return `false`_._|
|!|Not|returns `true` if the operand is `false`_,_ and returns `false` if the operand is `true`.|

#logical_operators #php  #php_operators 


####  Bitwise Operators

|Operators|Name|Result|
|---|---|---|
|`$x & $y`|And|If both bits are 1, the corresponding bit in the result is 1; otherwise, the corresponding bit is 0|
|`$x \| $y`|Or (inclusive or)|If both bits are 0, the corresponding bit in the result is 0; otherwise, the corresponding bit is 1|
|`$x ^ $y`|Xor (exclusive or)|If either bit, but not both, in `$x` and `$y` are 1, the corresponding bit in the result is 1; otherwise, the corresponding bit is 0|
|`~ $x`|Not|Change bit 1 to 0 and 0 to 1 in the $x operand|
|`$x << $y`|Shift left|Shifts the bits in `$x` left by the number of places specified by `$y`.|
|`$x >> $y`|Shift right|Shifts the bits in `$x` right by the number of places specified by `$y`.|

#php #php_operators  #bitwise_operators 
