
# 3. Selection Sort

let take this `[5,2,4,3,2,9,10]`

```
I = 1;
1) Select I value currentValue(2)
[5,2,4,3,2,9,10]
   ^

2) Compare with last element (5) -> j = 0 (if 5 > 2)
[5,2,4,3,2,9,10]
 ^

3) assign current value to last element --> array[j+1] = array[j];
[5,5,4,3,2,9,10] -> j = 0
 ^

Finally assign currentValue to J ---> array[j] = currentValue
[2,5,4,3,2,9,10] -> j = 0
```
let take this `[2,5,4,3,2,9,10]`

```
I = 2;
1) Select I value currentValue(4)
[2,5,4,3,2,9,10]
     ^

2) Compare with last element (5) -> j = 1 (if 5 > 4)
[2,5,4,3,2,9,10]
   ^

3) assign current value to last element --> array[j+1] = array[j];
[2,5,5,3,2,9,10] -> j = 1
     ^

Finally assign currentValue to J ---> array[j] = currentValue
[2,4,5,3,2,9,10] -> j = 0
```


let take this `[2,4,5,3,2,9,10]`
```
I = 3;
1) Select I value currentValue(3)
[2,4,5,3,2,9,10]
       ^

2) Compare with last element (5) -> j = 2 (if 5 > 3)
[2,4,5,3,2,9,10]
     ^

3) assign current value to last element --> array[j+1] = array[j];
[2,4,5,5,2,9,10] -> j = 1

2) Compare with last element (4) -> j = 1 (if 4 > 3)
[2,4,5,5,2,9,10]
   ^

3) assign current value to last element --> array[j+1] = array[j];
[2,4,4,5,2,9,10] -> j = 1
   ^  

Finally assign currentValue to J ---> array[j] = currentValue
[2,3,4,5,2,9,10] -> j = 1
   ^
```


**Final Algorithm **

```
function insertionSort(array){
    debugger;
    for (let i = 1; i < array.length; i++) {
        const currentVal = array[i];
        for (var j = i-1; j >= 0 && currentVal < array[j]; j--) {
            array[j+1] = array[j];
        }
        array[j+1] = currentVal;
    }
    return array;
}


insertionSort([5,7,8,3,2,9,10])
```
