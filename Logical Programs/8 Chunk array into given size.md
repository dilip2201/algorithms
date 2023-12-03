# 8 Chunk array into given size

```
function chunkArray(array,size) {
    
    //#Solution 1
    let finalChunkArray = []
    let selectedI = 0;
    for (let i = 0; i < array.length; i++) {
        if(!finalChunkArray[selectedI]) finalChunkArray[selectedI] = [];
        finalChunkArray[selectedI].push(array[i]);
        if(finalChunkArray[selectedI].length == size) selectedI++;
    }
    return finalChunkArray;

    //#Solution 2
    let chunked = [];
    let index = 0;
    while(index < array.length){
        chunked.push(array.slice(index,index+size));
        index = index + size;
        
    }
    return chunked;
   
};

chunkArray([1,2,3,4,5,6,7,8,9,10],3);
```