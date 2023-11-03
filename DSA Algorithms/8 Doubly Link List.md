# 8 Doubly Link List

```
class node{
	constructor(val){
		this.val = val;
		this.next = null;
		this.prev = null;
	}
}

class DoublyLinkList{
	
	constructor(){
		this.head = null;
		this.tail = null;
		this.length = 0;
	}
	push(val){
		
		var newNode = new node(val)
		if(!this.head){
			this.head = newNode;
			this.tail = this.head;
		}else{
			this.tail.next = newNode;
			newNode.prev = this.tail;
			this.tail = newNode;
		}
		this.length++
	}
	pop(){
		
		if(this.length == 1){
			this.head = null;
			this.tail = null
		}else{
			var poppedValue = this.tail;
			this.tail = poppedValue.prev;
			this.tail.next = null;
		}
		this.length--;
	}
	shift(){
		if(this.length == 1){
			this.head = null;
			this.tail = null
		}else{
			this.head = this.head.next;
			this.head.prev = null;
		}
		this.length--;
	}
	unshift(val){
		var newNode = new node(val);
		if(!this.head){
			this.head = newNode;
			this.tail = this.head;
		}else{
			var temp = this.head;
			temp.prev = newNode;
			newNode.next = temp;
			this.head = newNode;
		}
	}

	get(index){
		if(index < 0 || index >= this.length) return null;
		var current = this.head;
		var temp = 0;
		while(temp < index){
			current = current.next;
			temp++;
		}
		return current;
	}
	set(val,index){
		var current = this.get(index);
		if(current){
			current.val = val;
			
		}
	}
	insert(val,index){
		if(index < 0 || index > this.length) return false;
		if(index === 0) return this.unshift(val);
		if(index == this.length) this.push(val);
		var newNode = new node(val);
		if(!this.head){
			this.head = newNode;
			this.tail = this.head
		}else{
			var current = this.get(index - 1);
			newNode.next = current.next;
			current.next.prev = newNode;
			newNode.prev = current;
			current.next = newNode;
		}
		this.length++;
	}

	remove(index){
		if(index < 0 || index > this.length) return false;
		if(index === 0) return this.shift();
		if(index == this.length) this.pop();
		var removeNode = this.get(index);
		removeNode.prev.next = removeNode.next;
		removeNode.next.prev = removeNode.prev;
		
	}
}

var list = new DoublyLinkList;
list.push(10)
list.push(20)
list.push(30)
```