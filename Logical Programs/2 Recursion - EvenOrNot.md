# 3 Recursion - EvenOrNot

Write a JavaScript program to check whether a number is even or not.  

```
function CheckEvenorNot(n){
    
    if (n < 0) 
    {
        n = Math.abs(n);
    }
    if(n == 1){
        return true;
    }
    if(n == 0){
        return false
    }
    return CheckEvenorOdd(n-2)
}

CheckEvenorNot(10)
```