# 2. Recursion - exponent of a number

Write a JavaScript program to compute the exponent of a number.  
Note : The exponent of a number says how many times the base number is used as a factor.
`82 = 8 x 8 = 64.` Here 8 is the base and `2` is the exponent.

Solution
```
function exponent(num, times) {
    debugger;
    if(times <= 1) return num;
    return num * exponent(num,times - 1)
}


exponent(4, 3)
```