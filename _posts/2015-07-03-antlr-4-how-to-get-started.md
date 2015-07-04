---
layout: post
title: "ANTLR 4: How to Get Started"
category: programming
---

At my internship I'm developing a tool to translate legacy code to C++. ANTLR is going to help me do it.

This is my first time using ANTLR or any parsing tool like it, and this is also my first time building a project in Java. Lots to learn. I'm writing this to help other people like me, with no background in computer languages or Java development, get started.

The benefit of ANTLR 4 is that it automatically builds a lot of the Java files for you from your grammar, so you don't have to think about how to turn your grammar logic into Java logic. Once you get the hang of ANTLR's tokens and rules, the grammar part isn't too painful.

For me, understanding the Java has been the more painful part. ANTLR has some good proper Java API documentation but nothing that can explain the point of using any of these classes or methods in plain English.

I'm a fan of plain English.

**Lexer:** the lexer's job is to look for *tokens* in your input. You define your tokens in your grammar (`.g4`) file. Token identifiers start with a capital letter, but I usually like to keep my tokens in all caps so they're easier to differentiate from rule identifiers

```txt
fragment DIGIT : [0-9] ; //this is a token, all caps
INT_NUM : DIGIT+ ; //another token, all caps

value //this is a (parser) rule, starts with a lowercase
    : INT_NUM
    ;

```

**Parser:** the parser is basically how Java handles the parser rules you write in your grammar. For example, if my rule says 

**Listener:** ANTLR automatically creates an interface for your grammar's listener based on the ParseTreeListener class

