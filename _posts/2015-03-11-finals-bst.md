---
layout: post
title: "Finals: Binary Search Tree"
category: "data_structures"
---

This time I'm going to discuss one way to implement the binary search tree in C. 

I won't pretend that this is the best way or even a good way. This is just the way I have to know it for my final on Sunday. (Yes, I scheduled my final on a Sunday. That means I get to start spring break on Tuesday after my other final. It's not like I'm going to do anything fun on the Sunday before finals week.)

Here's the most basic functionality of a binary search tree:

{% highlight c %}
void add(value);
int  contains(value); //1 for yes, 0 for no
void remove(value);
{% endhighlight %}

First let's look at the `struct` for a basic BST.

{% highlight c %}
struct BST {
	struct Node * root;
	int count;
};
{% endhighlight %}

We have a `root` node and a `count` variable. `count` represents the number of nodes on the tree, and `root` is the top node on the tree. Before we look at the structure of a `struct Node` object, let's see how we create a tree.

{% highlight c %}
//create new BST from scratch
//return a tree with NULL root and zero nodes
struct BST * newBST() {
	struct BST * tree = (struct BST *) malloc(sizeof(tree));
	assert(tree != NULL); //successfully allocated

	_initBST(tree);
	return tree;
}
{% endhighlight %}

We allocate a pointer variable called `tree` that points to a `struct BST` object, and assert that it worked. By using a pointer, we can change the value of the members of the `struct BST` without passing them individually into the function being used to change those values. This is why pointers are cool.

Then we call `_initBSTree` on `tree`. I'm using underscores to identify private functions. I think in Java you can do this with classes and things. I'll learn Java eventually.

{% highlight c %}
//call after allocating tree
//initialize count and root node
void _initBST(struct BST * tree) {
	tree->count = 0;
	tree->root = NULL;
}
{% endhighlight %}

Here's a visualization of what this gives us:

<img class="wide" src="{{ site.url }}/assets/comp/initBST.png"/>

Everything in this image is a part of `tree`. 

`tree` exists, and it points to `root`, but `root` is actually nothing? How is that possible? Well, `root` is just the variable name for the memory location. There doesn't have to be anything at that memory location. 

Think of it like an empty lot. There's a building at 55 Main St. and a building at 59 Main St., but 57 Main St. can still be an empty lot. If you try to send mail there, it'll bounce back. In computer terms, that's called a `segmentation fault`, and we really don't like those.

So now we have a value and we want to add it to the tree. The value is added in the form of a node, and in this case, it's going to become the root node. Say we add a node with the value `17`. (I won't discuss [applications of the BST]() here, but assume we have a good reason for doing so.)

<img class="wide" src="{{ site.url }}/assets/comp/init-addBST.png"/>

Now the value that `root` holds is `17`. "But wait a second, doesn't `tree` point to `17`?" you ask. Well, `tree` points to `root`, and `root` is a `struct Node` object that holds the integer value `17`. Now's probably a good time to discuss the composition of a `struct Node` object.

{% highlight c %}
struct Node {
	TYPE val; //for now, 'TYPE' is going to be 'int'
	struct Node * left;
	struct Node * right;
};
{% endhighlight %}

Wait a second, computers don't have `left` and `right`. What could this possibly mean??

Well, let's look at a more full tree to understand the purpose of this better.

<img class="wide" src="{{ site.url }}/assets/comp/bst-colors.png"/>

Obviously the computer doesn't see any of this, it's just an arbitrary categorization (like masculine and feminine in Romance languages). But it helps us define ways to organize the data.

Circled in yellow is the `root` node, currently holding the value `42`. All of the values of the ***left children*** of the `root` (highlighted in blue) are less than `42` and all of the values of the ***right children*** (highlighted in red) are greater than `42`.

Isn't that neat? Even as you go down the subtree, the values of the left children of each node is less than the value at the node, and all the values of the right children are greater.

<img class="wide" src="{{ site.url }}/assets/comp/bst-sub-colors.png"/>

