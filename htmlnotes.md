-   [**HTML**](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML)

    -   **Document** (individual elements combined to form an entire
        HTML page)

        -   **Doctype**: \<!DOCTYPE html\>

            -   Required as the first line of an HTML document
                (historical artifact).

        -   **Root Element**: \<html\>

            -   Follows the \"doctype\" and wraps around all content on
                the entire page.

        -   **Head Element**: \<head\>

            -   Container for things that do not appear as viewable
                content (e.g., keywords and descriptions that will
                appear in search results, CSS, character set
                declarations, etc.).

        -   **Character Set**: \<meta charset=\"UTF-8\"\>

            -   Allows document to use \"utf-8\" character set, which
                includes most characters from all known human languages
                (nests within head element).

        -   **Title**: \<title\>

            -   Sets the title that appears in browser tab (nests within
                head element).

            -   Also appears as the search result in Google.

        -   **Body**: \<body\>

            -   Contains all of the content that will be shown to the
                viewer.

    -   **Elements** (content + opening/closing tags)

        -   **Block Elements** form a visible block on a page (e.g.,
            paragraphs, lists, navigation menus, footers, etc.):

            -   **Paragraph**: \<p\>

            -   **Divider**: \<hr\>

            -   **Headings**: \<h1\> through \<h6\>

                -   **NOTE**: As a general rule, try to have only one
                    \<h1\> tag in your HTML document, and it should be
                    the biggest text element on the page.

            -   Generic **Container**: \<div\>

            -   **Lists** (each item within a type of list needs to be
                identified by the \"\<li\>\" tag):

                -   Ordered Lists (lists that are numbered): \<ol\>

                -   Unordered Lists (lists composed of bullet points:
                    \<ul\>

            -   **Tables**: \<table\>

                -   Table Row: \<tr\>

                -   Table Header (consists of one cell within a row):
                    \<th\>

                    -   Should be nested within \<thead\> under main
                        table (semantics).

                -   Table Data (consists of one cell within a row):
                    \<td\>

                    -   Should be nested within \<tbody\> under main
                        table (semantics).

                -   Borders can be added by entering \<table
                    border=\"1\"\>, although this is discouraged, as CSS
                    should be used for styling.

            -   **Forms** (interactive controls to submit information to
                a web server): \<form\>

                -   Typically contain the \"action\" (the URL to send
                    form data to) and \"method\" (the type of HTTP
                    request, such as \"GET\" to receive information from
                    the server and \"POST\" to add information to the
                    serve) attributes, e.g.:\
                    \<form action=\"/my-form-submitting-page\"
                    method=\"POST\"\>

                -   **Input** (used to accept data from the user):
                    \<input\>

                    -   The operation of \<input\> depends upon its type
                        attribute. For a complete list of attributes,
                        view [**Form Input
                        Types**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#Form_<input>_types).
                        Examples:

                        -   **Text** (can be used for user names):
                            type=\"text\"

                        -   **Password**: type=\"password\"

                        -   **Placeholder** (temporary text in input
                            fields; used with \"text\" and \"password\"
                            attributes):
                            placeholder=\"insert-text-here\"

                        -   **Button**: type=\"button\"
                            value=\"insert-text-here\"

                            -   Simple **Submit** button:
                                type=\"submit\"

                                -   Alternatively, if placed at the end
                                    of a form, use the following to
                                    create an even simpler submit
                                    button:\
                                    \<button\>insert-text-here\</button\>

                        -   **Checkbox** (square box for multiple
                            choices): type=\"checkbox\"

                            -   To have the checkbox already marked upon
                                loading, add the attribute \"checked\"
                                to the input.

                        -   **Radio Button** (circular icon for one
                            choice): type=\"radio\"

                            -   In order to make the user only able to
                                select one choice, you must add the
                                \"name\" attribute, which must be common
                                among all choices.

                            -   The \"value\" attribute is necessary for
                                the query string to understand the
                                meaning behind each choice; otherwise,
                                it will simply state \"name=on\".

                            -   Example:\
                                \<label for=\"cats\"\>Cats:\</label\>\
                                \<input name=\"pet-choice\" id=\"cats\"
                                type=\"radio\" value=\"CATS\"\>\
                                \<label for=\"dogs\"\>Dogs:\</label\>\
                                \<input name=\"pet-choice\" id=\"dogs\"
                                type=\"radio\" value=\"DOGS\"\>

                -   **Dropdown Menus**: \<select\>

                    -   For every possible option to select, use an
                        \<option\> tag.

                    -   In order for the query string to understand that
                        an option has been selected from the dropdown
                        menu, the \"name\" attribute must be included in
                        the \<select\> tag, e.g.:\
                        \<select name=\"color\"\>\
                        \<option\>White\</option\>\
                        \<option\>Black\</option\>\
                        \</select\>

                    -   If you want the query string to contain text
                        other than \"White\" or \"Black\" in the example
                        above, use the \"value\" attribute in the
                        \<option\> tag, e.g.:\
                        \<option value=\"happy\"\>\</option\>

                -   **Text Areas** (multi-line plain-text editing
                    control): \<textarea\>

                    -   You can specify how large the text area is by
                        using the \"rows\" and \"cols\" attributes.

                    -   In order for the query string to process the
                        data in the text area, you must use the \"name\"
                        attribute.

                    -   Example:\
                        \<textarea name=\"paragraph\" rows=\"10\"
                        cols=\"50\"\>\</textarea\>

                -   **Labels** (add captions for individual items in a
                    form): \<label\>

                    -   A label can be used by placing the control
                        element inside the \<label\> element, or by
                        using the \"for\" and \"id\" attributes:

                        -   For example,\
                            \<label\>Username\<input
                            type=\"text\"\>\</label\>\
                            ...is identical to:\
                            \<label
                            for=\"username\"\>Username\</label\>\
                            \<input id=\"username\" type=\"text\"\>

                -   **Validations** ensure that users fill out forms in
                    the correct format, e.g.:

                    -   The Boolean attribute \"required\" makes a field
                        mandatory:\
                        \<label\>Username\<input type=\"text\"
                        required\>\</label\>

                        -   Only works if the browser (like Chrome)
                            allows it.

                    -   By changing type from \"text\" to \"email\", the
                        browser will ensure that the field contains an @
                        symbol.

        -   **Inline Elements** are contained within block level
            elements and do not cause new lines to appear:

            -   Italics: \<em\>

            -   Bold: \<strong\>

            -   Generic Container: \<span\>

        -   **BUT NOTE**: **Empty Elements** contain only a single tag:

            -   Image: \<img src=\"https://www.google.com/logo.png\"\>

                -   **NOTE**: Image width can be modified like so...\
                    \<img width=\"50\"
                    src=\"https://www.google.com/logo.png\"\>\
                    ...but is discouraged, as styling should be done by
                    CSS.

            -   Input: \<input type=\"text\"\>

        -   For a complete list of elements, view the [**MDN Element
            Reference**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element).

        -   **TIP**: In Sublime, press \"Ctrl+Shift+D\" to replicate an
            entire line of an element.

    -   **Attributes** (extra info; does not appear in content; target
        of style info)

        -   Components:

            -   Space between it and the element name (or prior
                attribute),

            -   Attribute name followed by an equals sign, and

            -   Attribute value surrounded by quotation marks.

                -   Double or single quotes may be used, but must be
                    done consistently. You can nest a single quote
                    within a double quote (and vice versa), but if you
                    want to nest the same type of quote, you must use
                    **HTML Entities** (e.g., &quot; or &apos;).

        -   Examples:

            -   Class: \<p class=\"editor-note\"\>content\</p\>

            -   Can be paired with the \"anchor\" element: \<a\>

                -   Hyperlink with Title:\
                    \<a href=\"https://www.google.com/\"
                    title=\"Google\"\>content\</a\>

        -   **BUT NOTE**: **Boolean Attributes** can be written without
            a value, but technically always have only one value
            (generally the same as the attribute name:

            -   Disabled: \<input type=\"text\" disabled=\"disabled\"\>

                -   Creates a text box in which typing is disabled.

                -   May also be written as:\
                    \<input type=\"text\" disabled\>

        -   For a complete list of attributes, view the [**MDN Attribute
            Reference**](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes).

    -   **Entity References** (make special HTML syntax characters
        appear as normal text):

        -   \< = &lt;

        -   \> = &gt;

        -   \" = &quot;

        -   \' = &apos;

        -   & = &amp;

    -   **HTML Comments** (write comments in the code that are invisible
        to the user by wrapping them in special markers):

        -   \<!\-- and \--\>

        -   **TIP**: In Sublime, you can (1) select text, and (2) hold
            \"Ctrl+/\" to turn text into comment.
            \"Ctrl+/\" to turn text into comment.
