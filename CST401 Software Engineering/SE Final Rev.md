# Chapter 12 Object Orientation Design & Modelling with UML
## 12.1 Object Oriented Design
What is object orientation?
- programming paradigm

2 paradigm:
- ==Procedural Paradigm==:
	- Basically making ==separate function==
	- It separates the data (the ingredients) from the procedures or routines (the cooking steps) that operate on that data.
- ==Object-Oriented Paradigm==:
	- ==Each object combines== both its ==data== (attributes) and its ==behaviors== (methods) into one neat package

Characteristic of OOD:
- ==Modularity==: divided into distinct objects (clear responsibility)
- ==Encapsulation==: Data and methods combined in objects (internal details are hidden)
- ==Abstraction==: Focus on essential qualities
- ==Inheritance==: Share common structure and behavior from its parent
- ==Polymorphism==: Object can take many form

Advantages:
- Reusability
- Scalability
- Maintainability
- Real-World Mapping

Object-Oriented Analysis (OOA):
- Creates an object model representing problem domain
Object-Oriented Design (OOD):
- Creates an object-oriented system to meet requirement
Object-Oriented Programming (OOP):
Implements the design using an object-oriented language like Java or C++.

## 12.2 Classes and Objects
![[Pasted image 20260719152611.png]]
- Objects: instances of real-world or system entities
	- Has:
		- State
		- Operation
- Classes:
	- Templates to create object
	- able to inherit attributes and behavior from other classes
### 12.2.1 Object Communication: Message Passing
Service name $\rightarrow$ method name
Information $\rightarrow$ parameters



## 12.3 Generalisation and Inheritance
- Superclass: general concept shared by one or more subclasses
- Subclass: Inherits attributes and function from superclass, can also introduces new attributes and function.
![[Pasted image 20260719153533.png]]
![[Pasted image 20260719153543.png]]

Inheritance advantages:
- abstraction mechanism
- Reuseable
Inheritance Problem:
- Object classes are not fully self-contained
- can cause inefficiencies
- maintained separately

## 12.4 Unified Modelling Language (UML)
![[Pasted image 20260719155013.png]]
- (-) Private
- (+) Public
- (0..1) 0 to 1


# Chapter 13 Object Orientation Design & Modelling with UML
## 13.1 Modelling Interactions and Behavior
### 13.1.1 Interaction Diagram
#### Sequence diagrams
![[Pasted image 20260719182553.png]]
- Vertical dimension represent time
- Vertical line, called a lifeline
- message is represented as an arrow
	- can have an argument list and a return value

#### Collaboration diagrams
![[Pasted image 20260719183530.png]]
![[Pasted image 20260719183730.png]]

#### State Diagrams
![[Pasted image 20260719184306.png]]

#### Activity Diagrams
![[Pasted image 20260719210246.png]]

## 13.2 Object-oriented Design Process
Process:
- Define the process
- Design system architecture
- Identify principal system object
- Develop design models
- Specify object interfaces 