
> var comments = {
>
> data: \[
>
> \'Good\',
>
> \'Bad\',
>
> \'Okay\'
>
> \],
>
> print: function() {
>
> this.data.forEach(function(elem) {
>
> console.log(elem)
>
> });
>
> }
>
> };

-   The \"this\" keyword essentially allows you to use the values
    contained in comments.data inside of comments.print without the need
    for any additional argument. Thus, by writing \"this\" inside of a
    method, it refers to the object that the method is defined in.

```{=html}
<!-- -->
```
-   [**DOM (\"Document Object Model\")
    Manipulation**](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Manipulating_documents)

    -   **Background**

        -   The DOM is the interface between JS and HTML/CSS (for making
            content interactive). When you load an HTML page, the
            browser turns every HTML tag into a JS object that we can
            select and manipulate, and all of these are stored inside of
            a \"document\" object. To view the HTML elements converted
            into JS objects (i.e., the DOM), type the following into the
            console: **console.dir(document);**

        -   **NOTE**: When performing DOM manipulation, be sure that the
            JS files are loaded after all HTML is written (or else you
            will be trying to manipulate HTML that does not yet exist to
            the JS files, and it will not work.)

    -   **Important DOM Selector Methods** (the following five methods
        have been added into the \"document\" object):

        -   **document.getElementById()**

            -   Takes in an ID name and returns the one element that
                matches that name (because an ID can only be associated
                with one element in a page). For example, if you have an
                HTML element with the ID of \"highlight\", you can
                return that element by stating:\
                var tag = document.getElementById(\'highlight\');

                -   You can then use console.dir(tag) to see all of the
                    properties contained in the \"highlight\" object.

        -   **document.getElementsByClassName()**

            -   Operates in the same way as getElementById(), but
                applies to all elements sharing the same class. If you
                want to return a list of all elements with the class
                \"bolded\", you would state:\
                var tags = document.getElementsByClassName(\'bolded\');

                -   You can then simply state \"tags\" to see all of the
                    properties for all \"bolded\" objects, and you can
                    use console.log(tags\[0\]) to access the first index
                    of the **Node List** (not technically an array, but
                    is array-like) containing the \"bolded\" objects.

                    -   The node list is \"array-like\" in the sense
                        that you can access individual indices, but you
                        **[CANNOT]{.ul}** apply forEach() to it (because
                        there is no forEach() function defined for these
                        node lists; they are defined for arrays).

                        -   **BUT NOTE**: You can use the
                            \"[**Array.from()**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from)\"
                            method to convert node lists and HTML
                            collections into arrays.

                -   **NOTE**: You can also access a specific index
                    (e.g., the first index) more directly by simply
                    stating:\
                    var tags =
                    document.getElementsByClassName(\'bolded\')\[0\];

        -   **document.getElementsByTagName()**

            -   Operates in the same way as the two above, but it refers
                to a general HTML tag (such as \<li\>, \<ul\>, \<h1\>,
                \<head\>, \<body\>) rather than a specific class/ID. If
                you want to return a list of all elements with the
                \<li\> tag, state:\
                var tags = document.getElementsByTagName(\'li\');

        -   **document.querySelector()**

            -   Operates in the same fashion as the methods above, but
                does so by using a **CSS**-Style Selector (i.e., \"\#\"
                for ID, and \".\" for class). **BUT**, it differs
                significantly by only returning the **[FIRST
                MATCH]{.ul}**. For example, to if you want to return an
                HTML element with the ID of \"highlight\", you would
                state:\
                var tag = document.querySelector(\'\#highlight\');

                -   If \"highlight\" were a class, you would use a
                    period instead of an octothorp, but note that you
                    will only return the first match.

                -   This works for any syntax that would be valid in
                    CSS, e.g.:\
                    var tags = document.querySelector(\'li a.special\');

                -   query.Selector can also take in basic **HTML** tag
                    names like \<h1\>:\
                    var tag = document.querySelector(\'h2\');\
                    ...but, again, only for the first match.

                -   If you want to select a **Specific Type** of element
                    (e.g., a numerical input), you would use brackets
                    and state:\
                    var tag =
                    document.querySelector(\'input\[type=\"number\"\]\');

        -   **document.querySelectorAll()**

            -   Operates in the same manner as query.Selector, except it
                returns a node list of **ALL** elements (as objects)
                that match a given CSS-style selector.

    -   **Manipulating Style**

        -   A DOM object\'s **Style** property is one way to manipulate
            an HTML element\'s style, e.g.:\
            // select your object:\
            var tag = document.getElementById(\'highlight\');\
            // manipulate your object:\
            tag.style.color = \'blue\';\
            tag.style.border = \'10px solid red\';\
            tag.style.fontSize = \'70px\';\
            tag.style.background = \'yellow\';\
            tag.style.marginTop = \'200px\';

            -   **NOTE**: This is not actually the best way to
                manipulate an object, as it is very repetitious (not
                \"dry\" code), but more significant is the
                \"**Separation of Concerns**\" (the principle that HTML,
                CSS, and JS should each be responsible for their own
                separate domain, and crossover between the three should
                be avoided -- HTML should be pure structure, CSS should
                be pure presentation, and JS should be pure behavior).

            -   Rather than changing multiple style properties in JS,
                you should turn them on/off by using the CSS file. For
                example, you can define a CSS class, select an element
                in JS, and add the class to its **classList**:\
                // define a class in CSS:\
                .toggleWarning {\
                color: red;\
                border: 10px solid red;\
                }\
                // add the .toggleWarning class to a select object in
                JS:\
                var tag = document.getElementsByTagName(\'h1\');\
                tag.classList.add(\'toggleWarning\');

                -   If you so choose, you can later remove the class by
                    stating:\
                    tag.classList.remove(\'toggleWarning\');

                -   A similar useful method is **toggle**, which
                    operates by (1) adding the specified class if it is
                    not present in the class list, and (2) removing the
                    specified class if it is present in the class list:\
                    tag.classList.toggle(\'toggleWarning\');

                -   **NOTE**: A class list is technically **NOT AN
                    ARRAY**. This is why you must use add() and remove()
                    rather than push() and pop().

    -   **Manipulating Text and Content**

        -   The **textContent** property retrieves the text inside of an
            HTML element. \"Text\" is defined as anything between the
            HTML tags but not including any tags contained within (it
            extracts only **Plain Text**). The method can be used to
            alter the text by the following syntax:\
            tag.textContent = \'blah blah blah\';

            -   **NOTE**: Because this method only works in plain text,
                no modifiers like \<strong\> or \<em\> will be
                preserved.

        -   The **innerHTML** property is used to manipulate both **HTML
            Text and Inner Element**s.

        -   **IMPORTANT SYNTAX NOTE**: When manipulating text and
            content (or style), it is not necessary to set a variable
            first. Instead, you can simply add the textContent or
            innerHTML property after the selector method, e.g.:\
            document.querySelector(\'h1\').textContent = \'Heading 1\';

    -   **Manipulating Attributes**

        -   The attributes of an HTML element (e.g., href, src, or
            anything else following the name=\"text\" syntax, such as
            id, class, etc.) can be modified by using **getAttribute()**
            and **setAttribute()** to read and write attributes. For
            example, to return the URL for the following:\
            \<a href=\"https://www.google.com/\"\>Search\</a\>\
            ...you would state:\
            var link = document.querySelector(\'a\');\
            link.getAttribute(\'href\');\
            ...and to modify the link, you would state the attribute as
            the first argument in the method, and the new URL as the
            second argument:\
            link.setAttribute(\'href\', \'https://www.yahoo.com/\');

        -   **NOTE**: When manipulating **Images**, the \"src\"
            attribute may be ignored if the \"srcset\" attribute has
            also been set. In such cases, srcset must be modified.

    -   **DOM Events**

        -   The **[MDN Event
            Reference](https://developer.mozilla.org/en-US/docs/Web/Events)**
            contains all of the different events that are recognized by
            the DOM application programming interface (**API**). Some
            common events to be most familiar with are \"click\",
            \"change\", \"mouseover\", and \"mouseout\".

        -   Events trigger the running of code when a certain action has
            been taken, as opposed to automatically executing when the
            page loads (e.g., clicking a button, hovering over a link,
            pressing a key, etc.). The event must be selected and then
            attached to a specific element by means of an **Event
            Listener** (e.g., \"Listen for a click on this \<button\>.\"
            To add a listener, use the **addEventListener** method
            through this syntax:\
            element.addEventListener(\'type\', functionToCall);

            -   For example, to have a message print to console when the
                first button in a document is clicked, you would state:\
                var button = document.querySelector(\'button\'); //
                select element\
                button.addEventListener(\'click\', function() { // add
                event listener\
                console.log(\'The button has been clicked.\'); // run
                code\
                });

                -   It is not necessary to use an anonymous function.
                    The same code could be executed as follows:\
                    var button = document.querySelector(\'button\');\
                    button.addEventListener(\'click\', printConsole);\
                    function printConsole() {\
                    console.log(\'The button has been clicked.\');\
                    }\
                    However, unless there is a need to use a named
                    function again somewhere else outside of the click
                    listener, it is better to simply use the anonymous
                    function.

            -   **NOTE**: You can have more than one listener on a given
                element. They will execute in the order that they were
                added.

            -   **THIS NOTE**: Inside of a listener, the \"this\"
                keyword refers to the item that was clicked on (or
                hovered upon, or which a keypress referred to, etc.). So
                whatever element is attached to the addEventListener is
                the event to which \"this\" refers. This is useful in
                situations where you want a large number of similar but
                individual (sibling) elements to run specific code only
                upon itself when activated. For example, if you have a
                \<ul\> with a dozen \<li\> tags within, and you want
                each individual \<li\> to change its color when clicked,
                you can use a for loop and \"this\" as follows:\
                var lis = document.querySelectorAll(\'li\');\
                for (var i = 0; i \< lis.length; i++) {\
                lis\[i\].addEventListener(\'click\', function() {\
                this.style.color = \'pink\';\
                });\
                }

```{=html}
<!-- -->
```
-   **JavaScript (Intermediate)**

    -   [**This**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)

        -   \"This\" is a reserved keyword, which means it cannot be set
            as the value of any variable. The value of \"this\" is
            determined upon execution (i.e., \"**Execution Context**\").

        -   There are **Four Rules** governing how the value of \"this\"
            is determined:

            -   **Global Context**

                -   This rule applies when you see \"this\" applied
                    outside of a declared object. When you see the word
                    \"this\" in the global context, its value refers to
                    the **Global Object**, which is the **Window** in
                    the browser environment. Thus, if you were to
                    console.log(this), you would return \"window\".

                -   In essence, every variable that you declare in the
                    global context is in fact attached to the window
                    object, which is what allows \"this\" to work in the
                    global context without an object being declared. For
                    example, you can create the following variable:\
                    var person = \'Ellie\';\
                    ...which can then be accessed as:\
                    window.person\
                    ...and which is also synonymous with:\
                    this.person

                -   **NOTE:** Even when you use \"this\" inside of a
                    **Function**, its value is still the global object
                    if no other object is declared within the function,
                    e.g.:\
                    function variablesInThis() {\
                    this.person = \'Ellie\'; // still the same as var
                    person = \'Ellie\'\
                    }

                    -   **HOWEVER**: The above process is considered bad
                        practice for setting global variables, as global
                        variables should be declared at the top of your
                        code (with the value either declared immediately
                        or at a later time within a function). If you
                        want to prevent the accidental creation of
                        global variables in a function, you can state
                        [**\"use
                        strict\"**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)
                        (in quotes) at the top of your JS file, which
                        will return a **TypeError** indicating that
                        \"this\" is **Undefined** upon execution.

            -   **Object/Implicit**

                -   When \"this\" is found inside of a **Declared
                    Object**, its value will always be the **Closest
                    Parent Object**. For example, given the following
                    object...\
                    var person = {\
                    firstName: \'Ellie\',\
                    sayHi: function() {\
                    return \'Hi \' + this.firstName;\
                    }\
                    }\
                    ...executing \"person.sayHi()\" will return \"Hi
                    Ellie\" because \"this.firstName\" is equivalent to
                    stating \"person.firstName\" due to \"person\" being
                    the closest parent object to \"this\".

                -   **NOTE**: Caution must be exercised with **Nested
                    Objects**, as a reference to properties beyond the
                    scope of the nested object may result in undefined
                    values being returned when using \"this\" within the
                    nested object.

            -   **Explicit**

                -   In order to avoid problems associated with nested
                    objects, you can set the context of \"this\" by
                    using the **Call**, **Apply**, or **Bind** methods
                    (which can only be used by **Functions**, and not by
                    any other data type).

                    -   [**Call**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call)
                        uses the following syntax:

> function.call(thisArg, arg1, arg2, ...);

-   The first argument is whatever object you want the value of \"this\"
    to be. The subsequent arguments are for any optional parameters to
    be used in the function in which you are changing the context of
    \"this\".

    -   **NOTE**: When the call method is used on a function, that
        function is immediately invoked.

-   Consider the following example:\
    var firstPerson = {\
    firstName: \'John\',\
    lastName: \'Doe\',\
    fullName: function() {\
    return this.firstName + \' \' + this.lastName;\
    }\
    }\
    var secondPerson = {\
    firstName: \'Mary\',\
    lastName: \'Jane\'\
    }

    -   If you want to return the full name of Mary Jane, there is no
        need to duplicate the fullName function from the first person
        (John Doe). Rather, you need merely state...\
        firstPerson.fullName.call(secondPerson);\
        ...because using the \"secondPerson\" argument in call will
        result in the \"this\" keyword from the \"firstPerson\" object
        actually being applied to the \"secondPerson\" object instead
        (i.e., Mary Jane).

```{=html}
<!-- -->
```
-   [**Apply**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply)
    uses the following syntax:\
    function.apply(thisArg, \[argsArray\]);

    -   Apply is almost identical to call except it only takes two
        arguments. The first argument operates the same as call, while
        the second is an **Array** (or [**ARRAY-LIKE
        OBJECT**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#Working_with_array-like_objects))
        that will be passed to the function in which you are changing
        the value of \"this\".

        -   **NOTE**: When the apply method is used on a function, that
            function is immediately invoked.

    -   Consider the following example:\
        var firstP = {\
        name: \'John\',\
        addNumbers: function(a, b, c, d) {\
        return this.name + \' calculated \' + (a+b+c+d);\
        }\
        }\
        var secondP = {\
        name: \'Jane\'\
        }

        -   Stating \"firstP.addNumbers(1, 2, 3, 4)\" will return \"John
            calculated 10\". You can do the same for Jane by either
            using call:\
            firstP.addNumbers.call(secondP, 1, 2, 3, 4);\
            ...or by using apply:\
            firstP.addNumbers.apply(second, \[1, 2, 3, 4\]);

-   [**Bind**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind)
    uses the following syntax:\
    function.bind(thisArg, arg1, arg2, ...);

    -   Bind is almost identical to call except that instead of invoking
        the function immediately, bind returns a function definition.
        This allows you to save a function with different values of
        \"this\" and invoke them at a later time (known as **Partial
        Application**), as you may not initially know all of the
        arguments that will be passed to a function.

        -   In the example for apply above, you might know that you
            always want to add 1 and 2 for the second person, but not
            know what other numbers will need to be calculated. You
            could first state:\
            var sPCalc = firstP.addNumbers.bind(secondP, 1, 2);\
            ...and then include more numbers on execution:\
            sPCalc(3, 4) // returns \"Jane calculated 10\"

    -   Bind is also important when working with asynchronous code
        (e.g.,
        [**setTimeout**](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout)),
        as it allows you to set the context of \"this\" for a function
        to be called at a later point in time. Consider the following:\
        var person = {\
        name: \'John\',\
        sayHi: function() {\
        setTimeout(function() {\
        console.log(\'Hi \' + this.name)\
        }, 1000);\
        }\
        }

        -   Although you may expect \"Hi John\" to be displayed in the
            console after 1 second, this does not occur. This is because
            setTimeout() does not run console.log() concurrently with
            the creation of the \"person\" variable; rather, it only
            executes after the timer expires. As a result, setTimeout()
            is run in the **Global Context** as a **Window Object**.
            Thus, \"this\" actually refers to window rather than
            \"person\", because window is the value of \"this\" upon
            execution. You can fix this by stating:\
            var person = {\
            name: \'John\',\
            sayHi: function() {\
            setTimeout(function() {\
            console.log(\'Hi \' + this.name)\
            }**[.bind(this)]{.ul}**, 1000);\
            }\
            }

            -   This may appear to be confusing, as you are using
                \"this\" to change the value of \"this\". However, at
                the time \"person\" is **[CREATED]{.ul}**, \"this\" does
                in fact refer to \"person\" because \"person\" (not
                window.setTimeout) is the nearest parent object to
                \"bind(this)\". Here, \"bind(this)\" is equivalent to
                \"bind(person)\".

```{=html}
<!-- -->
```
-   [**New**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new)

    -   The new operator is used together with a **Constructor
        Function** to create a new object. Inside the constructor
        function definition, the keyword \"this\" refers to the object
        that is created. When the new operator is used, an implicit
        return \"this\" is added to the constructor function.

        -   **NOTE**: A popular convention in JS is to capitalize the
            names of
            [**Constructors**](https://developer.mozilla.org/en-US/docs/Glossary/Constructor),
            which basically operate as model templates upon which new
            objects will be based.

    -   For example, you can create a constructor function for a
        person\'s name:\
        function Person(first, last) {\
        this.firstName = first;\
        this.lastName = last;\
        }

        -   In this context, \"this\" would apply to window in the
            global context (as there is no object has been declared).
            However, when paired with the new operator, \"this\" will
            instead refer to the newly created object that has been
            stored as a variable. For example...\
            var john = new Person(\'John\', \'Doe\');\
            ...results in \"this.firstName\" being equal to
            \"john.firstName\" (as \"john\" is the new object) and
            \"this.lastName\" being equal to \"john.lastName\".

```{=html}
<!-- -->
```
