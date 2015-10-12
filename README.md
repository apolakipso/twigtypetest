Craft-TwigTypeTest
==================

Test if a Twig Variable is of a certain type in Craft-CMS.


##Usage:

####Test: ```of_type('test_name')```

Check if a variable is of a specific type.

```twig
{% set test_var = craft.entries %}

{% if test_var is of_type('object') %}
  true
{% endif %}
```

Check if a variable is an array of a specific class.

TODO: This currently only checks for a certain class, extend this to check for arrays of other types as well.

```twig
{% set test_var = craft.entries.section("Things").find() %}

{% if test_var is of_type('array_of', 'Craft\\EntryModel) %}
  true
{% endif %}
```


**Available Tests:**

 - [array](http://php.net/manual/en/function.is-array.php)
 - [bool](http://php.net/manual/en/function.is-bool.php)
 - [class](https://github.com/victor-in/Craft-TwigTypeTest/issues/1)
 - [float](http://php.net/manual/en/function.is-float.php)
 - [int](http://php.net/manual/en/function.is-int.php)
 - [numeric](http://php.net/manual/en/function.is-numeric.php)
 - [object](http://php.net/manual/en/function.is-object.php)
 - [scalar](http://php.net/manual/en/function.is-scalar.php)
 - [string](http://php.net/manual/en/function.is-string.php)
 - array\_of true if the var is an array and the first entry (as returned by array_shift) is of the specified class

#### Filter: ```get_type```

Return the type of a variable.

```twig
{% set test_var = craft.entries %}

{{ test_var|get_type }}
```
will output:
``` object ```

Alias for php's [``` gettype() ```](http://php.net/manual/en/function.gettype.php)


#### Filter: ```get_class```

Return the class of a variable.

```twig
{% set test_var = craft.entries.section("Things").find() %}

{{ test_var[0]|get_type }}
```
will output:
``` Craft\EntryModel ```

Alias for php's [``` get_class() ```](http://php.net/manual/en/function.get-class.php)


##Install:

1. Move the `twigtypetest` directory into the `craft/plugins/` directory.
2. Go to Settings -> Plugins and enable 'Twig Type Tests'.
