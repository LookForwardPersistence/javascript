# 引擎主要由两部分组成:

内存堆：这是内存分配发生的地方
调用栈：这是你的代码执行时的地方

http://caibaojian.com/fedbook/practice/front-end-interview.html

# 双向链表
function LinkedList(){
		this.head = null
		this.tail = null
	}

    function Node(value,next,prev) {
    	this.value = value
    	this.next = next
    	this.prev= prev
    }
	
LinkedList.prototype.addToTail = function(value) {
  var newNode = new Node(value, null, this.tail);
  if (this.tail) this.tail.next = newNode;
  else this.head = newNode;
  this.tail = newNode;
};
 
 LinkedList.prototype.removeFromTail = function() {
 	if (!this.tail) return null
 		var value = this.tail.value
 	this.tail = this.tail.prev
 	if (this.tail) this.tail.next = null
 		else this.head = null
 }
 LinkedList.prototype.search = function(searchText) {
 	var currentNode = this.head
 	while(currentNode){
 		if (currentNode.value === searchText){
 			return currentNode
 		}
 		currentNode = currentNode.next
 	}
 	return null
 }
 LinkedList.prototype.insertAfter = function(insertText,beforeVuale) {
 	var newNode = new Node(insertText,null,null)
   var currentNode = this.search(beforeVuale)
   if(currentNode.next){
   	currentNode.next = newNode
   	newNode.prev = currentNode
   }
 }
var ll = new LinkedList();
ll.addToTail(1);
ll.addToTail(2)
ll.addToTail(3)
ll.addToTail(4)
ll.addToTail(5)
ll.addToTail(6)
ll.addToTail(7)
console.log('before remove the tail:')
console.log(ll)
console.log(ll.removeFromTail())
console.log('after remove the tail')
console.log(ll) 
console.log('search 5:')
console.log(ll.search(5))
