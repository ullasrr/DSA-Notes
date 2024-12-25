# OOPs 1

### DATA abstraction

### data encapsulation

### inheritance

### polymorphism

## Class variables →Declaration, initialization and accessing

# OOPs 2

### Static vs Dynamic allocation

stack memory → static (compiler time)

heap memory → dynamic (real time)

## Runtime allocation has syntax

example

```cpp
int *a;
a=new int(5); //dynamic allocation happens here
```

## For classes

```cpp
Player * ullas = new Player;

```

## Nested class, Array of Objects

# OOPs 3

## Constructor and its types

→ Hidden function 

→ Initialization 

→ Object creation 

## Types

1. Default constructor
2. Parametrized constructor
3. Copy constructor

## Destructor → Destroy object

### When a destructor is called?

### → When object goes out of scope

### Copy constructor → Shallow and deep copy

```cpp
//Shallow coppy
Bike b1(50,100);
Bike b2;
b2=b1;

//Deep copy or Copy constructor

Bike b1(50,100);
Bike b2=b1; //Deep copy
Bike b2(b1); //Deep copy
```

# IMP→ For calling copy constructor you have to pass object pass by reference inside constructor