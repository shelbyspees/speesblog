---
layout: post
title: "Trees Overview"
category: school
---

No thanks, I don't like the stuff.

Oh wait a second, we're talking about data structures. I can get on board with this.

The **tree** is an important data structure. It's like a big linked list with tons of links. We usually represent it with a *root* node at the top (which confuses people who are familiar with actual trees) and *child* nodes cascading down. Any node that doesn't have a child is called a *leaf* node. 

A simple visualization:

<img class="img-responsive" src="{{ site.url }}/assets/comp/simple-tree.png"/>

The following is a *binary* tree, meaning that each node has a maximum of two child nodes, and a *full* tree, meaning that each vertical row of the tree is filled in (the tree also happens to be [sorted]({{ site.url }}{% post_url 2015-03-11-finals-bst %}#add)):

<img class="img-responsive" src="{{ site.url }}/assets/comp/bst.png"/>

A *complete* tree fills in every node from left to right on each height level. This is hard to understand without seeing it, so here is an example of a *complete* tree that is not *full*.

<img class="img-responsive" src="{{ site.url }}/assets/comp/complete-tree.png"/>

>If an algorithm is of Θ(g(n)), it means that the running time of the algorithm as n (input size) gets larger is proportional to g(n).

>If an algorithm is of O(g(n)), it means that the running time of the algorithm as n gets larger is ***at most*** proportional to g(n).

- The height of any binary search tree with *n* nodes is *O(log(n))
	- FALSE. In the best case, the height of a BST is O(log n) if it is balanced. In the worst case, however, it can be Θ(n).
- Inserting into an AVL tree with *n* nodes requires Θ(log(n)) rotations.
	- FALSE.
- Inserting into an AVL tree may look at O(log(n)) nodes.
	- TRUE.





<h3 class="anchor" id="height-balanced">Height-balanced trees</h3>

What I'm going to try to understand right now is the height-balancing aspect of AVL trees.

<img class="img-responsive" src="{{ site.url }}/assets/comp/tree-height.png"/>

I labeled the **height** for each node in the above tree. You can see that it's neither *full* nor *complete*, but it is indeed <a href="#" class="tooltip-bottom" data-tooltip="Each node has two children.">*binary*</a>.

We measure the *height* of each node by starting from the bottom and counting up. All *leaf* nodes will have a height of `0`. Then count up to the next node. You can't do it exactly sequentially because you might end up with the wrong height for the root node. Look at the brown dotted lines to see the path I followed, and try to get the pattern.

**The height of a particular node is counted using the *longest* path to a leaf node.**

For the AVL tree we mostly care about the *difference* in height each node has with its sibling.

The AVL tree is going to be locally (normal) balanced and globally unbalanced.

[illustration showing local balance vs. global balance]

First, we're going to measure the height of `NULL` nodes as `-1`. See how I added a `NULL` node in the empty spot below in grey:

<img class="img-responsive" src="{{ site.url }}/assets/comp/tree-null-height.png"/>

The above tree is still balanced because there are no sibling nodes with height difference greater than one.

So what's an example of an *height-unbalanced* tree? 

<img class="img-responsive" src="{{ site.url }}/assets/comp/tree-unbalanced-height.png"/>

The teal node has a right child node with a height of `1`, and a `NULL` value where the right child would be, with an imagined height of `-1`. You also notice that the pink and teal nodes have a height difference greater than one, and this is expected because the teal node's children are unbalanced.

It's best to look for unbalanced nodes down in the leaves because that's where it's easiest to rotate.

**Balance factor = height(right subtree) - height(left subtree)**

At an unbalanced node N, a double rotation is needed when:

- N’s BF is positive and N’s right subtree’s BF is negative
- N’s BF is negative and N’s left subtree’s BF is positive.

{% highlight c %}
struct AVLTree*  newAVLTree();
void addAVLTree(struct AVLTree *tree, TYPE val);

void treeSort (TYPE data[], int n) {…}
void _treeSortHelper(AVLNode *cur, TYPE *data, int *count)
{% endhighlight %}

{% highlight c %}
void treeSort(TYPE data[], int n){
    int i; int count = 0;

	//declare an AVL tree
    struct AVLTree *tree = newAVLtree();
    assert(data != NULL && n > 0);

	//add elements to the tree
    for (i = 0; i < n; i++)
        addAVLTree(tree, data[i]);

	//call the helper function
    _treeSortHelper(tree->root, data, &count);
}
{% endhighlight %}

{% highlight c %}
//count goes from 0 to n-1
void _treeSortHelper(AVLNode *cur, TYPE *data, int *count){
     if (cur != NULL) {
        _treeSortHelper(cur->left, data, count);
        data[*count] = cur->val;
        (*count)++;
        _treeSortHelper(cur->right, data, count);
    }
}
{% endhighlight %}

{% highlight c %}
{% endhighlight %}
