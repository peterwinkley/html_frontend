            \"Ctrl+/\" to turn text into comment.

-   [**CSS**](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS)

    -   **The General Rule**

> selector {
>
> property: value;
>
> anotherProperty: value;
>
> }

-   For example, make all \<h1\> tags purple with 56-pixel font:\
    h1 {\
    color: purple;\
    font-size: 56px;\
    }

-   **Three Basic Selectors**

    -   **Element** selectors select all instances of a given element.
        For example, \"div\" is a CSS element selector that will modify
        the properties of all \<div\> HTML tags.

    -   The **ID** selector selects a single element with an octothorp
        (\"\#\") ID (only one per page). For example, the following
        HTML/CSS combination will result in the word \"hello\" appearing
        in yellow, while the word \"goodbye\" will remain as is:\
        \<div\>\
        \<p id=\"special\"\>hello\</p\>\
        \</div\>\
        \<div\>\
        \<p\>goodbye\</p\>\
        \</div\>\
        \#special {\
        color: yellow;\
        }

    -   The **Class** selector selects all elements in a given class by
        functioning just like an ID selector; however, a class is
        instead prefaced with a period (\".\"). For example, the
        following items marked as \"completed\" on a \"To Do List\" will
        be crossed out with a line:\
        \<div\>\
        \<p class=\"completed\"\>TASK \#1\</p\>\
        \</div\>\
        \<div\>\
        \<p class=\"completed\"\>TASK \#2\</p\>\
        \</div\>\
        .completed {\
        text-decoration: line-through;\
        }

        -   An element can be modified by multiple class or ID tags by
            simply adding a space between the two tag names, e.g.:\
            \<p class=\"completed uncompleted\"\>Text\</p\>

-   **Five More Advanced Selectors**

    -   The **Star (\*)** selector applies to every element on the page.

    -   The **Descendant** selector applies to selectors that have been
        \"nested\" under another. For example, if you want to modify the
        color of only those \<a\> tags that are nested within the \<li\>
        tags of a \<ul\> list, use the following:\
        ul li a {\
        color: red;\
        }

        -   In addition to HTML tags, CSS selectors such as \"ID\" or
            \"Class\" may be used within a Descendant selector.

        -   **HOWEVER**: If, for example, you have a second-tier \<ul\>
            nested within a first-tier \<ul\> that is nested within
            \<div id=\"box\"\>, and you only want to select the
            first-tier \<ul\> and not the second-tier, then you must use
            the \"\>\" combinator to select only the **[DIRECT]{.ul}**
            first-tier \"child\" \<ul\> (rather than the second-tier
            \"grandchild\" \<ul\>) of \<div id=\"box\"\>:\
            \#box \> ul {\
            color: red;\
            }

    -   The **Adjacent (+)** selector will select only the element that
        comes **[IMMEDIATELY]{.ul}** after another element (a
        \"sibling\" element, rather than a \"nested\" element). For
        example, to modify the font size of all \<ul\> tags that follow
        an \<h4\> tag (which are typed on the same \"level\" as the
        \<ul\> tags, and not nested under them), use the following:\
        h4 + ul {\
        font-size: 24px;\
        }

        -   If, in the above example, you want to select **[ALL]{.ul}**
            \<ul\> tags after any \<h4\> tag, then use the more
            generalized sibling combinator of \"\~\" instead of \"+\".

    -   The **Attribute** selector will allow the selection of any
        element based off of any attribute. For example, to change the
        font family of all \<a\> tags that link to Google, use the
        following:\
        a\[href=\"https://www.google.com/\"\] {\
        font-family: cursive;\
        }

        -   This selector an also be used to select all images of a
            particular source, or all inputs of a particular type, such
            as all checkboxes:\
            input\[type=\"checkbox\"\] {\
            border: 2px solid green;\
            }

        -   **TIP**: See the complete list of [**Attribute
            Selectors**](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors).

    -   The **Nth-of-Type** selector takes a specific number and selects
        the \"-nth\" instance of an element. For example, to change the
        background color of every second \<li\> tag in every list
        (literally meaning the second tag, not every other tag), use the
        following:\
        li:nth-of-type(2) {\
        background-color: rgba(100, 175, 225, 0.5);\
        }

        -   **NOTE**: To select every other tag, use the phrases (even)
            or (odd) instead of a specific number.

-   For more advanced selectors, view [**The 30 CSS Selectors You Must
    Memorize**](https://code.tutsplus.com/tutorials/the-30-css-selectors-you-must-memorize--net-16048).

```{=html}
<!-- -->
```
-   **CSS Location**

    -   CSS should generally be saved to its own file, but can also be
        included in the HTML head by using the \<style\> tag:\
        \<style type=\"text/css\"\>\
        li {\
        color: red;\
        }\
        \</style\>

    -   The preferred method is to use a \<link\> tag in the HTML head
        to refer to the separate file containing CSS:\
        \<link rel=\"stylesheet\" type=\"text/css\"
        href=\"directory/filename.css\"\>

-   **Specificity** is the means by which browsers decide which CSS
    property values are the most relevant to an element and, therefore,
    will be applied (e.g., if the body is styled to have red text, but a
    paragraph within the body is styled to have green text, then the
    text will be green because the green text style is more relevant to
    the specific paragraph than the general body).

    -   The following list of selector types increases by specificity
        (in magnitudes of 10):

        1.  Type selectors (e.g., li) and pseudo-element (e.g., :before)

        2.  Class selectors (e.g., .hello), attributes selectors (e.g.,
            \[type=\"text\"\]) and pseudo-classes (e.g., :hover)

        3.  ID selectors (e.g., \#hello)

    -   This [**Specificity
        Calculator**](https://specificity.keegan.st/) may be used to
        test CSS specificity rules.

