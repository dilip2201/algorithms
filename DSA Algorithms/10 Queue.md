# 10 Queue

```
class node{
	constructor(val){
		this.val = val;
		this.next = null;
	}
}

class Queue{
	//FIFO | First come will first out
	constructor(){
		this.head = null;
		this.tail = null;
		this.length = 0;
	}
	push(val){
		var newNode = new node(val);
		if(!this.head){
			this.head = newNode;
			this.tail = this.head;
		} else{
			this.tail.next = newNode;
			this.tail = newNode;
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

var queue = new Queue;
queue.push(5)
queue.push(10)
queue.push(15)
queue.push(20)
```