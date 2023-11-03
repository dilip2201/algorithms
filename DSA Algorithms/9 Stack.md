# 9 Stack

```
class node{
	constructor(val){
		this.val = val;
		this.next = null;
	}
}

class Stack{
	//LIFO | Last Come will first out.
	constructor(){
		this.head = null;
		this.tail = null;
		this.length = 0;
	}
	
	unshift(val){
		var newNode = new node(val);
		if(!this.head){
			this.head = newNode;
			this.tail = this.head
		}else{
			newNode.next = this.head;
			this.head = newNode;
		}
		this.length++;
	}
	shift(){
		if(this.length == 1){
			this.head = null;
			this.tail = null;
		}else{
			this.head = this.head.next;
		}
		this.length--;
	}
}

var stack = new Stack;
stack.push(5)
stack.push(10)
stack.push(15)
stack.push(20)
```