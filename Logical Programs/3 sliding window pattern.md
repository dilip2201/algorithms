```
function SlidingWindowPattern(arr,k) {
    let sum = 0;
    let start = 0;
    let highestSum = 0;
    for (let end = 0; end < arr.length; end++) {        
        sum += arr[end];
        if((end-start) + 1 == k){
            highestSum = Math.max(highestSum,sum);
            sum = sum - arr[start];
            start += 1;
        }
    }
    return highestSum;
    
}

SlidingWindowPattern([9,4,9,5,7,3,9,5,8,9,7,4,5,3],2)
```