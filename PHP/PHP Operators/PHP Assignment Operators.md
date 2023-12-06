
Besides the `+=` operator, PHP provides other arithmetic assignment operators. The following table illustrates all the arithmetic assignment operators:

| Operator | Example | Equivalent | Operation |
| --------- | -------- | ---------- | -------- |
| += | $x += $y | $x = $x + $y | Addition |
| -= | $x -= $y | $x = $x – $y | Subtraction |
| \*= | $x \*= $y | $x = $x \* $y | Multiplication |
| /= | $x /= $y | $x = $x / $y | Division |
| %= | $x %= $y | $x = $x % $y | Modulus |
| \*\*= | $z \*\*= $y | $x = $x \*\* $y | Exponentiation |


## Arithmetic assignment operators

Sometimes, you want to increase a variable by a specific value. For example:

```php
$counter = 1; 
$counter = $counter + 1;
```

PHP provides the arithmetic assignment operator `+=` that can do the same but with a shorter code. For example:

```php
$counter = 1; $counter += 1;
```

The expression `$counter += 1` is equivalent to the expression `$counter = $counter + 1`.

## Concatenation assignment operator

PHP uses the concatenation operator (.) to concatenate two strings. For example:

```php
<?php 
	$greeting = 'Hello '; 
	$name = 'John'; 
	$greeting = $greeting . $name; 
	echo $greeting;
?>
```

Output:
`Hello John`

By using the concatenation assignment operator you can concatenate two strings and assigns the result string to a variable. For example:

```php
<?php 
	$greeting = 'Hello '; 
	$name = 'John'; 
	$greeting .= $name; 
	echo $greeting;
?>
```

#php  #php-assignment-operator  
