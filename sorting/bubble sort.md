function bubbleSort(array){
    for (let i = array.length - 1; i >= 0; i--) {
        let noSwap = true;
       for (let j = 0; j <= i; j++) {
           if(array[j] > array[j+1]){
                noSwap = false;
                const temp = array[j]
                array[j] = array[j+1]
                array[j+1] = temp;
            }
       }
        if(noSwap){
            break;
        }
    }
    return array;
}


bubbleSort([18,2,9,1,38,44,32,45,90,54])