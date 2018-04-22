# PHP 7

## The `<?php ?>` tag:
- Should enclose PHP code with `<?php ?>`.
- Any code outside `<?php ?>` are interpreted as it is.
- Any HTML outside `<?php ?>` are interpreted by the browser.

### Exanmple:
```
<?php
echo 'hello world';
?>
bye world
```

The above code will print both `hello world` and `bye world`.

## Comment:

- PHP supports two types of comment - single-line comments and multiple-line comments.

### Example:
```
// This is the single-line comments

/*
  This is the multiple-line comments.
  second line.
*/
```

## Variable:

- PHP variables start with the $ sign followed by the variable name.
- The value of an unassigned variable is null.
- A valid variable name starts with a letter or an underscore followed by any combination of letters, numbers, and/or underscores.
- It is case sensitive. So, `$home` and `$Home` are two different variables.

### Example:
```
$txt = "Hello world!";
```

## Data types:

- PHP has 8 primitive data types.
  * Integer
  * String
  * Float (also called double)
  * Boolean
  * Array
  * Object
  * NULL
  * Resource
