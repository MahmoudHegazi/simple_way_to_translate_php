# simple_way_to_translate_php


```php

function toLowerSingleVal($value) {
    return strtolower($value);
}

function in_array_r($needle, $haystack, $strict = false, $lang='italian') {
    $lang_index = $lang == 'english' ? 0 : 1;
    
    for ($i=0; $i<count($haystack); $i++) {
        $yourArray = array_map('toLowerSingleVal', $haystack[$i]);
        if (($strict ? $yourArray === strtolower($needle) : $haystack[$i] == strtolower($needle)) || (is_array($yourArray) && in_array_r(strtolower($needle), $yourArray, $strict))) {
                if (count($yourArray) > $lang_index){
                  return $haystack[$i][$lang_index];
                } else {
                  return $needle;
                }
    }     
}
    return false;
}

$b = array(
array("hello", "Ciao"),
array("Irix", "Linux")
);
echo in_array_r("Hello", $b);
```
