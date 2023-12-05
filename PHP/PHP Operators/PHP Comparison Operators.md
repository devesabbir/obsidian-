
## Introduction to PHP comparison operators

A comparison operator allows you to compare two values and returns `true` if the comparison is truthful and `false` otherwise.

The following table illustrates the comparison operators in PHP:

| Operator | Name | Description |
| ---------- | ------ | ----------- |
| == | Equal to | Return `true` if both operands are equal; otherwise, it returns `false`. |
| !=, <> | Not equal to | Return `true` if both operands are equal; otherwise, it returns `false`. |
| === | Identical to | Return `true` if both operands have the same data type and equal; otherwise, it returns `false`. |
| !== | Not identical to | Return `true` if both operands are not equal or not have the same data type; otherwise, it returns `false`. |
| > | Greater than or equal to | Return `true` if the operand on the left  is greater than the operand on the right; otherwise, it returns `false`. |
| >= | Greater than or equal to | Return `true` if the operand on the left  is greater than or equal to the operand on the right; otherwise, it returns `false`. |
| < | Less than | Return `true` if the operand on the left is less than the operand on the right; otherwise, it returns `false`. |
| <= | Less than or equal to | Return `true` if the operand on the left  is less than or equal to the operand on the right; otherwise, it returns `false`. |


### Equality Operator (==)

The equality returns `true` if both values are equal; otherwise, it returns `false`. The following example returns true because 10 is equal 10:

```php
<?php 
	$x = 10; 
	$y = 10; 
	var_dump($x == $y); // bool(true)
?>
```

The following example returns `false` because `10` is not equal `20`:

```php
<?php 
	$x = 20; 
	$y = 10; 
	var_dump($x == $y); // bool(false)
?>
```

The following example compares the number `20` with a string `'20'`, it also returns `true`.

```php
<?php 
	$x = '20'; 
	$y = 20; 
	var_dump($x == $y); // bool(true)
?>
```

If you want to compare two values with the consideration of type, you can use the identical operator (`===`).

### Not equal to operator (!=, <>)

The not equal to (!=, <>) operator returns `true` if the lefthand value is not equal to the righthand value; otherwise, it returns `false`. For example:

```php
<?php
	$x = 20;
	$y = 10;
	var_dump($x != $y); // bool(true)
?>
```
### Identical operator (\=\=\=)

The identical operator returns `true` if both values are equal and have the same type; otherwise returns `false`.

```php
<?php 
	$x = '20'; 
	$y = 20; 
	var_dump($x === $y); // bool(false)
?>
```

### Not identical operator (\=\=!)

The not identical operator (!\=\=) returns `true` if the values are not equal or they do not have the same type; otherwise, it return `false`. For example:

```php
<?php 
	$x = 20; 
	$y = 10; 
	var_dump($x != $y); // bool(true) 
	
	$x = 20; 
	$y = '20'; 
	var_dump($x != $y); // bool(false)
?>
```
### Greater than (>)

The greater than return `true` if the lefthand value is greater than the righthand value; otherwise, it returns `false`:

```php
<?php 
	$x = 10; 
	$y = 20; 
	var_dump($x > $y); // bool(false) 
	var_dump($y > $x); // bool(true)
?>
```

### Greater than or equal to (>=)

The greater than or equal to operator returns true if the lefthand value is greater than or equal to the righthand value; otherwise, it returns false. For example:

```php
<?php 
	$x = 20; 
	$y = 20; 
	var_dump($x >= $y); // bool(true) 
	var_dump($y >= $x); // bool(true)
?>
```
### Less than (<)

The less than operator returns true if the lefthand value is less than the righthand value; otherwise, it returns false. For example:

```php
<?php 
	$x = 20; 
	$y = 10; 
	var_dump($x < $y); // bool(false) 
	var_dump($y < $x); // bool(true)
?>
```
### Less than or equal to (<=)

If the lefthand value is less than or equal to the righthand value, the less than or equal to operator returns true; otherwise, it returns false. For example:

```php
<?php 
	$x = 20; 
	$y = 20; 
	var_dump($x <= $y); // bool(true) 
	var_dump($y <= $x); // bool(true)
?>
```

