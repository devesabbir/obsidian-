
PHP supports many kinds of operators:

- Arithmetic Operators
- Assignment Operators
- Bitwise Operators
- Comparison Operators
- Increment/Decrement Operators
- Logical Operators
- Concatenating Operators

## Arithmetic Operators

| Operator |Name |Description |
| --- |--- | --- |
| +| Addition | Return the sum of two operands |
| – | Subtraction | Return the difference between two operands |
| \* | Multiplication | Return the product of two operands |
| / | Division | Return the quotient of two operands |
| % | Modulus | Return the remainder of the division of the first operand by the second one |


The following example uses the arithmetic operators:

```php
<?php

	$x = 20; 
	$y = 10; // add, subtract, and multiplication operators demo 
	echo $x + $y . '<br/>'; // 30 
	echo $x - $y . '<br/>'; // 10 
	echo $x * $y . '<br/>'; // 200 
	
	// division operator demo 
	$z = $x / $y; echo gettype($z) . '<br/>'; // integer 
	$z = $y / $x; echo gettype($z) . '<br/>'; // double 
	
	// modulus demo 
	$y = 15; 
	echo $x % $y . '<br/>'; // 5

?>
```

## Comparison Operators

Comparison operators allow you to compare two operands.

A comparison operator returns a Boolean value, either `true` or `false`. If the comparison is truthful, the comparison operator returns `true`, otherwise, it returns `false`.

The following are the list of comparison operators in PHP:

| Operator | Name | Description |
|---|---|---|
| \=\= | Equality | Return `true` if both operands are equal, otherwise returns `false`. |
| \=\=\= | Identity | Return `true` if both operands have the same data type and equal, otherwise return `false`.|
|!\=\=\=|Not identical|Return `true` if both operands are not equal or not have the same data type, otherwise return`false`.|
|>|Greater than|Return `true` if the operand on the left  is greater than the operand on the right, otherwise return `false`.|
|>\=|Greater than or equal to|Return `true` if the operand on the left  is greater than or equal to the operand on the right, otherwise return `false`.|
|<|Less than|Return `true` if the operand on the left is less than the operand on the right, otherwise return `false`.|
|<\=|Less than or equal|Return `true` if the operand on the left  is less than or equal to the operand on the right, otherwise return `false`.|


## Logical Operators

Logical operators allow you to construct logical expressions. A logical operator returns a Boolean value.

PHP provides the following logical operators:

|Operator|Name|Description|
|---|---|---|
|&&|Logical AND|Return `true` if both operands are `true`, otherwise return `false`. If the first operand is `false`, it will not evaluate the second operand because it knows for sure that the result is going to be `false`. This is known as short-circuiting.|
|\||Logical OR|Return `true` if one of the operands is `true`, otherwise returns `false`. If the first operand is `true`, it will not evaluate the second one.|
|xor|Logical XOR|Return `true` if either operand, not both, is `true`_,_ otherwise, return `false`_._|
|!|Not|returns `true` if the operand is `false`_,_ and returns `false` if the operand is `true`.|


## Bitwise Operators

Bitwise operators perform operations on the binary representation of the operands. The following illustrates bitwise operators in PHP:

|Operators|Name|Result|
|---|---|---|
|`$x & $y`|And|If both bits are 1, the corresponding bit in the result is 1; otherwise, the corresponding bit is 0|
|`$x \| $y`|Or (inclusive or)|If both bits are 0, the corresponding bit in the result is 0; otherwise, the corresponding bit is 1|
|`$x ^ $y`|Xor (exclusive or)|If either bit, but not both, in `$x` and `$y` are 1, the corresponding bit in the result is 1; otherwise, the corresponding bit is 0|
|`~ $x`|Not|Change bit 1 to 0 and 0 to 1 in the $x operand|
|`$x << $y`|Shift left|Shifts the bits in `$x` left by the number of places specified by `$y`.|
|`$x >> $y`|Shift right|Shifts the bits in `$x` right by the number of places specified by `$y`.|


## Incrementing/ Decrementing Operators

Increment (++)  and decrement (–) operators give you a quick way to increase and decrease the value of a variable by 1.

The following table illustrates the increment and decrement operators:

|Example|Name|Returned Value|Effect on $a|
|---|---|---|---|
|`++$a`|Pre-increment|`$a + 1`|Increments `$a` by 1, then returns `$a`.|
|`$a++`|Post-increment|`$a`|Returns `$a`, then increments `$a` by 1.|
|`--$a`|Pre-decrement|`$a - 1`|Decrements `$a` by 1, then returns `$a`.|
|`$a--`|Post-decrement|`$a`|Returns `$a`, then decrements `$a` by 1.|

## Concatenating Operator

Concatenating operator (.) allows you to combine two strings into one. It appends the second string to the first one and returns the combined string. For example:

```php
<?php 
	$str = 'PHP' . ' is ' . ' Awesome!'; 
	echo $str; 
?>
```
