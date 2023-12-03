#7 Find Maximum char from string.

```
function maxChar(string) {
    let mapResult = {}
    let max = 0;
    let maxChar = "";
    for (let i = 0; i < string.length; i++) {
        mapResult[string[i]] = mapResult[string[i]] + 1 || 1;
    }
    for(let char in mapResult){
        
        if(mapResult[char] > max){
           maxChar = char;
           max = mapResult[char]
        } 
    }
    return maxChar;
   
};

maxChar("Hello There!"); //e
maxChar("Hello 12311165111!"); //1
```