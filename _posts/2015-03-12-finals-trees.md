---
layout: post
title: "Finals: Trees"
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

We measure the *height* of each node by starting from the bottom and counting up. All *leaf* nodes will have a height of `0`. 