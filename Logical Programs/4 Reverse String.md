```
function reverse(string) {
    //#solution 1
    return string.split("").reverse().join("");
    
    //#solution 2
    let finalString = "";
    for (let i = string.length - 1; i >= 0; i--) {
        finalString += string[i];
    }
    return finalString;

    //#solution 3
    return string.split("").reduce((prev,current) => {
        return current + prev;
    },"")
};

reverse("apple");
```