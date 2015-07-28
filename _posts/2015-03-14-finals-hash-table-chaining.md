---
layout: post
title: Hash Table Chaining
category: school
published: false
---

In hash tables with chaining, you have a dynamic array of pointers, where each pointer points to a linked list. The links in the linked list contain the values to be stored.

###init()

{% highlight c %}
void initHashTable(struct HashTable * ht, int size) {
	int i;

	ht->size = size;
	ht->count = 0;

	//allocate dynamic array for ht->table
	//ht->table is an array of pointers
	//each index holds a pointer to a linked list
	ht->table = (struct LinkedList **) malloc(sizeof(struct LinkedList*));

	assert(ht->table != NULL);
	for (i = 0; i < size; i++) {
		//create new linked list to go in each index of ht->table
		ht->table[i] = newList();
	}	
}
{% endhighlight %}

###add()

{% highlight c %}
void addHashTable(struct HashTable * ht, TYPE val) {
	//compute hash table bucket index
	int index = HASH(val) % ht->size;
	if (index < 0) {
		index += ht->size; //handles negative integer value
	}
	
	//add to bucket
	addList(ht->table[index], val);
	ht->count++;

	//next step: reorganize if load factor is too large
}
{% endhighlight %}

This is really nice because we can take advantage of the linked list functions to add the value in our hash table bucket.

###contains()

{% highlight c %}
int containsHashTable(struct HashTable * ht, TYPE val) {
	//find correct bucket, same as add()
	int index = HASH(val) % ht->size;
	if (index < 0) {
		index += ht->size; //handles negative integer value
	}

	//check to see if element is there
	return containsLinkedList(ht->table[index], val);
}
{% endhighlight %}

###remove()

{% highlight c %}
void removeHashTable(struct HashTable * ht, TYPE val) {
	if ( containsHashTable(ht, val) ) {
		int index = HASH(val) % ht->size;
		if (index < 0) {
			index += ht->size; //handles negative integer value
		}

		//remove element from list
		removeLinkedList(ht->table[index], val);
		ht->count--;
	}
}
{% endhighlight %}

###Load factor

The *load factor* represents the average number of elements in each bucket.

>load factor = number of elements / size of table

In open address hashing, the load factor must be less than one, but in chaining the load factor can be greater than one.

Decide on a fixed limit for the load factor. When it reached the limit, double the table size and re-hash all the values to the new table.

###Algorithmic complexity

Assuming:

- Time to compute hash function is constant
- Chaining uses a linked list
- Worst case --> all values hash to same index
- Best case --> hash function uniformly distributes the values

`contains()` will look like this

|      			 | worst case | best case | average case |
| :--- | :--- | :--- | :--- |
| open addressing | O(n) because of probing | O(1) | |
| chaining 		  | O(n) because searching linked list | O(1) | O(load factor) |

We want to keep the load factor relatively small.

- Every key in a hash table must be unique.
	- TRUE.
- Every key in a hash table must map to a unique hash index.
	- FALSE. This is how we get collisions.
- Hash table performance decreases as the number of buckets increases.
	- FALSE. Performance generally increases with number of buckets.
- Hash table searches are linear in the number of records.
	- FALSE. With no collisions, searches are O(1). In general, a hash table search is O(K) where K is the maximum number of records in one bucket.
