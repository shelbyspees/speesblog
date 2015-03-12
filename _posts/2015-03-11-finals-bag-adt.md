---
layout: post
title: "Finals: Bag Abstract Data Type"
category: "data_structures"
---

The Bag abstract data type has probably the most widespread use, and is therefore probably the easiest to understand.

When I first encountered the Bag ADT, I thought, "Well this doesn't sound very computery." 

A bag of marbles (the original metaphor I was presented with) randomly changes its order, but the simple Bag ADT doesn't really change its order, for the most part. (See [Binary Search Tree](#bst-bag) for an implementation of the Bag ADT that does change the order of its contents.)

How do you choose to use a Bag to contain your data? Here are the main functions of the Bag ADT:

* `add` a new element
* `remove` an existing element
* determine if the bag `contains` an element
* get the current `size` of the bag
* look at element using an `iterator` (don't worry about this for now)

You don't care about the order of the elements at all, just whether an element is contained in the data, basically. 

Think of a grocery list. You `add` items to the list as you remember to them down, and you cross items off (`remove` them from) the list as you pick them up at the store. In this case, you probably don't care about the `size` of your grocery list.

Type-A personalities might go through the list and organize it by food group, or even plan their meals so that they can streamline their shopping trip, but you're not like that. No, you walk up and down each aisle and check your list to see if the food you're looking at is on the list. If you remember something you need during your shopping trip, you can add it to the list right then.

That's how I think of a bag, more or less. Nitpickers might criticize that items that have been crossed off the list are different from items that have been removed, but who pays that much attention to their grocery list? If you're at the store and realize that a bag of almonds is too expensive, you'll cross it off whether you buy it or not.

###Dynamic Array Bag


###Linked List Bag


<h3 class="anchor" id="bst-bag">Binary Search Tree Bag</h3>

The binary search tree really shines when it comes to the bag's `contains` function.

Basically, computers can't understanding non-arbitrary things. Computers are fast and stupid, while humans are slow and smart. Humans can narrow down a bunch of data by semantic category, for example ("Well, all of these words over here are baby names, so I won't find any Britney Spears songs there."). Computers will never be able to natively attribute meaning to data, which is why we have [JSON files](http://www.w3schools.com/json/), for example.

To touch on a much broader topic, this is why self-writing software is still many years away. While [Google's video-game playing AI](http://blogs.discovermagazine.com/crux/2015/02/26/artificial-intelligence-atari-video-games/#.VQDj1BDSm5I) might learn really quickly, it won't be able to handle the ever-changing needs of software stakeholders. At the end of the day, software is a tool to solve [human problems]({% post_url 2015-03-01-read-the-humanities %}), so we need humans to come up with good solutions to those problems.

Anyway, binary search tree. So if you want to make it significantly quicker for your program to find a specific chunk of data in your bag, you have to make it easy for the computer to narrow it down on computer terms. We'll use integers as an example, because it's really easy for both humans and computers to compare integers.

In high school my teachers would assign a unique student ID and sort the student list by ID rather than alphabetically. This allowed teachers to post grade results (in the form of a piece of paper on the wall) without students knowing everyone else's grades. 

| Student ID | Grade |
| --- | --- |
| 12341 | 78.8% |
| 29920 | 66.7% |
| 45612 | 91.2% |
| 59101 | 82.4% |
| 70714 | 90.1% |
| 98261 | 97.5% |

<br/>

So imagine a simple data structure like this one:

{% highlight c %}
struct Student {
	char * name;
	int studID;
	double grade; //percent
};
{% endhighlight %}

Using a binary search tree you could easily have the students sorted by `studID` and then retrieve the value of a student's `grade` by searching for their `studID`.

Assume we care about how long it takes for a program to find a specific element in a ginormous set. It's a lot faster for the program to search data that's sorted. That's why sorting algorithms are pretty much the foundation of computer science.

The way a binary search tree works is by maintaining the sorted nature of the data. Each node in the tree has a left child and a right child. All the left children of the node are smaller than the value held by the node, and all the children to the right are greater than the value held by the node.

So when trying to see whether the tree contains a specific value, the `contains` function first looks at the root/top node. If it matches the value being searched, it returns saying that the element was found successfully (`true` or `1`). 

Otherwise, if the value it's searching for is greater than the value at the root node, it goes to the right child node. If it's less than the value at the root node, it goes to the left child. If there are no child nodes, `contains` returns saying that its search was unsuccessful (`false` or `0`).

Here's an example program using the bag API:

{% highlight c %}
void printGrade(struct BST studList, int studID) {
	if ( contains(studList, studID) ) {
		struct Student * student = getStudentbyID(studList, studID);
		printf("The student's grade is %f", student->grade); //man I hope this syntax isn't wrong
	}
	else {
		printf("The student ID is not in the list.");
	}
}
{% endhighlight %}

And the `getGrade` function would look kind of like this:

{% highlight c %}
//precondition: studID is in the list
struct Student * getStudentbyID(struct BST studList, int studID) {
	struct Student * student = (struct Student *) malloc(sizeof(student));
	struct Student
}
{% endhighlight %}

Here's an example of a binary search tree with reasonably small integer values at each node:

<img class="wide" src="{{ site.url }}/assets/comp/bst.png"/>
