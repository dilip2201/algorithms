# 7 Singly Link List
```
class node{
	constructor(val){
		this.val = val;
		this.next = null
	}
}

class SinglyLinkList {
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
		}else{
			this.tail.next = newNode;
			this.tail = newNode;
		}
		this.length++;
	}
	pop(){
		if(!this.head) return undefined;
		var current = this.head;
		let newTail =current;
		while(current.next){
			newTail = current;
			current = current.next;
		}
		this.tail = newTail;
		this.tail.next = null;
		this.length--
		if(this.length == 0){
			this.head = null;
			this.tail = null
		}
		return current;
	}

	shift(){
		if(!this.length) return undefined;
		var current = this.head;
		this.head = current.next;
		this.length--;
		if(this.length){
			this.tail = null;
		}
	}
	unshift(val){
		var newNode = new node(val)
		if(!this.head){
			this.head = newNode;
			this.tail = this.head;
		}
		var temp = this.head;
		newNode.next = temp;
		this.head = newNode;
		this.length++
	}
	get(index){
		if(index < 0 || index >= this.length) return null;
		let current = this.head;
		let find = 0;
		while(find !== index){
			current = current.next;
			find++
		}
		return current;
	}

	set(val,index){
		const current = this.get(index);
		if(current){
			current.val = val;	
		}
		
	}
	insert(val,index){
		if(index < 0 || index > this.length) return false;
		if(index === this.length) this.push(val);
		if(index === 0) this.unshift(val);
		var previous = this.get(index-1);
		var newNode = new node(val);
		var temp = previous.next;
		newNode.next = temp;
		previous.next = newNode;
		this.length++
		return true
	}
	remove(index){
		if(index < 0 || index > this.length - 1) return null;
		if(index === 0) this.shift();
		if(index === this.length -1) return this.pop(); 
		var previousNode = this.get(index - 1)
		var removed = previousNode.next; 
		previousNode.next = removed.next;
		this.length--
		return removed;
	}
}

var list = new SinglyLinkList();
list.push(1);
list.push(2);
list.push(3);
list.push(4);
list.push(5);
list.push(6);

```
