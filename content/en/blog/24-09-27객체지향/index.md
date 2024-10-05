---
title: How object orientation works
date: 2024-09-27
---
<a href="https://bong0920.tistory.com/2" class="btn btn-primary">Read the blog</a>


<!--more-->

Abstraction
Abstraction: grouping things together by their common features to extract the required properties or behaviors.

 

Benefits of abstraction

If you don't use abstraction

We have to add a case statement every time a type of car is added.

//When not using abstraction
//Change the oil in the engine
switch(car type)
  case Audi : // oil change process description
  case Mercedes-Benz: // oil change process description
  case BMW : // Oil change process description
 

When using abstractions

No unnecessary work is involved when the type of car is added.

Requiring behavior from a larger concept and doing the actual behavior from a smaller concept (polymorphism).

// Car abstraction
// change engine oil
void changeEngineOil(Car c){
  c.changeEngineOil();
}
 

Encapsulation
Encapsulation: Hiding information to achieve low coupling

 

Why does hiding information lead to low coupling?

It hides your specific behavior.

Hiding your specific behavior means that it can't be interfered with from the outside.

This prevents room for increased coupling.

 

What should I encapsulate?

Specific behavior, likely to change frequently

Example) Engine behavior, data structure in the stack
