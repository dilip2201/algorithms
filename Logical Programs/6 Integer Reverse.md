# 6 Integer Reverse

```
function reverse(x) {
    let result = 0, digit = 0;
    while(x){
        digit = x % 10;
        result = (result * 10) + digit;
        x = x/10 | 0;
    }
    return result;
   
};

reverse(123);
```