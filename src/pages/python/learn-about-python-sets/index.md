---
title: Learn About Python Sets
---
**Sets in Python**

The data type "set", which is a collection type, has been part of Python since version 2.4. A set contains an unordered collection of unique and immutable objects. The set data type is, as the name implies, a Python implementation of the sets as they are known from mathematics. This explains, why sets unlike lists or tuples can't have multiple occurrences of the same element. 
Creating Sets

If we want to create a set, we can call the built-in set function with a sequence or another iterable object. 

In the following example, a string is singularized into its characters to build the resulting set x:
>>> x = set("A Python Tutorial")
>>> x
set(['A', ' ', 'i', 'h', 'l', 'o', 'n', 'P', 'r', 'u', 't', 'a', 'y', 'T'])
>>> type(x)
<type 'set'>
>>> 


We can pass a list to the built-in set function, as we can see in the following: 

>>> x = set(["Perl", "Python", "Java"])
>>> x
set(['Python', 'Java', 'Perl'])
>>> 


We want to show now, what happens, if we pass a tuple with reappearing elements to the set function - in our example the city "Paris": 

>>> cities = set(("Paris", "Lyon", "London","Berlin","Paris","Birmingham"))
>>> cities
set(['Paris', 'Birmingham', 'Lyon', 'London', 'Berlin'])
>>> 


As we have expected, no doublets are in the resulting set of cities.
Immutable Sets

Sets are implemented in a way, which doesn't allow mutable objects. The following example demonstrates that we cannot include for example lists as elements:
>>> cities = set((("Python","Perl"), ("Paris", "Berlin", "London")))
>>> cities = set((["Python","Perl"], ["Paris", "Berlin", "London"]))
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'list'
>>> 


**Frozensets**

Though sets can't contain mutable objects, sets are mutable: 
>>> cities = set(["Frankfurt", "Basel","Freiburg"])
>>> cities.add("Strasbourg")
>>> cities
set(['Freiburg', 'Basel', 'Frankfurt', 'Strasbourg'])
>>> 

Frozensets are like sets except that they cannot be changed, i.e. they are immutable:
>>> cities = frozenset(["Frankfurt", "Basel","Freiburg"])
>>> cities.add("Strasbourg")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'frozenset' object has no attribute 'add'



**Simplified Notation**

We can define sets (since Python2.6) without using the built-in set function. We can use curly braces instead: 
>>> adjectives = {"cheap","expensive","inexpensive","economical"}
>>> adjectives
set(['inexpensive', 'cheap', 'expensive', 'economical'])
>>> 
