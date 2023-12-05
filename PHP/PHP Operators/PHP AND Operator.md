
## Introduction to the PHP AND operator

The logical AND operator accepts two operands and returns `true` if both operands are `true`; otherwise, it returns `false`.

PHP uses the `and` keyword to represent the logical AND operator:

The following table illustrates the result of the `and` operator:

| Expression 01 | Expression 02 | Expression 01 and Expression 02 |
| ---- | ----- | ---- |
| true | true | true |
| true | false | false |
| false | true | false |
| false | false | false |

## PHP AND operator examples

Suppose that you want to offer discounts to customers who buy more than three items with a price of more than 99. To determine whether customers can get a discount or not, you can use the AND operator as follows:

```php
<?php 
	$price = 100; 
	$qty = 5; 
	$discounted = $qty > 3 && $price > 99; 
	var_dump($discounted);
?>
```
Output:
`bool(true)`

If you change the `$qty` to `2`, the `$discounted` will be `false` like this:

```php
<?php 
$price = 100; 
$qty = 2;
$discounted = $qty > 3 && $price > 99; 
var_dump($discounted);
?>
```

## Short-circuiting

When the value of the first operand is `false`, the logical AND operator knows that the result must be also `false`. In this case, it doesn’t evaluate the second operand. This process is called short-circuiting.

```php
<?php 
	$debug = false; 
	$debug && print('PHP and operator demo!');
?>
```

How it works.

- First, define the variable `$debug` and initialize it to `false`.
- Second, use the logical AND operator to combine the `$debug` and `print()`. Since `$debug` is `false`, PHP doesn’t evaluate the call to the `print()` function.

If you change the `$debug` to `true`, you’ll see a message in the output:

```php
<?php 
	$debug = true; 
	$debug && print('PHP and operator demo!');
?>
```

Output:
`PHP and operator demo!`

