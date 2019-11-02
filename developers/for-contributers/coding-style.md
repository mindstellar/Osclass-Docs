---
description: Basic Introduction to Osclass coding style
---

# Coding Style

## Coding Style

This small guide is partly based in the coding style guide of Zend Framework : [http://framework.zend.com/manual/1.12/en/coding-standard.coding-style.html](http://framework.zend.com/manual/1.12/en/coding-standard.coding-style.html)

### PHP Code Demarcation

PHP code must always be delimited by the full-form, standard PHP tags:

```php
<?php
 
?>
```

{% hint style="info" %}
**Short tags are never allowed.** For files containing only PHP code, the closing tag must always be omitted \(See General standards\).
{% endhint %}

### Variables

Variables should follow the Hungarian Notation \( [https://en.wikipedia.org/wiki/Hungarian\_notation](https://en.wikipedia.org/wiki/Hungarian_notation) \), that means they should start with a character indicating the type of variable, for example i for integer, a for arrays, o for objects, s for strings ... Also, each first character of a word should be uppercase.

```php
$iThisIsAnInteger = 42;
$sSomeText = 'This is some text';
$aVariable = array(1, 2, 3, 4 , 5);
...
```

**Note:** SQL column's names should follow a similar notation, but the first character should follow an underscore. Words are separated by an underscore, all in lowercase. If the column is a primary key, it should be preceded by "pk\_" if it's a foreign key by "fk\_"

```php
i_integer_variable
s_some_text
dt_registration_date
pk_i_id // this is a primary key
fk_i_category_id // this is a foreign key
...
```

### Classes

#### Class Declaration

The brace should always be written on the line underneath the class name.

Every class must have a documentation block that conforms to the PHPDocumentor standard. The following is an example of an acceptable class declaration:

```php
/**
* Documentation Block Here
*/
class Foo
{
    /**
     * Documentation Block Here
     */
    public function bar()
    {
        // all contents of function
        // must be indented four spaces
    }
}
```

### Control Statements

#### If/Else/Elseif

Control statements based on the `if` and `elseif` constructs must have a single space before the opening parenthesis of the conditional and a single space after the closing parenthesis.

{% hint style="info" %}
The opening brace is written on the same line as the conditional statement. 
{% endhint %}

The closing brace is always written on its own line. Any content within the braces must be indented using four spaces.

```php
if ($a != 2) {
    $a = 2;
} else {
    $a = 7;
}
 
if ($a != 2) {
    $a = 2;
} elseif ($a == 3) {
    $a = 4;
} else {
    $a = 7;
}
```

{% hint style="warning" %}
It's required ALWAYS to put the braces. 
{% endhint %}

The following if statements is not valid

```php
if($a != 2)
    $a = 2;
```

### Switch

Control statements written with the "switch" statement must have a single space before the opening parenthesis of the conditional statement and after the closing parenthesis.

All content within the "switch" statement must be indented using four spaces. Content under each "case" statement must be indented using an additional four spaces.

```php
switch ($numPeople) {
    case 1:
        break;
 
    case 2:
        break;
 
    default:
        break;
}
```

{% hint style="danger" %}
The construct default should never be omitted from a switch statement.
{% endhint %}

## Documentation Format

All documentation blocks \("docblocks"\) must be compatible with the phpDocumentor format. Describing the phpDocumentor format is beyond the scope of this document. For more information, visit: » [http://phpdoc.org/](http://phpdoc.org/) 

## More information

This small guide is partly based in the coding style guide of Zend Framework : [http://framework.zend.com/manual/1.12/en/coding-standard.coding-style.html](http://framework.zend.com/manual/1.12/en/coding-standard.coding-style.html)



