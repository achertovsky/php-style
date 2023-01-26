# prerequisites
Personal authors styleguide that serves as public manifestation of following obligation attempts. Does not conflicts with [PSR-2](https://www.php-fig.org/psr/psr-2/). Its in public space for sharing reason. <br>
_If you mind i have it and you dont - [just create own](https://github.com/new)_

# accepted
- If class method or standalone function (default php ofc, you not into [procedural programming](https://en.wikipedia.org/wiki/Procedural_programming), aint u?) has more than one parameter - pass every parameter from new line, including first
```
$string = 'foo';
//right
strpos(
    $string,
    'bar'
);
is_string($string);

//wrong
strpos($string, 'bar');
is_string(
    $string
);
```

# staging
