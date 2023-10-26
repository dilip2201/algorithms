# 4. Merge Sort

Step 1) Merge two Sorted Array into One.

>* [1,2,4,6,7,8,10] -->array1
>* [3,5,9,11,14,15] --> array2

```
i=0
j=0
result = [];
[1,2,4,6,7,8,10] [3,5,9,11,14,15]
 ^                ^
//compare both(1,3) value push small Value(1) to result array. and increase i value.
```

```
i=1;
j=0;
result=[1];
[1,2,4,6,7,8,10] [3,5,9,11,14,15]
   ^              ^
//compare both value(2,3) push small Value(2) to result array. and increase i value.
```

```
i=2;
j=0;
result=[1,2];
[1,2,4,6,7,8,10] [3,5,9,11,14,15]
     ^            ^
//compare both value(4,3) push small Value(3) to result array. and increase j value.
result=[1,2,3];
...
...
...
...
...
```

```
repeat until one array is done--> array1 is done.
i=6;
j=4;
result=[1,2,3,4,5,6,7,8,9,10,11];
push remain value of array2 = [3,5,9,11,14,15]
                                         ^  ^
```

## A Merge Algorithm 
```
function merge(array1,array2){
    let i = 0;
    let j = 0;
    let result = [];
    while(i < array1.length && j < array2.length){
        if(array1[i] > array2[j]){
            result.push(array2[j]);
            j++;
        }else{
            result.push(array1[i])
            i++;
        }
    }
    while(j < array2.length){
        result.push(array2[j])
        j++
    }
    while(i < array1.length){
        result.push(array1[i])
        i++
    }
    return result;
}
merge([1,2,5,9,10],[2,4,6,8,11,12,13]);
```
