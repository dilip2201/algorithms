# 5. Quick Sort


Step 1) Select 1st Index of array and set to the correct position
```
[10,12,8,5,25,23,3,4]
 ^
```

>index = 0;
compare with every element if value is less than swap. finally swap to current position

after swaping
```
[3,4,8,5,10,12,25,23]
		  ^
```
Repeat for left(0 index to 4) and right (6 index to 8)

```
function pivot(array,start = 0, end = array.length + 1){
    let pivot = array[start];
    let indexV = start;
    for (let i = start + 1; i < array.length; i++) {
        if(pivot > array[i]){
            indexV++;
            const temp = array[i];
            array[i] = array[indexV];
            array[indexV] = temp;
        }
    }
    [array[indexV], array[start] ] = [array[start], array[indexV] ]

    return indexV;
    
}
```
```
function QuickSort(arr, left = 0, right = arr.length - 1){
    
    if(left < right){
        const getPivotIndex = pivot(arr,left,right);
        QuickSort(arr,left,getPivotIndex-1)
        QuickSort(arr,getPivotIndex+1,right)
    }
    
    return arr;
}
```
>QuickSort([10,4,2,14,18,2,1])