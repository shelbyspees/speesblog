---
layout: post
title: "AVL Tree Implementation"
category: school
published: false
---

Work in progress.

This one's hard cause of the height-balancing thing. But someday soon I'll have a beautifully-composed breakdown of how to implement this data structure. That's my goal for all of these.

{% highlight c %}
struct AVLNode {
	void * val;
	struct AVLNode * left; //left child
	struct AVLNode * right; //right child

	//this is the difference between a BST and an AVL tree
	int height;
};

//Height-Balanced Binary Search Tree
struct AVLTree {
	struct AVLNode *root;
	int count;
};
{% endhighlight %}

###height()

{% highlight c %}
int _height(struct AVLNode * cur) {
	if (cur == NULL)
		return -1;
	return cur->height;
}

void _setHeight(struct AVLNode * cur) {
	int leftHeight = _height(cur->left);
	int rightHeight = _height(cur->right);
	if (leftHeight < rightHeight)
		cur->height = rightHeight + 1;
	else
		cur->height = leftHeight + 1;
}
{% endhighlight %}

The initialization for the AVL tree is exactly the same as for the binary search tree

###contains()

`contains` is also the same for both types of trees.

Note that we're using a weird `comparator typedef` to handle the pointer names.

{% highlight c %}
typedef int (* comparator) (void * left, void * right);
{% endhighlight %}

{% highlight c %}
int containsAVLTree(struct AVLTree * tree, void * val, comparator compare) {
	struct AVLNode * cur;
	cur = tree->root;

	while (cur != NULL) {
		if ((* compare)(cur->val, val) == 0)
			return 1; //found it
		else if ((* compare)(val, cur->val) < 0)
			cur = cur->left;
		else
			cur = cur->right;
	}
	return 0; //does not contain val
}
{% endhighlight %}

###add()

{% highlight c %}
void addAVLTree(struct AVLTree * tree, void * val, comparator compare) {
	tree->root = _addNode(tree->root, val, compare); //call the recursive helper function
	tree->count++;
}
{% endhighlight %}

{% highlight c %}
struct AVLNode * _addNode(struct AVLNode * cur, void * val, comparator compare) {
	struct AVLNode * newNode;
	if (cur == NULL) //base case
			{
		//create a new one and return it
		newNode = (struct AVLNode *) malloc(sizeof(newNode));
		assert(newNode != NULL);
		newNode->left = newNode->right = NULL;
		newNode->val = val;
		newNode->height = 0;
		return newNode;  //no need to balance here
	} else { //recursive case

		if ((*compare)(val, cur->val) < 0)
			cur->left = _addNode(cur->left, val, compare); //functional approach, rebuild subtree
		else
			cur->right = _addNode(cur->right, val, compare);
	}
	//must balance the tree on way up from the recursion
	return _balance(cur); //return the 'rebuilt' tree as come back from recursion
}
{% endhighlight %}

###remove()

{% highlight c %}
void removeAVLTree(struct AVLTree * tree, void * val, comparator compare) {
	if (containsAVLTree(tree, val, compare)) {
		tree->root = _removeNode(tree->root, val, compare);
		tree->count--;
	}
}
{% endhighlight %}

###balance()

{% highlight c %}
//utility function to compute the balance factor of a node
//computed as right - left
int _bf(struct AVLNode * cur) {
	return _height(cur->right) - _height(cur->left);
}

//utility function to balance a node
struct AVLNode * _balance(struct AVLNode * cur) {
	//current balance factor
	int cbf = _bf(cur);

	if(cbf < -1) { //cur is heavy on the left
		if( _bf(cur->left) > 0 ) { //is left child heavy on the right?
			//double rotation
			//rotate left child first
			cur->left = _rotateLeft(cur->left);
		}
		return _rotateRight(cur);
	}
	else if (cbf > 1) { //cur is heavy on the right
		if ( _bf(cur->right < 0) ) { //is right child heavy on the left?
			//double rotation
			//rotate right child first
			cur->right = _rotateRight(cur->right);
		}
		return _rotateLeft(cur);
	}

	_setHeight(cur);
	return cur;
}
{% endhighlight %}

{% highlight c %}
struct AVLNode * _rotateLeft(struct AVLNode *cur) {

	struct AVLNode *newTop;

	newTop = cur->right;
	cur->right = newTop->left;
	newTop->left = cur;
	//reset the heights for all nodes that have changed heights
	_setHeight(cur);
	_setHeight(newTop);

	return newTop;
}
{% endhighlight %}

{% highlight c %}
struct AVLNode * _rotateRight(struct AVLNode *cur) {
	struct AVLNode * newTop;

	newTop = cur->left;
	cur->left = newTop->right;
	newTop->right = cur;
	//reset the heights for all nodes that have changed heights
	_setHeight(cur);
	_setHeight(newTop);

	return newTop;
}
{% endhighlight %}
