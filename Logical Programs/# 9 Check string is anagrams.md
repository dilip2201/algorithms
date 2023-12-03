# 9 Check string is anagrams

```
function anagrams(stringA, stringB) {
    let map1 = buildCharMap(stringA)
    let map2 = buildCharMap(stringB)
    if(Object.keys(map1).length !== Object.keys(map2).length) {
        return false;
    }

    for(let char in map1){
        if(map1[char] !== map2[char]){
            return false;
        }
    }
    return true;
};

function buildCharMap(string){
    let mapResultA = {}
    for (let i = 0; i < string.length; i++) {
        mapResultA[string[i]] = mapResultA[string[i]] + 1 || 1;
    }
    return mapResultA;
}



anagrams("rail safety", "fairy tales"); //true
```