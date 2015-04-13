---
layout: post
title: For vs. While
category: programming
---

Last night I was reading through the [Git source code](https://github.com/shelbyspees/git) and I saw a for-loop that started like this: `for(;;)`.

Today I looked it up and found [this really helpful explanation on Stack Overflow](http://stackoverflow.com/a/6348114/3788802), so I'm going to copy it here.

---

Apart from issues of scope and one other thing, this:

    for(<init>; <test>; <step>) {
    	<body>
    }

is the same as:

    <init>
    while(<test>) {
    	<body>
    	<step>
    }

As other people have alluded to, in the same way that you can have a while loop without an <init> form or <step> form, you can have a for loop without them:

    while(<test>) {
    	<body>
    }

is the same as

    for(;<test>;) {
    	<body>
    } //Although this is terrible style

And finally, you could have a

    for(;true;) {
    	<body>
    }

Now, remember when I said there was one other thing? It's that **for loops don't need a test**--yielding the solution everyone else has posted:

    for(;;) {
    	<body>
    }

---