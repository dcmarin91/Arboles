# Ejercicios Arboles

## Medodo add

```
binaryTree.prototype.add = function(val){
   var root = this.root;

   if(!root){
      this.root = new Node(val);
      return;
   }

   var currentNode = root;
   var newNode = new Node(val);

   while(currentNode){
      if(val < currentNode.value){
          if(!currentNode.left){
             currentNode.left = newNode;
             break;
          }
          else{
             currentNode = currentNode.left;
        }
     }
     else{
         if(!currentNode.right){
            currentNode.right = newNode;
            break;
         }
         else{
            currentNode = currentNode.right;
         }
     }
  }
}

function binaryTree(){
  this.root = null;
}

function Node(val){
  this.value = val;
  this.left = null;
  this.right = null;
}

var bst = new binaryTree();
bst.add(4);
bst.add(2);
bst.add(7);
bst.add(1);
bst.add(3)
console.log(bst)

```

## Ejercicio 2 TraverseDFS

```
function DFS(node){
  if(node){
    console.log(node.value);
    DFS(node.left);
    DFS(node.right);
  }

}

binaryTree.prototype.traverseDFS=()=>{
  let root=this.root;
  DFS(root);
}

```
## Ejercicio 3 TraverseBFS

```function levelOrderSearch(rootNode) {
  if (rootNode === null) {
    return;
  }

  var queue = [];
  queue.push(rootNode);

  while (queue.length > 0) {
    var currentNode = queue[0];
    if (currentNode.left !== null) {
      queue.push(currentNode.left)
    }
    if (currentNode.right !== null) {
      queue.push(currentNode.right)
    }
    // Remove the currentNode from the queue.
    queue.shift()
  }
}
```
