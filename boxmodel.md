
    -   In a document, each element is represented as a rectangular box.
        In CSS, each of these boxes is described using the standard
        \"box model.\" Each box has four edges: (1) **Content
        Edge**, (2) **Padding Edge**, (3) **Border Edge**, and (4)
        **Margin Edge**. Padding is the space between the border and the
        element within the border, and the margin is the space between
        the border and everything outside of the border.

        -   The content edge can be controlled by setting the \"width\"
            and \"height\" properties in \"px\" or \"%\" (with
            percentage in relation to the parent element), which in turn
            pushes out the border edge as well, as there is direct
            contact between the content and border (if no padding has
            yet been set).

            -   **NOTE**: By using the \"max-width\" property in
                conjunction with \"width\", you can tell the browser to
                make an element\'s width a certain percentage, but then
                also cap that width to a maximum number of pixels,
                e.g.:\
                \#container {\
                width: 66.66%;\
                max-width: 700px;\
                }

        -   Space can be added between the content edge and border edge
            (and between the border edge and the next element\'s edge)
            by using the \"padding\" and \"margin\" properties
            respectively (in \"px\" or \"%\").

            -   By default, padding and borders are set to go around all
                edges of an element, but can be limited by using more
                specific properties for top, right, bottom, and
                left---such as \"padding-left\" or \"margin-top\".

            -   Alternatively, rather than typing a line of CSS for all
                four sides, the following shorthand can be used (with
                the first value setting the top property, and the
                remainder moving in a clockwise fashion):\
                p {\
                margin: 20px 40px 60px 80px;\
                }

        -   **NOTE**: By setting the \"margin\" property to \"auto\" on
            the left and right, an element will automatically be
            horizontally centered:\
            p {\
            margin: 0 auto 0 auto;\
            }

            -   The above syntax can also be shorted as (with the first
                value representing the vertical axis, and the second
                value representing the horizontal axis):\
                p {\
                margin: 0 auto;\
                }

-   **Colors**

    -   Colors can be created through the **Hexadecimal** system by
        combining the octothorp (\#) with a string of 6 hexadecimal
        \"numbers\" from 0-F, e.g.:\
        color: \#FF1493;

        -   This system follows an RGB scheme in which the first two
            numbers modify the amount of \"red,\" the second two modify
            \"green,\" and the last two modify \"blue.\"

    -   Alternatively, colors can be created through the **RGB** system:
        3 channels consisting of red, green, and blue, with each ranging
        from 0-255, e.g.:\
        color: rgb(0, 255, 0);

    -   Colors can be made **Transparent** through the RGBA system. Just
        like RGB but with an alpha (transparency) channel ranging from
        0.0-1.0, e.g.:\
        color: rgba(11, 99, 150, .6);

-   **Backgrounds**

    -   Follows the same format as colors, e.g., background: \#FF6789;

    -   The background property can also set a background image, e.g.:\
        body {\
        background: url(http://www.website.com/image.png);\
        }

        -   To prevent the background from **Repeating** an image, add
            the following property:\
            background-repeat: no-repeat;

        -   To allow the background image to **Stretch** out across the
            entire body, use:\
            background-size: cover;

-   **Borders**

    -   Borders have three key properties: \"width\" (typically in
        pixels), \"color\" (as noted above), and \"style\" (generally
        solid, dotted, or dashed). All three properties must be present
        in order for a border to take effect, e.g.:\
        h1 {\
        border-width: 5px;\
        border-style: solid;\
        border-color: purple;\
        }

    -   The alternative shorthand syntax may also be used (in the
        specified order):\
        border: 5px solid purple;

-   **Fonts**

    -   **Font-Family** specifies the font for an element:\
        p {\
        font-family: Arial;\
        }

        -   While not always necessary, you may sometimes have to put
            quotation marks around the font name---particularly when the
            font name begins with a number.

        -   [**CSS Font Stack**](http://www.cssfontstack.com/) shows
            what percentages of operating systems have a given system
            font (useful for choosing a safe bet on system
            compatibility).

            -   However, rather than using those limited fonts, it is
                better to use [**Google
                Fonts**](https://fonts.google.com/), choose a font, and
                embed the font\'s stylesheet link in your HTML \<head\>
                prior to the CSS link, e.g.:\
                \<link
                href=\"https://fonts.googleapis.com/css?family=Esteban\"
                rel=\"stylesheet\"\>

    -   **Font-Size** specifies how big the font appears (typically in
        pixels or \"px\"):\
        h1 {\
        font-size: 25px;\
        }

        -   Another size unit is \"em\", which dynamically sets font
            size in relation to a parent element. For example, if you
            want to make a section of a paragraph\'s text in \<span\>
            tags be twice the size of the rest of the text in the \<p\>
            tags, you would say:\
            span {\
            font-size: 2em;\
            }

            -   **BUT NOTE**: What constitutes the \"standard\" 1em
                (i.e., the default font size on a page without CSS
                markup) varies from browser to browser, although the
                size is typically around **[16 PIXELS]{.ul}**. To ensure
                uniformity among browsers, it is useful to set the
                body\'s font size at the outset.

            -   **ALSO**: Similar to \"em\" is \"rem\", which---rather
                than setting font size in relation to the parent
                element---sets the font size in relation to the \"root\"
                element on the page (i.e., the default font size
                discussed above).

    -   **Font-Weight** specifies how thick or thin the font appears.

        -   Typically involves absolute values of \"normal\" or
            \"bold\", or relative (to parent) values of \"lighter\" and
            \"bolder\", but can also be assigned a numeric value in
            increments of 100 generally from \"100\" to \"800\"
            depending on the font itself.

    -   **Line-Height** controls the height of a given line (similar to
        changing line spacing in Word to 1.5 or 2.0, which means that a
        larger font will result in larger spacing).

    -   **Text-Align** controls where an element\'s text is aligned on
        the page (typically \"left\", \"right\", and \"center\").

    -   **Text-Decoration** is used to give text effects such as
        \"underline\", \"overline\", or \"line-through\".

-   **Float**

    -   Normally, block level elements (such as \<div\>) are stacked
        directly underneath the preceding element on the page. To change
        this, use the \"float\" property and specify a value of the
        direction in which the element should float (\"left\",
        \"right\", \"none\").

    -   When an element is floated, it is taken out of the normal flow
        of the document (though still remaining part of it), and it is
        shifted to the left or right until it touches the edge of its
        containing box, or another floated element.

    -   When \<img\> tags are laid out in a consecutive sequence, HTML
        automatically places some small amount of white space between
        the images. If you want to remove the white space, you can use
        \"float\" to remove that white space.

```{=html}
<!-- -->
```
