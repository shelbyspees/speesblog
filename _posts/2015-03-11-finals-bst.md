---
layout: post
title: "Finals: Binary Search Tree"
category: "data_structures"
---

This time I'm going to discuss one way to implement the Binary Search Tree in C. 

I won't pretend that this is the best way or even a good way. This is just the way I have to know it for my final on Sunday. (Yes, I scheduled my final on a Sunday. That means I get to start spring break on Tuesday after my other final. It's not like I'm going to do anything fun on the Sunday before finals week.)

{% highlight c %}
{% endhighlight %}

First let's look at the `struct` for a basic BST.

{% highlight c %}
struct BSTree {
	struct Node * root;
	int count;
};
{% endhighlight %}

We have a `root` node and a `count` variable. `count` represents the number of nodes on the tree, and `root` is the top node on the tree. Before we look at the structure of a `Node`, let's see how we create a tree.

{% highlight c %}
//create new BST from scratch
//return a tree with NULL root and zero nodes
struct BSTree * newBSTree() {
	struct BSTree * tree = (struct BSTree *) malloc(sizeof(tree));
	assert(tree != NULL); //successfully allocated

	_initBSTree(tree);
	return tree;
}
{% endhighlight %}

We allocate a pointer variable called `tree` that points to a `struct BSTree` object, and assert that it worked. By using a pointer, we can change the value of the members of the `struct BSTree` without passing them individually into the function being used to change those values. This is why pointers are cool.

Then we call `_initBSTree` on `tree`. I'm using underscores to identify private functions. I think in Java you can do this with classes and things. I'll learn Java eventually.

{% highlight c %}
//call after allocating tree
//initialize count and root node
void _initBSTree(struct BSTree * tree) {
	tree->count = 0;
	tree->root = NULL;
}
{% endhighlight %}

Here's a visualization of what this gives us:

<img class="wide" src="{{ site.url }}/assets/comp/initBST.png"/>

Everything in that image is a part of `tree`. 

`tree` exists, and it points to `root`, but `root` is actually nothing? How is that possible? Well, `root` is just the variable name for the memory location. There doesn't have to be anything at that memory location. 

Think of it like an empty lot. There's a building at 55 Main St. and a building at 59 Main St., but 57 Main St. can still be an empty lot. If you try to send mail there, it'll bounce back. In computer terms, that's called a `segmentation fault`, and we really don't like those.

So now we have a value and we want to add it to the tree. The value is added in the form of a node, and in this case, it's going to become the root node. Say we add a node with the value `17`. (I won't discuss applications of the BST here, but assume we have a good reason for doing so.)

<img class="wide" src="{{ site.url }}/assets/comp/init-addBST.png"/>
