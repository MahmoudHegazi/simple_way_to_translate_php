# simple_way_to_translate_php

##### note big apps use frameworks with alot of configurations and setup to reach same target this do it easy and fast and simple

```php

function toLowerSingleVal($value) {
    return strtolower($value);
}

function in_array_r($needle, $haystack, $strict = false, $lang='italian') {
    $lang_index = $lang == 'english' ? 0 : 1;
    
    for ($i=0; $i<count($haystack); $i++) {
        $yourArray = array_map('toLowerSingleVal', $haystack[$i]);
        if (($strict ? $yourArray === strtolower($needle) : $yourArray == strtolower($needle)) || (is_array($yourArray) && in_array(strtolower($needle), $yourArray, $strict))) {
        

                if (count($yourArray) > $lang_index){
                  return $haystack[$i][$lang_index] ? $haystack[$i][$lang_index] : $needle;
                } else {
                  return $needle;
                }
    }     
}
    return $needle;
}

$b = array(
array("hello", "Ciao"),
array("Irix", "")
);
echo in_array_r("hello", $b);
```
