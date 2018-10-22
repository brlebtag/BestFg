# BestFg
Algorithm to find the best foreground color based on the specified background color.

Extract RGB components from string:

```
function extractRGB(str) {
    return [parseInt(str.substr(1, 2), 16), parseInt(str.substr(3 ,2), 16), parseInt(str.substr(5, 2), 16)];
}

```

Get best foreground color:

```

function getBestFg(str){
    var rgb = extractRGB(str);
    var r = rgb[0], b  = rgb[1], g = rgb[2];
    
    var yiq = ((r*299)+(g*587)+(b*114))/1000;
    
    return (yiq >= 128) ? 'black' : 'white';
}
```