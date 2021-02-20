```
-   **[Bootstrap](https://getbootstrap.com/) (v.3)**

    -   **About**

        -   Bootstrap is the most popular HTML, CSS, and JS framework
            for developing responsive, mobile-first projects.

        -   To incorporate Bootstrap\'s CSS into your project, you can
            do either one of the following:

            1.  Download the bootstrap.css file, placing it into your
                project directory, and creating a \<link\> to the
                bootstrap.css file; or

            2.  Paste the following \<link\> to the bootstrap.css file,
                which is hosted online:\
                \<link rel=\"stylesheet\"
                href=\"https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css\"
                integrity=\"sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u\"
                crossorigin=\"anonymous\"\>

        ```{=html}
        <!-- -->
        ```
        -   **NOTE**: The semantics in Bootstrap have been criticized as
            being sometimes meaningless, and another contender for
            performing these tasks is [**Semantic
            UI**](https://semantic-ui.com/). However, Bootstrap is more
            popular and widely accessible through tutorials.

    -   **Important Pieces**

        -   [**Buttons**](https://getbootstrap.com/css/#buttons) require
            that they be identified first by a \"btn\" class followed by
            a second specific class.

            -   There are seven specific classes:

                -   Default (standard white button): btn-default

                -   Primary (provides extra visual weight; set to be the
                    primary action in a set of buttons): btn-primary

                -   Success (indicates successful or positive action):
                    btn-success

                -   Info (contextual button for informational alerts):
                    btn-info

                -   Warning (indicates caution should be taken):
                    btn-warning

                -   Danger (indicates a potentially dangerous action):
                    btn-danger

                -   Link (deemphasizes the button to look like a link
                    while behaving like a button): btn-link

            -   Buttons classes can be added to the \<a\>, \<button\>,
                or \<input\> elements, e.g.:\
                \<a class=\"btn btn-default\" href=\"\#\"
                role=\"button\"\>Link\</a\>\
                \<button class=\"btn btn-default\"
                type=\"submit\"\>Button\</button\>\
                \<input class=\"btn btn-default\" type=\"button\"
                value=\"Input\"\>\
                \<input class=\"btn btn-default\" type=\"submit\"
                value=\"Submit\"\>

            -   Button sizes can be reduced or increased by adding a
                third size class.

                -   Large: btn-lg

                -   Small: btn-sm

                -   Extra Small: btn-xs

            -   To make a button appear \"active,\" add the \"active\"
                class:\
                \<button class=\"btn btn-success btn-xs
                active\"\>Text\</button\>

            -   To disable a button, add a \"disabled\" attribute and
                set its value to \"disabled\":\
                \<button class=\"btn btn-success btn-xs\"
                disabled=\"disabled\"\>Text\</button\>

        -   [**Jumbotron**](https://getbootstrap.com/components/#jumbotron)
            (class=\"jumbotron\") extends the entire viewport to enlarge
            and showcase key content within.

            -   By default, the Jumbotron will extend across the entire
                width of the screen. To prevent this behavior, place the
                \<div class=\"jumbotron\"\> within a \<div
                class=\"container\"\>, as the \"container\" class in
                Bootstrap will add padding and margins to center the
                Jumbotron.

        -   [**Forms**](https://getbootstrap.com/css/#forms)

            -   [**Basic
                Form**](https://getbootstrap.com/css/#forms-example)

                -   Applying the class=\"form-group\" attribute to all
                    \<div\> elements in the form optimizes the spacing
                    between the elements (e.g., between the username and
                    password field).

                -   Applying the class=\"form-control\" attribute to an
                    \<input\> element improves the style of the normal
                    default appearance (adds rounded corners, padding,
                    spacing, focus effects, etc.), but also makes
                    changes to how the element behaves within the grid
                    system.

                -   Applying the class=\"help-block\" to a \<p\> element
                    modifies the text of a helpful hint to be more
                    subtle and subdued in appearance.

            -   [**Inline
                Form**](https://getbootstrap.com/css/#forms-inline)

                -   A basic form will lay its contents by stacking them
                    on top of each other. However, by applying the
                    class=\"form-inline\" to your form (which doesn\'t
                    necessarily have to be a \<form\> element) will
                    place its contents in a line from left to right.

        -   [**Navbar**](http://getbootstrap.com/components/#navbar)

            -   Navbars serve as navigation headers for an application
                or site. Navbars must be placed within a \<nav\>
                element, and, like buttons, require a general \"navbar\"
                class followed by a second specific class (typically
                \"navbar-default\", but may also be \"navbar-inverse\"
                for an inverted color scheme).

            -   A navbar may contain a \"**Brand**\" image (e.g.,
                company name or logo) as the first object in the navbar.
                This is constructed by creating a \"navbar-header\" and
                placing an anchored \"navbar-brand\" within the header
                (to add a link to the homepage, typically), and then an
                \<img\> within the brand, if desired:\
                \<nav class=\"navbar navbar-default\"\>\
                \<div class=\"navbar-header\"\>\
                \<a class=\"navbar-brand\" href=\"\#\"\>\<img
                src=\"\#\"\>\</a\>\
                \</div\>\
                \</nav\>

            -   The remaining content on the **Left Side** of the navbar
                should appear outside of the \<div\> containing the
                \"navbar-header\", and it should be placed in \<ul
                class=\"nav navbar-nav\"\>. Each item within the navbar
                should be marked with \<li\> tags (and those should
                contain an \<a\> tag if a link is desired).

                -   **NOTE**: The \<li\> tags will function normally
                    even if contained in a \<div\> rather than \<ul\>;
                    however, the \<ul\> should be used for semantics.

            -   To add additional content to the **Right Side** of the
                navbar, use \<ul class=\"nav navbar-nav
                navbar-right\"\>.

                -   To ensure that the content on the right side does
                    not press too squarely on the right edge of the
                    browser, everything within the \<nav\> should be
                    placed within a \<div class=\"container\"\> (fixed
                    width) or \<div class=\"container-fluid\"\> (full
                    width).

            -   To get the full benefit out of a navbar (such as dynamic
                dropdown menus), you must install the Bootstrap
                **JavaScript** file in your HTML \<body\>. Like
                \"bootstrap.css\", you can either use the
                \"bootstrap.js\" file downloaded from Bootstrap, or you
                can use the following link:\
                \<script
                src=\"https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js\"
                integrity=\"sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa\"
                crossorigin=\"anonymous\"\>\</script\>

                -   **NOTE**: Bootstrap\'s JavaScript requires
                    [**jQuery**](http://code.jquery.com/) to work, and
                    its \<script\> must be placed BEFORE Bootstrap\'s:\
                    \<script
                     src=\"http://code.jquery.com/jquery-3.2.1.js\"
                    integrity=\"sha256-DZAnKJ/6XZ9si04Hgrsxu/8s717jcIzLy3oi35EouyE=\"
                    crossorigin=\"anonymous\"\>\</script\>

            -   To have items **Collapse** when the browser hits mobile
                size, place everything that you want to collapse inside
                \<div class=\"collapse navbar-collapse\"\>.

                -   To add the \"hamburger\" icon that provides a
                    dropdown icon for the collapsed items, (1) change
                    the above \<div\> to read \<div class=\"collapse
                    navbar-collapse\"
                    id=\"bs-example-navbar-collapse-1\"\>, and (2) place
                    the following \<button\> within the
                    \"navbar-header\":\
                    \<button type=\"button\" class=\"navbar-toggle
                    collapsed\" data-toggle=\"collapse\"
                    data-target=\"\#bs-example-navbar-collapse-1\"
                    aria-expanded=\"false\"\>\
                    \<span class=\"sr-only\"\>Toggle
                    navigation\</span\>\
                    \<span class=\"icon-bar\"\>\</span\>\
                    \<span class=\"icon-bar\"\>\</span\>\
                    \<span class=\"icon-bar\"\>\</span\>\
                    \</button\>

                    -   The three \"icon-bar\" classes are responsible
                        for making the three bars in the icon.

                    -   The \"data-target\" attribute is responsible for
                        showing/hiding the content when the icon is
                        clicked. The value of this attribute should be
                        set to whatever \<div\> (by ID) you want to
                        show/hide.

            -   To keep the navbar **Fixed to Top**, include the
                \"navbar-fixed-top\" class, and add a minimum of 50px of
                padding to the top of the \<body\> (as the navbar itself
                is 50px high), although it may better to add a little
                more for extra space.

        -   [**Glyphicons**](http://getbootstrap.com/components/#glyphicons)

            -   To place icons, use the link above to find the class of
                icon you wish to use (e.g., an envelope icon), and
                insert it according to the following syntax:\
                \<span class=\"glyphicon glyphicon-envelope\"
                aria-hidden=\"true\"\>\</span\>

                -   The icon \<span\> should contain no text or child
                    elements.

                -   The aria-hidden=\"true\" attribute is used to hide
                    decorative icons on assistive technologies (e.g.,
                    **Screen Readers**). If the icon is not decorative
                    and is intended to convey meaning, then that meaning
                    can be added through by using \<span
                    class=\"sr-only\"\>, e.g.:\
                    \<div class=\"alert alert-danger\" role=\"alert\"\>\
                    \<span class=\"glyphicon
                    glyphicon-exclamation-sign\"
                    aria-hidden=\"true\"\>\</span\>\
                    \<span class=\"sr-only\"\>Error: Enter a valid email
                    address\</span\>\
                    \</div\>

                -   If you\'re creating controls with no text (such as a
                    \<button\> that only contains an icon), you can add
                    an \"aria-label\" attribute to the control and make
                    its value be a description that will appear on
                    screen readers.

            -   For additional icons, install [**Font
                Awesome**](http://fontawesome.io/get-started/) by
                placing the entire directory into your project, and then
                inserting the following into your \<head\>:\
                \<link rel=\"stylesheet\"
                href=\"path/to/font-awesome/css/font-awesome.min.css\"\>

    -   [**The Grid System**](http://getbootstrap.com/css/#grid)

        -   Bootstrap includes a fluid grid system that appropriately
            scales up to 12 columns as the device or viewport size
            increases. These 12 columns are contained within every
            instance of \<div class=\"row\"\>. You can then place
            additional \<div\> elements within each row and divide them
            by the following syntax: \<div class=\"col-size-\#\"\>.

            -   The \"**\#\"** option determines how many columns (out
                of 12) the \<div\> will occupy. In the following
                example, the first row will have 3 evenly spaced \<div\>
                groups that are each 4 columns wide, and the second row
                will have 2 \<div\> groups, with the first being 9
                columns in width and the second being 3 columns:\
                \<div class=\"container\>\
                \<div class=\"row\"\>\
                \<div class=\"col-md-4\"\>First Symmetrical
                Group\</div\>\
                \<div class=\"col-md-4\"\>Second Symmetrical
                Group\</div\>\
                \<div class=\"col-md-4\"\>Third Symmetrical
                Group\</div\>\
                \</div\>\
                \<div class=\"row\"\>\
                \<div class=\"col-md-9\"\>First Asymmetrical
                Group\</div\>\
                \<div class=\"col-md-3\"\>Second Asymmetrical
                Group\</div\>\
                \</div\>\
                \</div\>

            -   The \"**Size**\" option determines the width of the
                \<div\>, which determines the \"breaking point\" at
                which the \<div\> elements in a single row will take up
                a full 12 columns and stack on top of each other, rather
                than appear side-by-side.

                -   Four sizes and breaking points:

                    -   Extra Small (\"col-xs-\#\") for mobile phones:
                        Auto width.

                    -   Small (\"col-sm-\#\") for tablets: 750 pixels.

                    -   Medium (\"col-md-\#\") for smaller monitors: 970
                        pixels.

                    -   Large (\"col-lg-\#\") for larger monitors: 1170
                        pixels.

                -   Given the sizes above, if you were to have 4 \<div
                    class=\"col-md-3\"\> elements, the 4 elements would
                    appear side-by-side until the screen width dropped
                    below 970 pixels, at which point all 4 would stack
                    on top of each other. If, however, you wanted tablet
                    users (below 970 pixels) to see the first two
                    elements appear side-by-side and the last two
                    elements below, you would say: \<div
                    class=\"col-md-3 col-sm-6\"\>.

            -   This system also allows for **Nesting** additional
                \"row\" classes within other existing grid elements,
                e.g.:\
                \<div class=\"container\"\>\
                \<div class=\"row\"\>\
                \<div class=\"col-md-3 col-sm-6\"\>\
                \<div class=\"row\"\>\
                \<div class=\"col-sm-6\"\>First half of Group
                \"1\"\</div\>\
                \<div class=\"col-sm-6\"\>Second half of Group
                \"1\"\</div\>\
                \</div\>\
                \</div\>\
                \<div class=\"col-md-3 col-sm-6\"\>Group \"2\"\</div\>\
                \<div class=\"col-md-3 col-sm-6\"\>Group \"3\"\</div\>\
                \<div class=\"col-md-3 col-sm-6\"\>Group \"4\"\</div\>\
                \</div\>\
                \</div\>

        -   Notes for **Image Galleries**:

            -   Visit [**Unsplash**](https://unsplash.com/) for free
                high-quality images.

            -   In order for images to be appropriately sized within its
                grid, a quick method is to nest the image within the
                \"thumbnail\" class, e.g.:\
                \<div class=\"col-lg-4 col-md-6 col-sm-6\"\>\
                \<div class=\"thumbnail\"\>\
                \<img src=\"files/01.jpg\"\>\
                \</div\>\
                \</div\>

            -   **NOTE**:

                -   If you\'re looking for Pinterest-like presentation
                    of thumbnails of varying heights and/or widths,
                    you\'ll need to use a third-party plugin such
                    as [**Masonry**](http://masonry.desandro.com/), [**Isotope**](http://isotope.metafizzy.co/),
                    or [**Salvattore**](http://salvattore.com/).

                -   If you don\'t mind the images being of varying
                    heights, but want to get rid of the white space bug,
                    then
                    see [here](https://www.udemy.com/the-web-developer-bootcamp/learn/v4/questions/1989586).

                -   If you want to crop all of the images to the same
                    size, then see an example of this
                    [here](https://codepen.io/nax3t/pen/MJwpdb).

