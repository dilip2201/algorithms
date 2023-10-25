# 2. Selection Sort


>index = 0
>1) Select first element(5) 
>2) find minimun value(1) from rest Array
>3) Swap
```
[5,3,4,1,2] first = 5, min = 3
 ^ ^

[5,3,4,1,2] first = 5, min = 3
 ^   ^

[5,3,4,1,2] first = 5, min = 1
 ^     ^

[5,3,4,1,2] first = 5, min = 1
 ^       ^

Swap
[1,3,4,5,2]
```

>index = 1
>1) Select first element(3) 
>2) find minimun value(2) from rest Array
>3) Swap

```
[1,3,4,5,2] first = 3, min = 3
   ^ ^

[1,3,4,5,2] first = 3, min = 3
   ^   ^

[1,3,4,5,2] first = 3, min = 2
   ^     ^
Swap
[1,2,4,5,3]
```

Repeat

```
function selectionSort(array){
    debugger;
    for (let i = 0; i < array.length; i++) {
        let minimumValueIndex = i;
        for (let j = i; j < array.length; j++) {
            if(array[minimumValueIndex] > array[j])
            {
                minimumValueIndex = j;
            }
        }
        const temp = array[i];
        array[i] = array[minimumValueIndex];
        array[minimumValueIndex] = temp;
       
    }
    return array
}


selectionSort([5,3,4,1,2]);
```
