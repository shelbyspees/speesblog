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

The following is a *binary* tree, meaning that each node has a maximum of two child nodes, and a *complete* tree, meaning that each vertical row of the tree is full (the tree also happens to be [sorted]({{ site.url }}{% post_url 2015-03-11-finals-bst %})):

<img class="wide" src="{{ site.url }}/assets/comp/bst.png"/>

Here is an example of a *full* tree that is not *complete*.

<img class="wide" src="{{ site.url }}/assets/comp/full-tree.png"/>


---

Height-balanced trees

What I'm going to try to understand right now is the height-balancing aspect of AVL trees.