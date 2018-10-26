---
layout: post
title: Part 2 - Fundamentals of Generic Programming
date: 2018-10-26
categories: posts
---

I chose this paper purely because I wanted to read someting from Alexander Stepanov. 
If you are a C++ programmer, and don't know who he is, well
if you've written std::vector<int>, that is this guys work.
Writing a dynamic array was not his peak accomplishment, but writing a 
library that utilizes his ideas of common type requirements.

After some time programming with templates, you begin to understand that
every time you take a template parameter *T* to write a function or class,
you have expectations that the user provided type will 
have common properties like comparison, ordering or the addition operator.

In this paper stepanov outlines the type requeirements as a axiomatic set and
declares it as concepts.

The first concept, and most important one, used all over STL is that of a *Regular Type*. 
A type having his default constructor, copy constructor, destructor, assignment, equality, inequality
and ordering. The simplest regular type is an int. The axioms of a regular type
where formed for a type to behave as a integer.

Now let's look at one of the axioms for assignmet. 

$$ T a = c; T b = c; a = d; assert(b == c); $$

This is the first time someone defined the assignment operator and equality operator
in such a way. Humbly stated, we expect to modify the value of $a$ without changing the value of 
$b$. This is in fact the definition of value semantics used in programming languages.

It's a shame concepts did not make it in c++17.

EDIT:

Quote from a talk that came out recently:

>    The containers and algorithms that where a part of the 1998. STL where nothing
>    like the containers and algorithms libraries at the time.
>    Everybody knew that when you had a new container class you had to use inheritence
>    the algorithms had to be member functions of the class, 
>
>    *Sean Parent*

References:

[Sean Parents talk about generic programming](https://www.youtube.com/watch?v=iwJpxWHuZQY)