So now if we try to search for our original value of `17`, we go *left* of `42`, *right* of `16`, and *left* of `19`. That's a lot of trouble for just finding one number, isn't it? Actually it isn't.

Let's look at the array version of the same sorted list:


    [1, 10, 15, 16, 17, 19, 30, 42, 43, 45, 47, 50, 75, 90, 101] //count is 15


For a computer, iterating through this list to find `17` takes five comparisons, whereas our binary search tree only takes four. And what if we're searching for `101`? That takes fifteen comparisons, but the BST still only takes four. Significantly more efficient, don't you think?

Here's the array visual of binary search for variety:

    [1, 10, 15, 16, 17, 19, 30, 42, 43, 45, 47, 50, 75, 90, 101] //less than 42
    [1, 10, 15, 16, 17, 19, 30] //greater than 16
    [17, 19, 30] //less than 19
    [17] //equal to 17, found it!

The number of elements gets cut in half with each comparison, which gives us O(log(n)) time.

This is especially efficient when looking for a value not contained in the data, like `55`:

    [1, 10, 15, 16, 17, 19, 30, 42, 43, 45, 47, 50, 75, 90, 101] //greater than 42
    [43, 45, 47, 50, 75, 90, 101] //greater than 50
    [75, 90, 101] //less than 90
    [75] //less than 75, but 75 has no children

So in this case `contains(55)` would tell us "Nope, not in here."

So how to we keep the list sorted as we `add` and `remove` values? The short answer is: **recursion**.

On the outside, our `add` function looks like this:

{% highlight c %}
//add value to tree
void addBST(struct BST * tree, TYPE val) {
	tree->root = _addNode(tree->root, val);
	tree->count++;
}
{% endhighlight %}

Notice how we plug in the `tree`'s `root` instead of the tree itself in that internal `_addNode` function. That's your hint that we'll be using recursion, since the `root` is just like any other node in the tree.

Here's the pseudocode for the `_addNode` function:

{% highlight c %}
_addNode
	plug in current node and value to be added
	if (current == NULL)
		create a new node with value to be added and return it

	else recursively look for empty child node
		if value to be added < current->value
			call _addNode with left child and value to be added
		else if value to be added > current->value
			call _addNode with right child and value to be added
		//else current->value == value to be added

	return pointer to current node
{% endhighlight %}

And here's the implementation in C:

{% highlight c %}
//recursively look for empty child to find a place to add the node
struct Node * _addNode(struct Node * cur, TYPE val) {
	struct Node * newnode;
	if (cur == NULL) {	//create new node and return
		newnode = (struct Node *) malloc(sizeof(newnode));
		assert(newnode != NULL); //successfully allocated
		newnode->val = val;
		newnode->left = NULL;
		newnode->right = NULL;
		return newnode;
	}
	//recursively look for empty child node
	if ( -1 == compare(val, cur->val) ) { //val < cur->val, go left
		cur->left = _addNode(cur->left,val);
	}
	else if ( 1 == compare(val, cur->val) ) { //val > cur->val, go right
		cur->right = _addNode(cur->right, val);
	} // else cur->val == val
	return cur;
}
{% endhighlight %}

The nice thing about this `add` function is that you only have to go down the tree. The tree will always be sorted. Let's see it in action.

Say I wanted to add the value `55` to my tree after quickly learning it wasn't there thanks to my super fast `contains` function.

<img class="wide" src="{{ site.url }}/assets/comp/bst-add-colors.png"/>

The tree will always be sorted, but it won't always be balanced. Let's go back to our sorted array:

    sortedArray = [1, 10, 15, 16, 17, 19, 30, 
    	42, 43, 45, 47, 50, 75, 90, 101] //count is 15

Imagine I wrote some code like this:

{% highlight c %}
for (i = 0; i < count; i++) {
	addBST(tree, sortedArray[i]);
}
{% endhighlight %}

We would end up with a tree that looks like this:

