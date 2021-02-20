-   [**JavaScript**](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
    **(Basic)**

    -   **Writing a JavaScript File**

        -   JavaScript must be saved to a file ending in the \".js\"
            extension.

        -   To add the JS file to your website, you must use a
            \<script\> tag in your HTML file:\
            \<script src=\"filename.js\"\>\</script\>

        -   **NOTE**: Use double slashes \"//\" to make unexecuted
            **Comments** within your JS file (similar to comments that
            can be included in HTML and CSS).

    -   **The JavaScript Console**

        -   Accessible on the \"Console\" tab in \"Developer Tools\" in
            Chrome (accessed by F12).

        -   Just as with using the Developer Tools for testing and
            understanding how your HTML/CSS work (rather than actually
            writing your HTML/CSS), the JS console serves the same
            function.

        -   **TIP**: Pressing the \"up\" arrow in the console will bring
            back previously lines of code, so you do not have to retype
            it.

    -   **Primitives**

        -   There are 5 low-level, basic types of data used in JS:

            -   **Numbers**

                -   Whole, fractional, or negative numbers are all
                    treated the same way.

                -   In the console, the browser can perform mathematical
                    processes in the same manner as a calculator by
                    simply typing, e.g., \"4 + 10\" and pressing
                    \"Enter\" to have the result returned to you.

                    -   One function known as **Modulo** (a.k.a., the
                        Remainder Operator) uses the \"%\" placed
                        between two numbers (like a \"+\" for addition),
                        then it will divide the second number into the
                        first number as many times as it can as a whole
                        number, and then gives you the remainder as a
                        result, e.g.:\
                        10 % 3 = 1\
                        20 % 5 = 0\
                        15 % 11 = 4

            -   **Strings**

                -   All of the text within one pair of **Quotation
                    Marks** constitutes one string. This is also true of
                    numbers that appear within quotes.

                    -   You can use either double quotes (\"), single
                        quotes (\'), or backticks (\`), but the pair
                        must match or an error will result.

                        -   **IMPORTANT**: If you want to have a string
                            include **Newlines** (i.e., the character
                            that causes a line break to occur when you
                            press Enter), then you must use the
                            **Backtick**. Other types of strings will
                            remain on one line unless you use special
                            escape characters (described below).

                        -   Backticks can also be used in conjunction
                            with \${} to **Embed Values** within a
                            string, e.g.:\
                            \`Half of 100 is \${100/2}.\`\
                            ...translates to:\
                            \"Half of 100 is 50.\"

                    -   **BUT NOTE**: You can have a single quote within
                        a pair of double quotes (e.g., if you are typing
                        a word has an apostrophe), and it will still be
                        valid.

                -   **Concatenation**:

                    -   Strings can be added together formulaically to
                        create a single string, e.g.:\
                        \'Charlie \' + \'Brown\' = \'Charlie Brown\'

                -   **Escape Characters**:

                    -   Escape characters all start with a backslash
                        (\"\\\"), and they are used to \"escape\" out of
                        the string to write special characters that
                        would not otherwise be valid within the string.
                        For example, if you want the string to say,
                        \"She said \"Goodbye!\"\" without using single
                        quotes around \"Goodbye!\", then say:\
                        \'She said \\\"Goodbye!\\\"\'

                    -   The following link includes a [**List of Special
                        Escape
                        Notations**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String).

                -   **Length Property**:

                    -   Every string has a \"length property,\" which
                        refers to the number of characters (including
                        spaces, numbers, etc.) within that string. For
                        example, by typing the following, the console
                        will tell you that the string \"hello\" is 5
                        characters long:\
                        \'hello\'.length;

                -   You can also access individual characters by using
                    **Brackets**, and placing a number (beginning with
                    zero) within the brackets that corresponds to the
                    position in the string in which the character
                    appears (i.e., its \"**Index**\"). For example, JS
                    will access the first letter in the string \"hello\"
                    and return \"h\" if you say:\
                    \'hello\'\[0\];

                    -   **TIP**: Rather than manually counting each
                        character, you can determine the index number of
                        the very last character by using \".length\" and
                        subtracting by 1.

                -   **NOTE**: To determine if something is a number or a
                    string, you can use: console.log(typeof var);

            -   **Booleans**

                -   Only two options: true or false

                -   **TIP:** To invert the value of a variable from true
                    to false or vice versa, simply use the NOT (\"!\")
                    operator, e.g.:\
                    var x = true; // x will return true\
                    x = !x; // x will return false\
                    x = !x; // x will return true

            -   **Null** & **Undefined**

                -   These are actually values rather than a true
                    category (no multiple types of \"null\" or
                    \"undefined\").

                -   Undefined variables are those which are declared but
                    not initialized, whereas null variables are
                    \"explicitly nothing.\"

                    -   For example, if you run \"var age;\" without a
                        value, then JavaScript is simply told to make
                        some space for something called \"age\" but
                        without storing anything there. If you then ask
                        the console to give you a return on \"age\", it
                        will come back \"undefined.\" If you ask the
                        console to return something that doesn\'t exist
                        at all, like \"color,\" then it will return an
                        error.

                    -   By contrast, if you are making a game and making
                        a string for the name of the current player as
                        \"var currentPlayer = \'charlie\';\" and that
                        player dies (game over), you would set
                        \"currentPlayer = null;\" to make it clear that
                        there is no longer any \"current player.\"

    -   **Variables**

        -   A variable is simply a named container with data stored
            within. Variables are structured according to the following
            syntax:\
            var yourVariableName = yourValue;\
            var name = \'Rusty\';\
            var secretNumber = 73;\
            var isAdorable = true;

            -   **NOTE**: The naming convention used in JS relies on a
                system of capitalization known as **camelCase**, in
                which the first word of the name starts with a
                lower-case letter, and subsequent words begin with an
                upper-case letter.

        -   The name \"variable\" means that the data stored within that
            container can vary. For instance, you can begin by setting
            the following in the console:\
            var name = \'Rusty\';\
            However, if you later decide that you want to change the
            name, then you can simply state \"name = \'Tater\';\" which
            will result in the console returning the value \"Tater\"
            when you simply type \"name\" into the console.

        -   Math can also be performed with the name of a variable that
            has a number for its value. For example, if you set a
            variable with the name of \"num\" and set its value to 73,
            you can type \"num + 7\" to receive the result of 80.

    -   **Useful Built-In Methods**

        -   **Alert**

            -   Creates a pop-up message for the user when running the
                following:\
                alert(\'hello world\');

        -   **Console.log**

            -   \"Prints\" data to the JavaScript console (so only those
                viewing the console can see the text/data):\
                console.log(\'hello world\');

        -   **Prompt**

            -   Allows the browser to get input from a user via a pop-up
                message with a text field in which the user can input
                information:\
                prompt(\'What is your name?\');

            -   The information obtained through Prompt can also be
                stored as a variable for later use. For example, the
                browser may run the following operation:\
                var userName = prompt(\'What is your name?\');\
                Then after the user inputs his name, that name can be
                recalled by running \"username\".

            -   **NOTE**: When a number is entered into a prompt by the
                user, it is stored as a string (e.g., 7 becomes \"7\").
                To recall the stored string as a number, use the
                following syntax: Number(storedString);

                -   If the prompt intends that the answer only be an
                    answer and not contain any text, it would be most
                    efficient to have the starting variable be something
                    to the effect of:\
                    var numberAnswer = Number(prompt(\'Enter a
                    number.\'));\
                    or\
                    var answer = prompt(\'Enter a number.\');\
                    var numberAnswer = Number(answer);

                -   **ALSO NOTE**: Alternatively, you may use the
                    **Unary Plus** operator (\"+\") to convert a string
                    to a number: +storedString;

                -   **SEE ALSO**:
                    [**parseFloat()**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat)

        -   **Clear**

            -   Run \"clear()\" to clear the console.

    -   **Boolean Logic**

        -   Boolean logic relies upon **Comparison Operators** in
            determining whether a particular result should be labeled as
            \"true\" or \"false\". For example, assuming the value of
            \"x = 5\", then the following operators would produce the
            following results:

  **Operator**   **Name**                   **Example**   **Result**
  -------------- -------------------------- ------------- ------------
  \>             Greater than               x \> 10       False
  \>=            Greater than or equal to   x \>= 5       True
  \<             Less than                  x \< -50      False
  \<=            Less than or equal to      x \<=100      True
  ==             Equal to                   x == \'5\'    True
  !=             Not equal to               x != \'b\'    True
  ===            Equal value and type       x === \'5\'   False
  !==            Not equal value or type    x !== \'5\'   True

-   **Double Equals** performs **Type Coercion**, which takes the two
    numbers, strings, or variables and tries to turn them into a similar
    type to compare them. **Triple Equals**, by contrast, does not
    perform type coercion, so a pure number 5 will not be treated the
    same way as a string containing the number \"5\".

    -   As a general rule, triple equals should always be preferred, as
        it is more specific than double equals. For example, if you were
        to run \"var y = null;\" and then \"y == undefined\", the
        console would return a value of \"true\" because null and
        undefined are similar, even though the two are not technically
        true equivalents.

    -   Additional quirks in JS demonstrating the anomalies that arise
        when using double equals:\
        true == \"1\" // true\
        0 == false // true\
        null == undefined // true\
        NaN == NaN // false (\"NaN\" stands for \"not a number\")

```{=html}
<!-- -->
```
-   **Logical Operators**

    -   Logical operators are used to \"chain together\" expressions of
        Boolean logic. For example, where \"x = 5\", and \"y = 9\", you
        would receive the following results:

  **Operator**   **Name**   **Example**           **Result**
  -------------- ---------- --------------------- ------------
  &&             AND        x \< 10 && x !==5     False
  \|\|           OR         y \> 9 \|\| x === 5   True
  !              NOT        !(x === y)            True

-   **AND** requires both sides of the equation to be true to return a
    result of \"true.\" On the other hand, **OR** only requires one or
    the other to be true to return a result of \"true.\"

-   **NOT** negates the truth (or falsity) of whatever is contained in
    its parentheses. In the example above, the parenthetical statement
    says that \"5 = 9\", which is false. Adding the NOT operator is
    tantamount to saying, \"It is NOT TRUE that \'5 = 9\' is true,\"
    which is ultimately a true statement, thereby returning a result of
    \"true.\"

```{=html}
<!-- -->
```
-   The following values are treated as being \"**Falsy**\" in JS
    (whereas everything else is considered \"**Truthy**\"):\
    false (NOTE: This false is not within a string. Any text within a
    string is \"truthy.\")\
    0\
    \"\"\
    null\
    undefined\
    NaN

```{=html}
<!-- -->
```
-   **Conditionals**

    -   Conditionals are the means by which you add \"decisions\" to
        your code. For example, when you log in to a website, there is
        code that checks the password you type in with the password
        stored on the site\'s server (and you are logged in if they
        match, and given an error message if they do not match).

    -   Three Key Conditionals

        -   **If**

            -   \"If you are younger than 18, you cannot enter the
                venue\":\
                if (age \< 18) {\
                console.log(\'Sorry, you are not old enough to enter the
                venue.\');\
                }

        -   **Else If** always follows an \"if\" statement as a
            secondary condition, as it will only run if the preceding
            \"if\" statement is false.

            -   \"If you are between 18 and 21, you can enter but cannot
                drink\":\
                else if (age \< 21) {\
                console.log(\'You can enter, but cannot drink.\');\
                }

        -   **Else** will only run as a last-ditch effort when all
            preceding \"if\" and any subsequent \"else if\" statements
            are false.

            -   \"Otherwise, you can enter and drink\":\
                else {\
                console.log(\'Come on in. You can drink.\');\
                }

    ```{=html}
    <!-- -->
    ```
    -   **Ternary Operator**

        -   The ternary operator is a shorthand method of creating a
            simple \"if/else\" conditional by the following syntax:\
            condition ? ifStatement : elseStatement

            -   For example, to perform an age check, you could state:\
                age \>= 18 ? console.log(\'You can enter.\') :
                console.log(\'You must leave.\');

-   **Loops**

    -   [**While
        Loops**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while)
        repeat code while a condition is true. They are very similar to
        if statements, except they repeat a given code block instead of
        just running it once:\
        while (someCondition) {\
        // run some code\
        }

        -   For example, to have the console print numbers 1-5, you
            would say:\
            var count = 1;\
            while (count \< 6) {\
            console.log(count);\
            count++;\
            }

            -   **NOTE**: Using \"++\" will add a value of 1, but you
                can add more value, for example, 4, by using \"+= 4\".
                For subtracting, just use a \"-\" sign instead of a
                \"+\" sign.

        -   If you want the user to enter a certain phrase into a
            prompt, but do not need exact specificity (only that the
            user provide the phrase somewhere in the response to the
            prompt), then you can use the **Index Of** method. This
            method returns the first index (starting at 0) at which a
            given element can be found in the array (in this case, the
            user\'s response), or -1 if it is not present.

            -   For example, if a prompt is set to loop until the user
                types \"yes\" (variable named \"answer\"), and the user
                instead types \"hell yes\", then running
                answer.indexOf(\'yes\') will return a result of 5,
                because the phrase \"yes\" begins at index 5 of the
                user\'s answer of \"hell yes\". If the user typed \"yes
                sir\", then the result would be 0, because the phrase
                \"yes\" begins at index 0. If the user fails to include
                the phrase \"yes\" anywhere in his response, then a
                result of -1 will be returned, due to the fact that the
                phrase \"yes\" appears nowhere in the user\'s answer.
                Therefore, to make a prompt loop until the user types
                the word \"yes\" (and thereby returning a positive index
                to terminate the loop), the following expression may be
                used:\
                var answer = prompt(\'Are we there yet?\');

> while (answer.indexOf(\'yes\') === -1) {
>
> var answer = prompt(\'Are we there yet?\');
>
> }
>
> alert(\'Yay! We made it!\');

-   **SEE ALSO**: [**Do...While
    Loops**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/do...while)

```{=html}
<!-- -->
```
-   **Infinite Loops** occur when the terminating condition in a loop is
    never false. For example, the code below will print 0 forever
    because \"count\" is never incremented:\
    var count = 0;\
    while (count \< 10) {\
    console.log(count);\
    }

-   [**For
    Loops**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
    operate similarly to while loops, but with a different syntax. Most
    significantly, the variable that is set to initialize the for loop
    is typically only meant to exist within the confines of that
    particular for loop:

    -   **Syntax**:\
        for (init; condition; step) {\
        // run some code\
        }

        -   \"**Init**\" (for \"initialize\") declares a variable and
            sets it to some initial value at the start of the loop,
            \"**Condition**\" states when this loop should keep running
            (for as long as the condition returns \"true\"), and
            \"**Step**\" states what should be done at the end of every
            iteration.

    -   Example of how to print numbers 1-5 with a for loop:\
        for (var i = 1; i \< 6; i++) {\
        console.log(i);\
        }

        -   This statement \"initializes\" by setting \"i\" as 1, and
            provides that \"i\" will be printed to the console and then
            increased by an increment of 1 for as long as \"i\" is less
            than 6.

    -   Example of how to print each character in the world \"hello\":\
        var str = \'hello\';\
        for (var i = 0; i \< str.length; i++) {\
        console.log(str\[i\]);\
        }

        -   This statement initializes by setting \"i\" as 0, and
            provides that the corresponding index of \"hello\" (as
            defined by the number at which \"i\" is currently set) will
            be printed to the console and then increased by an increment
            of 1 for as long as the numerical value of \"i\" is less
            than the numerical length of the \"str\" variable (in this
            case, the word \"hello\").

    -   **SEE ALSO**: [**For...In
        Loops**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in)

```{=html}
<!-- -->
```
-   [**Functions**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)

    -   Functions allow you to wrap bits of code up (with a suggested
        limit of 20 lines) into reusable packages. They function by
        first \"declaring\" a function, e.g.:\
        function doSomething() {\
        console.log(\"HELLO WORLD\");\
        }\
        ...and then \"calling\" the function as many times you want,
        e.g.:\
        doSomething();\
        doSomething();\
        doSomething();\
        doSomething();

        -   **NOTE**: It is necessary to include the empty parentheses
            after \"doSomething\" to actually **Execute** its code;
            otherwise, the console will simply spit the code back out
            for you to see in its entirety (i.e., give you the value of
            \"doSomething\").

        -   Another Syntax: As an alternative to a **Function
            Declaration**, you can also use a **Function Expression**:\
            var doSomething = function() {\
            console.log(\'HELLO WORLD\');\
            }

            -   **BUT NOTE**: If the value of doSomething is modified,
                the function is lost.

    -   [**Arguments**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments)
        are how we can write functions that take inputs. Rather than
        using empty parentheses, you insert the name of an argument
        within the parentheses following the function name.

        -   For example, in order to create a function that can
            dynamically return the square of any numerical input, you
            would state:\
            function square(num) {\
            console.log(num \* num);\
            }\
            ...and then \"**Call**\" square with whatever value you
            \"pass in\" (i.e., input), e.g.:\
            square(10); // prints 100\
            square(4); // prints 16\
            square(3); // prints 9

        -   Functions can have as many arguments as needed and can
            generally be given any name. Simply separate the arguments
            with commas. For example, to calculate the area of a
            rectangle, you must multiply length and width:\
            function area(length, width) {\
            console.log(length \* width);\
            }\
            ...and then call the function, e.g.:\
            area(2, 4) // prints 8

            -   **NOTE**: If you want a function to have [**Default
                Parameters**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters)
                in the event the user does not specify a value, use the
                following syntax:\
                function area(length = 200, width = 400) {\
                console.log(length \* width);\
                }

        -   Other examples of useful functions include (1) being able to
            add or subtract from a player\'s score during a game (by
            inserting a positive or negative number as an argument);
            or (2) checking a user\'s login credentials by making their
            e-mail and password into two arguments, and then running an
            If statement to determine if they match correctly, or else
            return an error.

        -   **NOTE**: All functions have an [**Arguments
            Object**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments),
            which is an **Array-Like Object** that can be used to access
            the arguments in a manner similar to accessing an array
            item. For example, if you have the following function...\
            function logNumbers(a, b, c) {\
            console.log(arguments\[0\]);\
            console.log(arguments\[1\]);\
            console.log(arguments\[2\]);\
            }\
            ...the console will print the following upon executing
            logNumbers(2, 4, 6):\
            2\
            4\
            6

            -   **ALSO NOTE**: The arguments object can be useful for
                constructing functions in which a varied number of
                arguments may be passed. For example, if you want to
                create a function that will return the sum of any set of
                numbers that have been passed as arguments, you could
                say:\
                function addNumbers() {

> var sum = 0;

for (var i = 0; i \< arguments.length; i++) {

sum += arguments\[i\];

> }
>
> return sum;
>
> }

-   **The Return Keyword**

    -   Every function returns something, but if you don\'t tell it what
        to return, it just returns \"undefined.\" In previous examples,
        functions have been used to print to the console, which is
        always an undefined return and cannot be used for anything. For
        example, in the \"square()\" function above, if you ran
        square(4), the console would print 16, but it would also return
        \"undefined\". Additionally, if you ran...\
        \'4 squared is: \' + square(4);\
        ...it would return: \'4 squared is: undefined\' rather than \'4
        squared is: 16\'. That is because the return keyword was not
        used in the original function. Instead, you must state:\
        function square(num) {\
        return num \* num;\
        }

        -   The use of the return keyword in this example also provides
            the additional benefit of allowing the returned result to be
            stored as a variable. For example, if you were to next run
            var result = square(104), then you would receive the
            returned value of 10816 after calling \"result\".

    -   For another example of how the return keyword allows you to
        capture a returned value in a variable, consider this function
        which capitalizes the first character in a string:\
        function capitalize(str) {\
        return str.charAt(0).toUpperCase() + str.slice(1);\
        }\
        This is a functioned named \"capitalize\" that takes an argument
        named \"str\", converts the first character (at index 0) of
        \"str\" to upper case, and then adds that first character to the
        beginning of the remaining letters in \"str\" beginning at the
        \"slice\" that starts at index 1 (the second character). If you
        run the following:\
        var city = \"paris\";\
        var capital = capitalize(city);\
        ...then you would receive an output of \"Paris\" upon calling
        \"capital\", because the capitalize() function performed its
        return on the argument \"str\" (in the form of the substituted
        variable of \"city\").

        -   **IMPORTANT:** Once a return keyword is triggered, it will
            **[STOP THE EXECUTION OF A FUNCTION]{.ul}**. Therefore, if a
            function includes an if statement, such as:\
            function capitalize(str) {\
            if (typeof str === \'number\') {\
            return \"That\'s not a string.\"\
            }\
            return str.charAt(0).toUpperCase() + str.slice(1);\
            }\
            ...if the user inputs a number rather than a word to the
            \"str\" argument, he will receive a return of \"That\'s not
            a string.\", and there will be no further execution of the
            second return statement.

-   **Higher Order Functions** are functions into which another function
    can be \"**Passed**\" as an argument. For example, JS includes a
    built-in function called setInterval(). Within the parentheses of
    this function, you first place the name of another function that you
    want setInterval() to run, and then follow that with the interval
    (in milliseconds) that the script should execute until terminated.
    Thus, if you want to have another function (which has already been
    previously set) run every second, you would state:\
    setInterval(anotherFunction, 1000);\
    Upon executing this statement, setInterval() will run
    anotherFunction() every 1000 milliseconds.

    -   **NOTE**: When the example above is executed, it will return a
        number (e.g., 661) in the console. To stop the function from
        running, simply run clearInterval(661).

    -   **ALSO NOTE**: If, in the above example, you want a function to
        run every second, but you don\'t want to name that function
        ahead of time, you can insert an **Anonymous Function**:\
        setInterval(**[function() {\
        ]{.ul} [// code that you want to run every second;\
        }]{.ul}**, 1000);

-   **Scope**

    -   Scope refers to the context in which JavaScript is being
        executed (i.e., which properties and variables are \"visible\"
        within a particular function, yet are excluded by or different
        in another function). For example, if you declare the following
        function:\
        function getNumber() {\
        var x = 40;\
        console.log(x);\
        }\
        ...the console will print 40 if you call the function. However,
        if you simply call \"x\", then the console will return an error
        saying \"x\" is undefined. This is because the scope in which
        \"x\" exists in the function differs from the \"**Global**\"
        scope, where \"x\" does not exist. Conversely, if you were to
        later define \"x\" as a variable with a value in the global
        scope, and then run the function, the function will still print
        40 notwithstanding the value of \"x\" in the global scope.

        -   **HOWEVER**: If you were to have set \"var x = 40;\" in the
            global scope, and then created the following:\
            function getNumber() {\
            console.log(x);\
            }\
            ...the Console will still print 40. This is because when a
            variable is defined outside of a function, you still have
            access to it inside of that function **[AS LONG AS]{.ul}**
            the interior of the function does not redefine that
            variable. In other words, a more-specific \"child\" scope is
            governed by values set in the \"parent\" scope unless
            otherwise stated. The converse, however, is not true, and
            the parent scope will not be governed by anything set in the
            child scope.

            -   **BUT NOTE**: If the variable was set FIRST in the
                parent scope, then directly modified in the function,
                e.g.:\
                var x = 40;\
                function getNumber() {\
                x = 80;\
                console.log(x);\
                }\
                ...then simply calling \"x\" in the console will print a
                value of 80. This is because the function is not
                declaring a \"new\" variable \"x\" within itself;
                rather, it recognized that there was already a variable
                \"x\" existing outside of itself and redefined that
                variable externally while incorporating the redefined
                value internally. **[HOWEVER]{.ul}**, had the function
                stated \"**[var]{.ul}** x = 80;\", then the function
                would have created its own \"x\" as an internal
                variable, and calling \"x\" globally would print 40.

```{=html}
<!-- -->
```
-   [**Arrays**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

    -   **Basics**

        -   Arrays are high-level data structures (ways of holding
            information using JS) containing lists of data. For example,
            rather than making four \"friend\" variables:\
            var friend1 = \'Mac\';\
            var friend2 = \'Dennis\';\
            var friend3 = \'Charlie\';\
            var friend4 = \'Dee\';\
            \...you could use an array by making a comma-separated list,
            like so:\
            var friends = \[\'Mac\', \'Dennis\', \'Charlie\', \'Dee\'\];

        -   Arrays are indexed starting at 0 (just like characters in a
            string). The index method is used to get data out of the
            array, e.g.:\
            console.log(friends\[0\]) // \"Mac\"\
            friends\[1\] + \' \<3 \' + friends\[2\] // \"Dennis \<3
            Charlie\"

        -   Arrays are useful in that they can be updated by simply
            stating, for example:\
            friends\[0\] = \'Frank\';\
            ...and all lines of code that would have otherwise produced
            \"Mac\" now say \"Frank\".

        -   Arrays are also useful in that new data can be added to them
            without modifying the original line of \"var friends ...\"
            Rather, you can simply assign a new value/string (or any
            other data, including \"true,\" \"null,\" or even other
            arrays) to the next available index, and it will be added to
            the array, e.g.:\
            friends\[4\] = \'Cricket\';

        -   To initialize an array without yet adding data to the array,
            you can simply state:\
            var friends = \[ \];\
            ...or...\
            var friends = new Array();

        -   Arrays also have a length property that can be called by
            using \".length\", e.g.:\
            var friends = \[\'Frank\', \'Dennis\', \'Charlie\', \'Dee\',
            \'Cricket\'\];\
            friends.length; // returns 5 (because there are 5 friend
            values)

        -   Arrays can be nested within arrays like so:\
            var friendGroups = \[\
            \[\'Friend 1\', \'Friend 2\'\],\
            \[\'Friend A\', \'Friend B\'\]\
            \];

            -   **NOTE**: When arrays are nested, you can call a
                specific index within a nested array like so :\
                console.log(friendGroups\[1\]\[0\]); // \"Friend A\"
                (takes the second\
                // index of the first array, and the\
                // first index of the nested array)

    -   **Built-In Array Methods**

        -   For a complete list of Array Methods, refer to the
            \"Methods\" section in the MDN link to \"Arrays\" above.

        -   Five Important Methods:

            -   **Push/Pop**

                -   Use push() to add a value to the **[END]{.ul}** of
                    an array (rather than having to count or use
                    \"length\" to figure out which index in the array
                    you would have to manually add the value to), e.g.:\
                    var colors = \[\'red\', \'orange\', \'yellow\'\];\
                    colors.push(\'green\'); // \[\'red\', \'orange\',
                    \'yellow\', \'green\'\]

                -   If you were to then state \"colors.pop();\", then
                    \"green\" would be removed, because pop() removes
                    the last item in an array.

                    -   **NOTE**: When pop() is used, the console
                        actually returns the removed variable. Because a
                        value is returned, that means it can be stored
                        as a variable if so stated:\
                        var removedColor = colors.pop(); // stores
                        \"green\"

            -   **Unshift/Shift**

                -   unshift() and shift() operate in the same way as
                    push() and pop(), except that they add/remove values
                    to the **[BEGINNING]{.ul}** of an array.

                    -   **NOTE**: While counterintuitive, remember that
                        unshift() is used to ADD, not to remove.

            -   **indexOf**

                -   indexOf() takes an argument and tries to find that
                    argument in a given array. If it finds it, then it
                    will return the FIRST index of where it\'s found in
                    the array, e.g.:\
                    var friends = \[\'Frank\', \'Dennis\', \'Charlie\',
                    \'Dee\', \'Cricket\'\];\
                    friends.indexOf(\'Dennis\'); // 1

                    -   **NOTE**: Remember that indexOf() will only
                        return the **[FIRST]{.ul}** index, so if the
                        same argument appears elsewhere in the array,
                        that index will not be returned.

                    -   **ALSO**: If an argument is **[NOT]{.ul}**
                        present, \"-1\" will be returned.

            -   **Slice**

                -   slice() is used to copy different portions of an
                    array, e.g.:\
                    var fruits = \[\'Banana\', \'Orange\', \'Lemon\',
                    \'Apple\', \'Mango\'\];\
                    var citrus = fruits.slice(1, 3);\
                    ...leads to...\
                    var fruits = \[\'Banana\', \'Orange\', \'Lemon\',
                    \'Apple\', \'Mango\'\];\
                    var citrus = \[\'Orange\', \'Lemon\'\];

                    -   **NOTE**: The first number in slice argument
                        signifies the first index that will be copied
                        (\"Orange\"), and the second number represents
                        where the slice will end **[AND IS
                        NON-INCLUSIVE]{.ul}** (\"Apple\"). Thus, only
                        \"Orange\" and \"Lemon\" are copied out.

                    -   **TIP**: If you want to **Duplicate** an entire
                        array, simply omit the numbers in the slice
                        argument, and all data in the array will be
                        copied over.

            -   **Splice**

                -   splice() changes the contents of an array by
                    removing and/or adding elements at any point in the
                    index.

                    -   To **Remove** an element, use this syntax:\
                        var fruits = \[\'Banana\', \'Orange\',
                        \'Lemon\', \'Apple\', \'Mango\'\];\
                        fruits.splice(1, 2);\
                        ...leads to...\
                        var fruits = \[\'Banana\', \'Apple\',
                        \'Mango\'\];

                        -   The splice syntax works by using the first
                            number as the index number at which to start
                            changing the array (in this case, index 1,
                            which is \"Orange\"). The second number is
                            the **Delete Count**, which can be 0 (to not
                            delete the starting index) or any other
                            positive number to indicate how many indices
                            (beginning from your starting index) are to
                            be deleted (in this case, delete two indices
                            starting with index 1, which means deleting
                            indices 1 and 2, i.e., \"Orange\" and
                            \"Lemon\").

                    -   To **Add** an element, use this syntax:\
                        var fruits = \[\'Banana\', \'Apple\',
                        \'Mango\'\];\
                        fruits.splice(1, 0, \'Orange\', \'Lemon\');\
                        ...leads to...\
                        var fruits = \[\'Banana\', \'Orange\',
                        \'Lemon\', \'Apple\', \'Mango\'\];

                        -   In this case, splice() is told to:\
                            (1) look at index 1 (starting as
                            \"Apple\"),\
                            (2) abstain from deleting the element at
                            index 1,\
                            (3) insert \"Orange\" as the new index 1,
                            and\
                            (4) insert \"Lemon\" after \"Orange\" (this
                            addition process can be repeated
                            indefinitely and will ensure that \"Mango\"
                            remains as the last index).

    -   **Array Iteration** is the process in which a code will run
        through every element in an array, rather than just one element.
        For example, message board comments are stored in an array, and
        they are only displayed when some code runs through that array
        and creates HTML content for each comment stored in the array.

        -   **For Each Iteration** (newer method):\
            var colors = \[\'red\', \'orange\', \'yellow\',
            \'green\'\];\
            colors.forEach(function(color) { // \"color\" is a
            placeholder to represent a console.log(color); // singular
            instance of any given element in\
            }); // the collection; call it whatever you want

            -   Essentially, the \"color\" placeholder argument merely
                represents the value of every element in the array.
                Thus, the code is calling the console.log() function
                \"for each\" element, and then passing in each
                element\'s value.

            -   Alternatively, you could set a function beforehand, and
                then run it through forEach():\
                var colors = \[\'red\', \'orange\', \'yellow\',
                \'green\'\];\
                function printColors(color) {\
                console.log(color);\
                }\
                colors.forEach(printColors);

            -   **IMPORTANT:** forEach() executes a callback function
                once for each element in the array in ascending order.
                The callback function is expected to have **[AT LEAST 1
                (BUT UP TO 3) ARGUMENTS]{.ul}** separated by commas).
                The first argument represents the **Element** in the
                array. The second argument represents the **Index** of
                said element. The third argument represents the
                **Array** that forEach() was called on (which will be
                the same for every iteration of the loop). Thus, if you
                want to print both the contents of a list along with its
                index number, you would state:\
                var colors = \[\'red\', \'orange\', \'yellow\',
                \'green\'\];\
                function printColors(x, i) {\
                console.log(i + \': \' + x);\
                }\
                colors.forEach(printColors);\
                ...which would yield:\
                0: red\
                1: orange\
                2: yellow\
                3: green

        -   **For Loop Iteration** (older method):\
            var colors = \[\'red\', \'orange\', \'yellow\',
            \'green\'\];\
            for (var i = 0; i \< colors.length; i++) {\
            console.log(colors\[i\]);\
            }

            -   The above code will start by printing index 0 of
                \"colors\" to the console, and repeat the process until
                reaching index 3. This is possible because the length of
                \"colors\" is 4, and the final index value is 3. As the
                final index in an array will always be one digit smaller
                than the length of the array, this loop will necessarily
                run until all array values are printed.

-   [**Objects**](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics)

    -   **Basics**

        -   An object, like an array, is a collection of related data
            (of any type) and/or functionality. Unlike an array, objects
            are meant to handle data that does not follow a logical and
            progressive order. Objects have no built-in order. Objects
            use the following **Syntax** (**Key-Value Pairs** where the
            \"key\" (name) is separated from the value by a colon, and
            all key-value pairs are separated by commas):\
            var objectName = {\
            member1Name: member1Value,

> member2Name: member2Value,
>
> member3Name: member3Value
>
> };

-   **Retrieving Data** from an object is done by either **Bracket or
    Dot Notation**:\
    var dog = {\
    name: \'Rusty\',\
    breed: \'Mutt\',\
    age: 3\
    };\
    ...bracket notation:\
    console.log(dog\[\'name\'\]); // \"Rusty\"\
    ...dot notation:\
    console.log(dog.name); // \"Rusty\"

    -   **Usage Notes:**

        -   You **[CANNOT]{.ul}** use dot notation if the property
            starts with a number:\
            someObject.1blah // invalid\
            someObject\[\'1blah\'\] // valid

        -   You **[CANNOT]{.ul}** use dot notation if the property name
            has a space in it (not a good practice anyway):\
            someObject.fav color // invalid\
            someObject\[\'fav color\'\] // valid

        -   You **[CAN]{.ul}** look up things using a variable when
            using bracket notation:\
            var str = \'name\';\
            someObject.str // doesn\'t look for \"name\"\
            someObject\[str\] // evaluates str and looks for \"name\"

-   **Updating Data** in an object is done just like an array (access a
    property and reassign it):\
    objectName\[\'propertyName\'\] = newPropertyValue;\
    ...or...\
    objectName.propertyName = newPropertyValue;

-   **Creating Objects** can be done in one of three ways:

    -   Make an empty object and then add to it:\
        var person = {};\
        person.name = \'Travis\';\
        person.age = 21;\
        person.city = \'LA\';

    -   Make an object by executing a built-in function and then add to
        it:\
        var person = new Object();\
        person.name = \'Travis\';\
        person.age = 21;\
        person.city = \'LA\';

    -   Make an object all at once:\
        var person = {\
        name: \'Travis\',\
        age: 21,\
        city: \'LA\'\
        };

-   Objects can be inserted within arrays, so that each item within an
    array is its own object. This is typical when working with an online
    array of comments, posts, friends, etc.:\
    var posts = \[\
    {\
    title: \'Article 1\',\
    author: \'Author 1\',\
    comments: \[\'Awesome post.\', \'Terrible post.\'\]\
    },\
    {\
    title: \'Article 2\',\
    author: \'Author 2\',\
    comments: \[\'I love this.\', \'I hate this.\'\]\
    }\
    \];

    -   To access the title of the first post, you would state:\
        posts\[0\].title

    -   To access the second comment of the second post, you would
        state: posts\[1\].comments\[1\]

```{=html}
<!-- -->
```
-   **Adding Methods to Objects**

    -   A \"method\" (e.g., alert(), prompt(), indexOf(), etc.) is a
        function that is a property inside of an object. console.log()
        is an example of a method that has been added to an object.
        \"console\" is a built-in object with \"log()\" as a built-in
        function. By putting the two together (console.log), you are
        having JS look at the \"console\" object and run its \"log()\"
        function.

    -   Adding methods to objects (rather than having them stand alone)
        is useful for grouping things together logically to avoid a
        \"**Namespace Collision**.\" For example, to have a function
        return \"WOOF\" when a \"dog\" object \"speaks,\" but have it
        return \"MEOW\" when a \"cat\" object speaks,\" you would
        state:\
        var pets = \[\
        {\
        type: \'dog\',\
        speak: function() {\
        return \'WOOF\';\
        }\
        },\
        {\
        type: \'cat\',\
        speak: function() {\
        return \'MEOW\';\
        }\
        }\
        \];\
        ...so that pets\[0\].speak() will return \"WOOF\", and
        pets\[1\].speak() will return \"MEOW\".

    -   **[This](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)**

        -   The \"this\" keyword behaves differently depending on the
            context. The following example illustrates how \"this\"
            behaves when used in methods that have been added to an
            object.

            -   Suppose you\'re making an app that has some comments,
                and you want to have some comment data stored in an
                object:

> var comments = {
>
> data: \[
>
> \'Good\',
>
> \'Bad\',
>
> \'Okay\'\
> \]
>
> };

-   Now suppose you want to make a method called \"print()\" and add it
    to \"comments\". You could define a separate function, and then
    \"print\" the data by running \"print(comments.data)\":

> function print(arr) {
>
> arr.forEach(function(elem) {
>
> console.log(elem)
>
> });
>
> }\
> print(comments.data); // \"Good,Bad,Okay\"

-   But if you want to add the print function to the comments object,
    you can use \"this\" to refer to the data that is contained in the
    same object (i.e., \"this\" object):

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
