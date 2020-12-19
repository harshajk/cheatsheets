# Datatypes

## Advanced data types

### Abstract data type:
An abstract data type (ADT) is a type that consists of a collection of data and associated operations for manipulating the data. The ADT will only mention the list of operations that can be performed byt not the implementation. The implementation itself is hidden which is why it's called **abstract**.

ADT has to control all copy operations to avoid dynamic memoty aliasing problems caused by shallow copying.

### C++ Class
Classes are containers for variables and the operations (methods) that will affect the variables. As ADT's implement encapsulation techniquest for groupinf all similar data and functions into a group, the classes can also be applied to group them. A class has three access control sections for wrapping the data ans methods, and they are:

**Public**: Data and methods can be accessed by any user of the class.

**Protected**: Data and methods can only be accessed by class methods, derived classes, and friends.
    * **Private**: Data and methods cna only be accessed by class methods and friends.

### Templates
The templates are the features that allow the functions and classes to operate with generic types. It makes a function or class work on many differernt data types without having to be rewritten for each one. Using the template, we can build various data types.

### Function Templates
Function templates allows us to create a single function instead of two different functions for different data types.

```cpp
/* Function templates */
#include <iostream>
using namespace std

class Animal
{
    protected:
        string m_name;

    public:
        Animal(string name) : m_name(name) { }

        /* The interface that has to be implemented in derived class */
        virtual string MakeSound() = 0;

        string GetName()
        {
            return m_name;
        }

};

class Dog : public Animal
{
public:
    /* Forward the constructor arguments */
    Dog(string name) : Animal(name) {}

    /* Copy assignment operator overloading */
    void operator = (const Dog &D)
    {
        m_name = D.m_name;
    }

    /* Here we implement the interface */
    string MakeSound() override
    {
        return "woof-woof!";
    }
};

class Cat : public Animal
{
public:
    /* Forward the constructor arguments */
    Cat(string name) : Animal(name) {}

    /* Copy assignment operator overloading */
    void operator = (const Cat &C)
    {
        m_name = C.m_name;
    }    

    /* Here we implement the interface */
    string MakeSound() override
    {
        return "meow-meow!";
    }
};

template<typename T>
void GetNameAndMakeSound (T& theAnimal)
{
    cout << theAnimal.GetName() << " goes ";
    cout << theAnimal.MakeSound() << endl;
}

int main ()
{
    Dog dog = Dog("Bulldog");
    GetNameAndMakeSound(dog);

    Cat cat = Cat("Persian Cat");
    GetNameAndMakeSound(cat);

    return 0;
}

```

### Class templates
Similar to the function template, the class template is used to build a generic class that can accept various data types. 

```cpp
#include <iostream>

using namespace std;

class Animal
{
protected:
    string m_name;

public:
    Animal(string name) : m_name(name) { }

    /* The interface that has to be implemented in derived class */
    virtual string MakeSound() = 0;

    string GetName()
    {
        return m_name;
    }
};

class Dog : public Animal
{
public:
    /* Forward the constructor arguments */
    Dog(string name) : Animal(name) {}
    
    /* Copy assignment operator overloading */
    void operator = (const Dog &D)
    {
        m_name = D.m_name;
    }

    /* Here we implement the interface */
    string MakeSound() override
    {
        return "woof-woof!";
    }
};

class Cat : public Animal
{
public:
    /* Forward the constructor arguments */
    Cat(string name) : Animal(name) {}

    /* Copy assignment operator overloading */
    void operator = (const Cat &C)
    {
        m_name = C.m_name;
    }

    /* Here we implement the interface */
    string MakeSound() override
    {
        return "meow-meow!";
    }
};

template<typename T>
void GetNameAndMakeSound(T& theAnimal)
{
    cout << theAnimal.GetName() << " goes ";
    cout << theAnimal.MakeSound() << endl;
}

template <typename T>
class AnimalTemplate
{
private:
    T m_animal;

public:
    AnimalTemplate(T animal) : m_animal(animal) {}

    void GetNameAndMakeSound()
    {
        cout << m_animal.GetName() << " goes ";
        cout << m_animal.MakeSound() << endl;
    }
};    

int main()
{
    Dog dog = Dog("Bulldog");
    AnimalTemplate<Dog> dogTemplate(dog);
    dogTemplate.GetNameAndMakeSound();

    Cat cat = Cat("Persian Cat");
    AnimalTemplate<Cat> catTemplate(cat);
    catTemplate.GetNameAndMakeSound();
    
    return 0;
}
```

We have a new class name AnimalTemplate. It's a template class and it can be used by any data type. However, we have to define the data type in the angle bracket, when we use the instances dogTemplate and catTemplate.

### Standard Template Library
C++ programming has another powerful feature regarding the use of template classes, which is the Standard Template Library. It's a set of class templates to provide all functions that are commonly used in manipulating various data structures. 

There are four components thar build the STL, and they are 
- Algorithms
- Containers
- Iterators
- Functions

Algorithms: used on ranges of elements such as sorting and searching.

Containers: used to store objects and data. The common container that is widely used is vector. The vector is similar to an array, except it has the ability to resize itself automatically when an element is inserted or deleted.

Iterators: used to work upon a sequence of values. Each container has its own iterator. For instance, there are begin(), end(), rbegin(), and rend() functions in the vector container.

Functions are used to overload the existing function. The instance of this componene is called a functor, or function object. The functor is defined as a pointer of a function where we can parameterize the existing function.

