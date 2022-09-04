# binary-tree
<script>
// javascript program to insert element in binary tree

	/*
	* A binary tree node has key, pointer to left child and a pointer to right
	* child
	*/
class Node {
	constructor(val) {
		this.key = val;
		this.left = null;
		this.right = null;
	}
}

	var temp;

	/* Inorder traversal of a binary tree */
	function inorder(temp) {
		if (temp == null)
			return;

		inorder(temp.left);
		document.write(temp.key + " ");
		inorder(temp.right);
	}

	/* function to insert element in binary tree */
	function insert(temp , key) {

		if (temp == null) {
			root = new Node(key);
			return;
		}
		var q = [];
		q.push(temp);

		// Do level order traversal until we find
		// an empty place.
		while (q.length!=0) {
			temp = q.pop();
			

			if (temp.left == null) {
				temp.left = new Node(key);
				break;
			} else
				q.push(temp.left);

			if (temp.right == null) {
				temp.right = new Node(key);
				break;
			} else
				q.push(temp.right);
		}
	}

	// Driver code
		var root = new Node(10);
		root.left = new Node(11);
		root.left.left = new Node(7);
		root.right = new Node(9);
		root.right.left = new Node(15);
		root.right.right = new Node(8);

		document.write("Inorder traversal before insertion:");
		inorder(root);

		var key = 12;
		insert(root, key);

		document.write("<br\>Inorder traversal after insertion:");
		inorder(root);


</script>
