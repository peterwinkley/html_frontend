-   [**Object-Oriented
    Programming**](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects)
    **(\"OOP\")**

    -   **About**

        -   OOP is a programming model that uses blueprints to create
            objects. Such blueprints are conventionally called
            **Classes**, and the created objects are called
            **Instances**. The goal is to make classes modular so they
            can be reused and shared among all parts of an application.
            JS does not have \"built-in\" classes in version ES5, but
            they can be implemented via constructor functions and
            objects.

    -   **[New](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new)
        Operator**

        -   As noted in the \"this\" section above, the new operator is
            used together with a constructor function to create a new
            object. The new operator works by:\
            (1) creating an empty object;\
            (2) setting the keyword \"this\" to be that empty object;\
            (3) adding an implicit \"return this\" line to the end of
            the function; and\
            (4) adding a property onto the empty object called
            \"\_\_proto\_\_\" (a.k.a., \"**Dunder** **Proto**\", which
            links the created object to the prototype property on the
            constructor function.

    -   **Multiple Constructors**

        -   When working with multiple constructors, you can make use of
            \"this\" and call to optimize your code, e.g.:\
            function Dog(name, age) {\
            this.name = name;\
            this.age = age;\
            this.bark = function() {\
            console.log(this.name + \' just barked!\');\
            }\
            }\
            function Cat(name, age) {\
            Dog.call(this, name, age);\
            this.meow = function() {\
            console.log(this.name + \' just meowed!\');\
            }\
            }

            -   **NOTE**: It may be confusing to see that \"this\" is
                used as the first argument in Dog.call() of Cat() to
                redefine \"this\" as used in Dog(). However, remember
                that the constructor will be used with the new operator.
                This means that, when new is applied to Cat(), a **[NEW
                OBJECT]{.ul}** will be created in which all \"this\"
                keywords in Cat() will refer to the new cat object (to
                which \"this\" will now apply because the cat is the
                closest parent object). Thus, you can use \"this\" as
                the first argument in Dog.call() to redefine all
                \"this\" keywords in Dog() to refer to the newly created
                Cat() object.

        -   For further optimization, you can use \"this\" and apply
            together with a built-in JS object called
            \"[**arguments**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments)\",
            which is an array-like object corresponding to the arguments
            passed to a function. As \"arguments\" is an array-like
            object, it can be used with apply as a shorthand, e.g.:\
            function Cat(name, age) {\
            Dog.apply(this, **[arguments]{.ul}**);\
            this.meow = function() {\
            console.log(this.name + \' just meowed!\');\
            }\
            }

    -   **Prototypes**

        -   [**Basics**](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object_prototypes)

            -   Prototypes are the mechanism by which JS objects inherit
                features from one another. Upon creation, all
                constructors possess a prototype property, which is an
                object that can have properties and methods attached to
                it. The prototype property has two properties: (1)
                \"constructor\", which relates back to the definition of
                the constructor itself; and (2) \"\_\_proto\_\_\", which
                allows properties or methods of the prototype to be
                accessed by any object created from the constructor.

                -   **NOTE**: The \"\_\_proto\_\_\" property of a
                    created object is identical to the prototype
                    property of the constructor. Thus, if you created an
                    object from a Cat() constructor, the following would
                    be true:\
                    catObject.\_\_proto\_\_ === Cat.prototype

        -   [**Prototype
            Chain**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)

            -   If you want to add a property or method to all objects
                that will be (or, more significantly, already have been)
                created by a constructor, you need only add that
                property/method to the prototype of the constructor. For
                example, you have already created two cats (named
                \"button\" and \"kiwi\") from a Cat() constructor, and
                the only properties in the constructor are \"name\" and
                \"age\". However, you now want to add a property called
                \"isMammal\", which is to be set as \"true\" for all
                cats. You can state...\
                Cat.prototype.isMammal = true;\
                ...which then results in the following statements
                returning true:\
                button.isMammal; // true\
                kiwi.isMammal; // true

            -   In the example above, if you were to access \"button\"
                to view its properties and methods, you would not
                immediately see \"isMammal\" as a property directly
                under \"button\" as you would with \"name\" and \"age\".
                Rather, you would have to access the \"\_\_proto\_\_\"
                property under \"button\" to see \"isMammal\".
                Nevertheless, you are still able to access
                \"button.isMammal\" without saying
                \"button.\_\_proto\_\_.isMammal\". This is because JS
                follows the prototype chain (by following a line of
                \"\_\_proto\_\_\" properties) to locate an object\'s
                properties or methods.

                -   The chain here works as follows:\
                    (1) If the requested property/method is not found
                    directly in the cat object, check the cat\'s
                    \"\_\_proto\_\_\".\
                    (2) If the cat\'s \"\_\_proto\_\_\" (which itself an
                    object constructed by JS\'s built-in
                    [**Object()**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
                    constructor) does not contain the property/method,
                    then refer to the Object() constructor\'s
                    \"\_\_proto\_\_\" nested under the cat\'s
                    \"\_\_proto\_\_\".\
                    (3) If the Object() constructor\'s \"\_\_proto\_\_\"
                    does not contain the property/method, then the
                    result is \"undefined\" and the inquiry goes no
                    further, as the Object() constructor is the last
                    link in the chain.

                -   **NOTE**: This manner in which JS finds methods can
                    be applied to all created objects. For example, all
                    arrays are created by JS\'s built-in Array()
                    constructor, which contains a prototype object to
                    which the \"push\" method (among others) is
                    attached. If you create an array named \"cats\" and
                    you want to push a new cat into the array, you are
                    able to say \"cats.push(\'Stumpy\')\" rather than
                    \"cats.\_\_proto\_\_.push(\'Stumpy\')\" due to
                    prototype chaining.

            -   The prototype chain allows for further **Code
                Optimization**. For example, if you have a Dog()
                constructor and you want to apply a bark() method to
                each dog created by Dog(), you would have a lot of
                repetitive code if you inserted the bark() method
                directly into the Dog() constructor, as the bark()
                method would be repeated in every created dog object
                with the exact same value each time. But by taking
                advantage of the linking capabilities of the prototype
                chain, you could simply state:\
                function Dog(name, age) {\
                this.name = name;\
                this.age = age;\
                }\
                Dog.prototype.bark = function() {\
                console.log(this.name + \' just barked!\');\
                }

-   [**Closures**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)

    -   **About**

        -   A closure is a function that makes use of variables defined
            in outer functions that have previously returned. Consider
            the following example:\
            function outerFunc() {\
            var outerData = \'closures are \';\
            return function innerFunc() {\
            var innerData = \'awesome\';\
            return outerData + innerData;\
            }\
            }

            -   In this example above, if you were to simply call
                outerFunc(), you would only return the definition of the
                inner function, which would appear as:\
                function innerFunc() {\
                var innerData = \'awesome\';\
                return outerData + innerData;\
                }

            -   However, as the result of outerFunc() is itself a
                function, this gives you the ability to call innerFunc()
                immediately upon calling outerFunc() by simply stating
                **[outerFunc()()]{.ul}**, which returns, \"closures are
                awesome\". Because innerFunc() makes use of the returned
                outerData variable defined in outerFunc(), that makes
                innerFunc() a closure.

                -   **NOTE**: If an inner function does not make use of
                    any returned external variables, then it is merely a
                    **Nested Function**.

        -   **NOTE**: When working with closures, you may either call
            the inner function right away (via \"yourFunc()()\"), or you
            can store the result of the outer function to be used by the
            inner function at a later time (similar to how bind()
            works), e.g.:\
            function outer(a) {\
            return function inner(b) {\
            return a + b;\
            }\
            }\
            var storeOuter = outer(5);\
            storeOuter(10) // returns 15

    -   **Usage**

        -   Closures are useful for creating **Private Variables**,
            which are variables that cannot be modified externally.

            -   Consider the following example:\
                function counter() {\
                var count = 0;\
                return function() {\
                return ++count; //
                [**Pre-Increment**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Increment_())\
                }\
                }

                -   If you were to call counter()() repeatedly, you
                    would return \"1\" each time, without the count ever
                    going up. This is because there is no \"container\"
                    to keep track of the incremented count variable that
                    exists only within the counter() function. However,
                    if you were to save counter() to a new variable in
                    the global scope:\
                    var counter1 = counter();\
                    ...then there is now a persistent variable (i.e.,
                    counter1) to \"house\" the increments to \"count\"
                    within counter1\'s own counter() function.

                -   The primary benefit of using closures in this way is
                    that it is no longer possible for the value of count
                    within counter1 to be externally modified by any
                    other function. Thus, you are free to repeat this
                    process with a new variable named \"counter2\",
                    which, in turn, will have its own internal count
                    variable insulated from any external modification.
                    Neither will have their count value increase except
                    through their own internal operations.

            -   Consider the following for another more \"practical\"
                example:\
                function classroom() {\
                var instructors = \[\'Adam\', \'Ben\'\];\
                return {\
                getInstructors: function() {\
                return instructors;\
                },\
                addInstructors: function(instructor) {\
                instructors.push(instructor);\
                return instructors;\
                }\
                }\
                }

                -   Essentially, the classroom() function operates as a
                    model template upon which new \"course\" objects can
                    be created, and in which all courses will have Adam
                    and Ben as instructors. You can create two courses
                    as variables (e.g., \"course1\" and \"course2\"),
                    and you can add an instructor to course 1:
                    course1.addInstructor(\'Charlie\'); // \[\'Adam\',
                    \'Ben\', \'Charlie\'\]\
                    ...but this addition will not be reflected in
                    course2:\
                    course2.getInstructors(); // \[\'Adam\', \'Ben\'\]

```{=html}
<!-- -->
```
