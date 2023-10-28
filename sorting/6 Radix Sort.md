# 5. Quick Sort


Step 1) Create `10` buckets and split value based on last digit
>[117,1930,450,6589,9945,10,56,1,56,9840]

Step 2) first we check highest digit length --> it is `4(1930)`

step 3) loop `4` times and split value based on digit.

first loop(last digit)
```
0 -> [1930,450,10,9840]
1 -> [1]
2 -> []
3 -> []
4 -> []
5 -> [9945]
6 -> [56]
7 -> [117]
8 -> []
9 -> [6589]

now merge all array to one
[1930,450,10,9840,1,9945,56,117,6589]
```

second loop(second last digit)
```
0 -> [1]
1 -> [10,117]
2 -> []
3 -> [1930]
4 -> [9840,9945]
5 -> [450,56]
6 -> []
7 -> []
8 -> [6589]
9 -> []

now merge all array to one
[1,10,117,1930,9840,9945,450,56,6589]
```

third loop(third last digit)
```
0 -> [1,10,56]
1 -> [117]
2 -> []
3 -> [1930]
4 -> [450]
5 -> [6589]
6 -> []
7 -> []
8 -> [9840]
9 -> [1930,9945]

now merge all array to one
[1,10,56,117,1930,450,6589,9840,1930,9945]
```

4th loop(4th last digit)
```
0 -> [1,10,56,117,450]
1 -> [1930,1930]
2 -> []
3 -> []
4 -> []
5 -> [6589]
6 -> []
7 -> []
8 -> []
9 -> [9840,9945]

Merge and your final result
[1,10,56,117,1930,450,6589,9840,1930,9945]
```

Solutions
```
function getDigit(num,position){
   return Math.floor(Math.abs(num) / Math.pow(10,position)) % 10
}
```

```
function digitCount(num){
   if(num === 0) return 1;
   return Math.floor(Math.log10(Math.abs(num)))+1
}
```

```
function mostDigit(array){
   let getMost = 0;
   for (let i = 0; i < array.length; i++) {
      getMost = Math.max(getMost,digitCount(array[i]))
   }
   
   for (let i = 0; i < getMost; i++) {
      let bucket = Array.from({length : 10}, () => [])
    
      for (let j = 0; j < array.length; j++) {
         const digitF = getDigit(array[j],i)
         bucket[digitF].push(array[j])
      }
      array = [].concat(...bucket);
   }
   return array;
   
}


mostDigit([1067,5,24,300,970,9900])
```