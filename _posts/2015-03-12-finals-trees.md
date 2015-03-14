---
layout: post
title: "Trees"
category: data_structures
---

No thanks, I don't like the stuff.

Oh wait a second, we're talking about data structures. I can get on board with this.

The **tree** is an important data structure. It's like a big linked list with tons of links. We usually represent it with a *root* node at the top (which confuses people who are familiar with actual trees) and *child* nodes cascading down. Any node that doesn't have a child is called a *leaf* node. 

A simple visualization:

<img class="wide" src="{{ site.url }}/assets/comp/simple-tree.png"/>

The following is a *binary* tree, meaning that each node has a maximum of two child nodes, and a *complete* tree, meaning that each vertical row of the tree is full (the tree also happens to be [sorted]({{ site.url }}{% post_url 2015-03-11-finals-bst %}#add)):

<img class="wide" src="{{ site.url }}/assets/comp/bst.png"/>

A *full* tree fills in every node from left to right on each height level. This is hard to understand without seeing it, so here is an example of a *full* tree that is not *complete*.

<img class="wide" src="{{ site.url }}/assets/comp/full-tree.png"/>







<h3 class="anchor" id="height-balanced">Height-balanced trees</h3>

What I'm going to try to understand right now is the height-balancing aspect of AVL trees.

<img class="wide" src="{{ site.url }}/assets/comp/tree-height.png"/>

I labeled the **height** for each node in the above tree. You can see that it's neither *full* nor *complete*, but it is indeed <a href="#" class="tooltip-bottom" data-tooltip="Each node has two children.">*binary*</a>.

We measure the *height* of each node by starting from the bottom and counting up. All *leaf* nodes will have a height of `0`. Then count up to the next node. You can't do it exactly sequentially because you might end up with the wrong height for the root node. Look at the brown dotted lines to see the path I followed, and try to get the pattern.

**The height of a particular node is counted using the *longest* path to a leaf node.**

For the AVL tree we mostly care about the *difference* in height each node has with its sibling.

The AVL tree is going to be locally (normal) balanced and globally unbalanced.

[illustration showing local balance vs. global balance]

First, we're going to measure the height of `NULL` nodes as `-1`. See how I added a `NULL` node in the empty spot below in grey:

<img class="wide" src="{{ site.url }}/assets/comp/tree-null-height.png"/>

The above tree is still balanced because there are no sibling nodes with height difference greater than one.

So what's an example of an *height-unbalanced* tree? 

<img class="wide" src="{{ site.url }}/assets/comp/tree-unbalanced-height.png"/>

The teal node has a right child node with a height of `1`, and a `NULL` value where the right child would be, with an imagined height of `-1`. You also notice that the pink and teal nodes have a height difference greater than one, and this is expected because the teal node's children are unbalanced.

It's best to look for unbalanced nodes down in the leaves because that's where it's easiest to rotate.