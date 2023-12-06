
## Introduction to the PHP OR operator

The logical `OR` operator accepts two operands and returns `true` if either operand is true; otherwise, it returns `false`. In other words, the logical OR operator returns `false` if both operands are `false`.
To represent the logical OR operator, PHP uses either the `or` keyword or the `||` as follows:

`expression1 or expression2`
OR
`expression1 || expression2`

The following table illustrates the result of the `or` operator:

| expression1 | expression2 | expression1 \| expression2 |
|---| ---- | --- |
| true | true | true |
| true | false | true |
| false | true | true |
| false | true | true |
| false | false | false |

Note that the `or`, `Or`, and `OR` are the same because PHP keywords are case-insensitive.
The `||` and `or` operators return the same result. The only difference between the `||` and `or` operators are their precedences. The `or` operator has higher precedence than the `||` operator.

## PHP OR operator examples

Suppose that you need to clear the cache of the website if the flag `$exprired` or `$purge` is set to `true`. To do that, you can use the logical OR operator as follows:

```php
<?php 
	$expired = true; 
	$purged = false; 
	$clear_cache = $expired || $purged; 
	var_dump($clear_cache);
?>
```
Output:
`bool(true)`

Since `$expired` is `true`, the result of the OR operator is also `true`.
However, if you change the `$expired` to `false`, the result will be `false` as shown in the following example:

```php
<?php 
	$expired = false; 
	$purged = false; 
	$clear_cache = $expired || $purged; 
	var_dump($clear_cache);
?>
```

In practice, you often use the logical OR operator in the [if](https://www.phptutorial.net/php-tutorial/php-if/), [if-else](https://www.phptutorial.net/php-tutorial/php-if-else/), [if-elseif](https://www.phptutorial.net/php-tutorial/php-if-elseif/), [while](https://www.phptutorial.net/php-tutorial/php-while/), and [do-while](https://www.phptutorial.net/php-tutorial/php-do-while/) statements.

#php-or-operator
## Short-circuiting

When the first operand is `true`, the logical OR operator knows that the result must be also `true`. In this case, it doesn’t evaluate the second operand. This process is called short-circuiting.

In practice, you often find that the or operator is used in the following pattern:

`function_call() || die(message)`

If the `function_call()` returns `true`, it succeeded. PHP will never execute the second operand which is a call to the `die()` function. Otherwise, PHP will call the `die()` function with an error message.

For example:

```php
<?php 
function connect_to_db(){ return false; } connect_to_db() || die('Cannot connect to the database.');
?>
```

Output:
`Cannot connect to the database`

In this example, the `connect_to_db()` function returns `false`, PHP calls the `die()` function that shows the error message.

#short-circuiting

## The PHP OR gotchas

See the following example:

```php
<?php 
	$result = false or true; 
	var_dump($result);
?>
```

Output:
`bool(false)`

In this example, you would expect that the $result is true because false or true expression returns true. However, it is not the case.
When evaluating the following statement:
```php
$result = false or true;
```
PHP evaluates the `$result = false` first and then the `or` operator second because the `=` operator has higher precedence than the `or` operator.

Technically, it is equivalent to the following:

```php
($result = false) or true;
```
Therefore, `$result` is assigned the `false` value.

To fix this, you need to use parentheses to change the order of evaluation:

```php
<?php 
	$result = (false or true); 
	var_dump($result);
?>
```

Output:
`bool(true)`

Or you can use the || operator:

```php
<?php 
	$result = false || true; 
	var_dump($result);
?>
```

Output:
`bool(true)`
Therefore, it’s a good practice to always use the `||` operator instead of the `or` operator.

#php-or-gotchas


