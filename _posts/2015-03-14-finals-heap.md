---
layout: post
title: Heap Implementation and Heap Sort
category: data_structures
---

I'm going to represent a heap using a dynamic array.

###Heap Implementation

Suppose the `root` has index `0`, what are the indices of the two children of a node at index `i`? 

```
leftChild 	= 2i + 1
rightChild 	= 2i + 2
```

What is the index of the parent of a node at index `i`? 

```
(i-1)/2
```


###Heap Sort

[Source.](http://www.cprogramming.com/tutorial/computersciencetheory/heapsort.html)

>The first important thing to remember about heaps is that the top element of the heap is always "next" in order (either the next highest or next lowest, in the case of numbers). Think about the consequences of this fact -- if we take all of our input values and store them in a heap, and we remove one element at a time, we will remove these elements in sorted order. But how fast is doing this?

>There are two factors at work: the time it takes to create a heap by adding each element and the time it takes to remove all of the elements from a heap. Fortunately, **we have a guarantee that adding a single element to and removing a single element from a heap both take O(log(n)) time**. As noted above, each of these operations takes place once for each element in the input. Consequently, the algorithmic efficiency of a heap sort is O(n*log(n)), rather good indeed. 

>There are, however, a few tradeoffs. First, **heap sort will always take O(n*log(n)) time** -- while this means that its worst-case efficiency is more robust than any algorithm previously discussed, it means that even the best case time is O(n*log(n)). As you may recall, bubble sort can be optimized so that it takes only O(n) time in the best case! 

>Moreover, the simple implementation of heap sort will require additional space sufficient to hold a heap of size n, meaning that **you need at least double the amount of space for heapsort as you do for our previous sorts**. And creating a heap may have other consequences, such as increasing the constant that is normally dropped in big-O notation. As a result, for small data sets, heap sort might not be the fastest choice! 

>A last consideration is that heap sort is not a "stable" sort in the sense that **it doesn't preserve the original order of equal elements**. This might matter if, for instance, you had a list of emails that you wanted to sort by date, and you also wanted to sort alphabetically by sender. One option would be to first sort the emails alphabetically, and then sort by the date received. A stable sort would keep the alphabetical order for emails sent on the same day; an unstable sort would not. 

Steps to perform heap sort:

1. Build heap
2. Swap the first and last element
3. Adjust heap
4. Repeat steps 2 and 3 but exclude the last element


This is the C++ implementation. Will change this later.

{% highlight c %}
// Built-in Heap Sort algorithm
DynArr * HeapTreeSort(void) {
	// This is the array that will be returned
	Elem * NewArray = new DynArr[cur];

	// The algorithm works back to front, with the sorted
	// elements being stored in NewArray
	for (int index = cur-1; index >=0; --index) {
	    // Since the Remove() function alters cur by subtracting 1
	    // from it each time, we must use a seperate variable to
	    // index NewArray.
		NewArray[index] = Remove();
	}
  	return NewArray;
}
{% endhighlight %}
