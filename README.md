
# HTML Journey Notes
The goal of this section is to record an HTML and CSS cheat-sheet for a future reference guide so I don't have to rely on a mass amount of bookmarks. 

I'll keep things barebones for my own understanding while providing some reference links if I want to explore other niche areas further. 

## Table of Contents
- [HTML Journey Notes](#html-journey-notes)
    - [Table of Contents](#table-of-contents)
        - [Learning Process](#learning-process)
    - [Section 1: HTML Basics](#section-1-html-basics)
    - [Section 2: CSS Basics](#section-2-css-basics)
    - [Section 3: CSS Tips](#section-3-css-tips)
    - [Section 4: CSS Box Model](#section-css-box-model)
    - [Section 5: Advanced CSS](#section-5-advanced-css)
    - [Section 6: Website Setup](#section-6-website-setup)

### Learning Process
1. #### ***Course of Action***
    - Go through a learning section and record notes here
    - Apply to real world project
    - Go through next section; rinse/repeat

2. #### ***Documentation***
    - Go through Andrei Udemy Course
        - https://www.udemy.com/course/the-complete-web-developer-zero-to-mastery
    - Go through The Odin Project recommended readings
        - https://www.theodinproject.com/paths/foundations/courses/foundations/lessons/introduction-to-html-and-css
    - When I learn a complicated aspect, or not fully clear on something, go through other bookmarks to see if a different point-of-view is offered

### Section 1: HTML Basics
- HTML is creating the structure of the page, and CSS is the design
- Utilizes index.html as the primary directional HTML for crawlers, and can link-out to other html pages
1. #### ***Elements***
    - Almost all HTML on a page is pieces of content wrapped in a container
        - Thus almost everything needs an opening and closing tag
        - Using the correct tag with certain elements is important for SEO
        - https://developer.mozilla.org/en-US/docs/Web/HTML/Element
2. #### ***HTML Boilerplate Page Setup***
    - The homepage should always be named index.html as servers will look for it by default
    - **To trigger all the below in VScode, just type "!" without the quotes**
    - The first line should declare a doctype. In HTML, this would be
    ```
    <!DOCTYPE html>
    ```
    - After declaring a doctype, we have to put everything within the HTML container
    ```
    <html>
    </html>
    ```
    - In the page header, we will put metadata that is not viewable to the user, and other information that the page needs, not visible to the page visitor
    ```
    <head></head>
    ```
    - Within the head, there should always be a Title element. This is used to give the page title for the user. Otherwise it would just default to the page name of index.html
    ```
    <title></title>
    ```
    - Within the head we have to specify the character set encoding of the page so that it displays different symbols and characters
    ```
    <meta charset="utf-8"/>
    ```
    - Now we have to add a body element where all readable text will go. This will be after the header but within the html element
    ```
    <body></body>
    ```
    - After all of this, we'll have the following setup:
    ```
    <!DOCTYPE html>
    <html>
        <head>
            <meta charset="utf-8"/>
            <title>My First Webpage</title>
        </head>

        <body>
            Hello World
        </body>
    </html>
    ```
3. #### ***HTML Foundations***
    - Commenting in HTML: 
    ```
    <!-- this is a comment 
    -->
    ```
    - **If working within the body element with no other elements inside, it will just output 1 long line of text without proper formatting.** 

    - Paragraph: will add a new line after the closing tag
        ```
        <p></p>
        ```
    - Headings: Simply creating a hierarchy
        ```
        <h1></h1> through <h6>
        ```
    - Strong: makes text bold, but in a way that affects accessibility, as it marks the text as being important in things like screen readers.
        ```
        <strong></strong>
        ```
    - Em: same thing as strong, but for italicized text. Creates an emphasis on a certain text.
        ```
        <em></em>
        ```
    - Lists: These can be used inside each other as a nested list, as well
        - Unordered: bullet points
        ```
        <ul>
            <li> item 1 </li>
        </ul>
        ```
        - Ordered: numbers
        ```
        <ol>
            <li> item 1 </li>
        </ol>
        ```
    
4. #### ***HTML Links and Images***
    - Creating Links: Utilize the anchor element to create a link
        ```
        <a></a>
        ```
        - We now have to add an attribute to the anchor tag to tell it where to go. An attribute is made of two parts: a name and a value. In this case, we add a Hyperlink reference (href) to tell it where to go
        ```
        <a href="https://www.theodinproject.com/about">click me</a>
        ```
        - **By default, anchor tags have a blue color and underline.**
        - **This is called an Absolute link**
        - For Internal, i.e. Relative links, we reference the filename path. If there is another HTML file in the same folder to reference titled 'about.html', it would be:
        ```
        <a href="about.html">About</a>
        ```
        The same file in a folder called 'Pages' in the same directory would be:
        ```
        <a href="pages/about.html">About</a>
        ```
    - Images and Misc Self-closing tags: These tags do not require a closing tag. Similar to page links, we utilize the img element, but use the src attribute instead of href. The biggest difference is that no closing tag is needed. We can also put multiple attributes within the img element, such as specifying the size and width.
        ```
        <img src="www.linkhere.com/image.png"> 
        ```
        - This can be done with both absolute and relative paths
            ```
            absolute: <img src="www.linkhere.com/image.png"> 
            relative: <img src="images/dog.jpg">
            ```
        - Paths can be a bit tricky. Using the above example, if we wanted to use the dog image but we were in the about page, which is in it's own folder. To go up one level in folder heirarchy, we use 2 dots like so: ../
            ```
            <img src="../images/dog.jpg">
            ```
        - To put meta data on the image, for both SEO and accessibility, we use 'alt' attribute right after the img location
            ```
            <img src="www.linkhere.com/img.png" alt="this is a cool image"> 
            ```
        - To add size and width
            ```
            <img src="www.linkhere.com/img.png" width="42" height="42" alt="this is a cool image"> 
            ```
        - Differences in image types and when to use them:
            - PNG: Ideal for icons, technical diagrams, logos etc as they utilize colors and opacity better than JPG, but are larger in size.
            - SVG: Vector is ideal for all the same thing as PNG, as they scale without losing quality, making them ideal for responsive design. First choice in those scenarios, but not always available. The only downside is text scaling, which can be solved by converting to outlines using Sketch or Illustrator.
            - JPG: Ideal for photos due to file size scaling, but does not show transparent pixels. 
        - Commonly used self closing tags
            ```
            <br> = Line break
            <hr> = Horizontal line added
            ```
5. #### ***HTML Forms***
    - Using the form tag:
        ```
        Within the form tags, we have to specify the input type
        <form>
            (you can put text before the input box here)
            <input type="text">
        </form>

        To add a button, just change input type to "submit"
        To specify the name, you would add a value="" attribute
        <input type="submit" value="register">

        To clean the information in the form, the input type "reset" works
        <input type="reset">

        There are other input type's such as "email" which will check if the information entered is in the email format. 
        "Date" is another popular one.
        ```

    - Other types of input types
        "Radio" will create clickable buttons
        "Checkbox" will be selectable boxes
        "Password" will hide all typed responses
        ```
        Gender <br>
            <input type="radio">Male<br>
            <input type="radio">Female<br>
        However, when adding multiple buttons, they will all remain clickable as there is nothing that specifies they are connected. We have to use the "name" attribute to link them.

         Gender <br>
            <input type="radio" name="gender">Male<br>
            <input type="radio" name="gender">Female<br>       

        ```
    - If we want to require a certain form element to be filled out before submitting, we can add the "required" attribute to a form element. The idea is that forms are never required, thus defaulting to false. So if we add the "required" word, it assumes it's true and we don't have to specify.
        ```
        Email <input type="email" required>
        ```
    
    - If we want a dropdown form
        Within the form, we'll need to structure the dropdown similar to an unordered list
        ```
        Dropdown Name <br>
            <select>
                <option value="audi">Audi</option>
                <option value="BMW">BMW</option>
            </select>
        ```
        We can add attributes to the select tag, such as "multiple", which allows for multiple selections.

    - Form submission
        We have to specify the internal names of the data fields so the query is sent to the back-end in a clean manner. To do this, we just add a name= attribute to every field
        ```
        ...
        Last Name <input type="text" name="lastName"><br>

        For a "radio"-like input type, we have to add a value as well for specification
        Gender <br>
            <input type="radio" name="gender" value="male">Male<br>
            <input type="radio" name="gender" value="female">Female<br>
        We have to do the same for the <value> tag as well, but this time it's not needed for the input type individually
        <select name="cars">
            <option value="audi" name="audi">Audi</option>
            <option value="BMW" name="bmw">BMW</option>
        </select>>
        ```

### Section 2: CSS Basics
- Utilizes style.css
- 'Cascading' in CSS means that it will execute commands in order, like a waterfall method, so the last command will override previous requests for potentially the same item. 
    - As a result, it's best practice to add selectors in the stylesheet in the same heirarchy as the HTML - i.e. head selectors coming before body selectors
1. #### ***CSS Fundamentals***
    - Telling the HTML file to look at our CSS file. We want to put this in the header section
        ```
        <link rel="stylesheet" type="text/css" href="style.css">
        Type means the media type, and rel means rleationship to this (html) file.
        Then in href, put the link to style.css, wherever it lies in the folder. Will have to do this to every HTML page I want to share that particular css file. I can do different styles on different pages by adding a different css file for those pages, and linking appropriately.
        ```
    - Commenting-out:
        ```
        Can use command+/ hotkey, or:
        /* text here
        */
        ```
    - In essence, we have to identify the 'selector', the 'property, and the value of that property. The code looks like this:
        ```
        Note, these are placeholders
        selector {              // selector = what is being selected
            property: value;    // property = what to change, and value = how much
        }

        So if we wanted to apply a color to a something like an h2 in our code, the same code structure would be:
        h2 {
            color: red;
        }
        We can also add multiple properties within the h2 element, like text-align: center
        ```
    - We can also utilize in-line CSS styles without the stylesheet, meaning that styles can be applied as attributes to elements in our HTML pages. This is not commonly used but good to know so you don't get confused when viewing.
        ```
        Adding a style attribute to the header:
        <header style="background-color:blue"> </header>
        ```
        - We can also add style tags to the page head element like so
        ```
        In this example, adding a different background color to a list
        <style>
            li {
                background-color: purple;
            }
        </style>
        ```
2. #### ***CSS Properties***
    - How to make a universal selector
        ```
        * {
            property: value;
        }
        ```
    - A basic way to modify one element from our stylesheet:
        ```
        This adds to H2: a color, aligns it to the center of the page, adds a 5px border around it
        h2 {
            color: red;
            text-align: center;
            border: 5px solid purple;
        }
        ```
    - Adding background images
        ```
        selector {
            background-image: url(image-or-link-path-here.jpeg)
        }
        However, chances are the alignment is off. We can add another property like:
        background-size: cover;
        ```
    - Removing list bullets/numbers
        ```
        li {
            list-style: none;
        }
        If we want to display them horizontally, we can use the display property

        li {
            list-style: none;
            display: inline-block;
        }
        ```
3. #### ***CSS Selectors***
    - we can add multiple selectors to our css
        ```
        h2, p {
            color: red;
            text-align: center;
            border: 5px solid purple;
        }
        ```
    - Selectors are powerful as we can create our own elements, in that we can define a section that already might have a CSS element, but there are certain ones that we want excluded from the main CSS properties into their own definition
        ```
        In the HTML, if we add class="whatever name here" to a paragraph tag, then we can define that in our CSS. 
        For example, in the HTML Part:
        <p class="customname">Lorum Ipsum</p>
        Then in the CSS, add a reference to the new selector:
        .webtext {
            border: 5px dashed green;
        }

        We can add multiple classes to same line as well. So paragraph would be:
        <p class="class1 class2">
        ```
    
    - If we want to add a property to everything, instead of typing it out we can just use * as the element, and it will apply it to everything unless something overrides it in the casecade on further down code.

    - Element within Element is done just by adding Element1 Element2 with no comma and a single space. This says that the selector only applies if Element2 is within Element1.

    - Hover can be added to an element to give a hover effect
        ```
        p:hover{
            text-align:center;
        }
        ```
    
    - last-child and first-child can be added to an element to select the last or first item with that element name
        ```
        .webtext last-child{
            border: 5px dashed green;
        }
        ```

4. #### ***Text and Fonts***
    - text decoration can highlight an entire section in something like underline
        ```
        p {
            text-decoration: underline;
        }
        or
        p {
            text-decoration: line-through;
        }
        ```
    - text transform can change the font style to all uppercase and other features 
        ```
        p {
            text-transform: uppercase;
        }
        ```
    - line height can determine the line height, in pixels, of space between lines
        ```
        p {
            line-height: 20px;
        }
    - to change the font actual size, best to do by percentage:
        ```
        p {
            font-size: 150%;
        }
        ```
    - to change the font family, we do this:
        ```
        p {
            font-family: Georgia;
        }
        Note: if something is multiple words, you have to use quotation marks around it

        If we are doing a custom font, it's best to add a fallback option like so:
        p {
            font-family: "custom font", Georgia;
        }
        ```
    - to change font we would use font style
        ```
        p {
            font-style: italic;
        }
        ```
    - font weight we can specify a number or something like bold
        ```
        p {
            font-weight: bold;
        }
        ```
    - to add a Google Font to our page, we do this:
        ```
        1. Get the tag html from google fonts, for ex: 
        <link href="https://fonts.googleapis.com/css2?family=Roboto:ital,wght@1,100&display=swap" rel="stylesheet"> 

        2. Add the link tag to the <head>

        3. Google Fonts will say what to add to our CSS, for ex:
        font-family: 'Roboto', sans-serif;

        4. Add the style to whereever we want to use the font in our style.css
        ```

### Section 3: CSS Tips
1. #### ***CSS Image Alignment***
    - If an image is above text or weirdly aligned, try the float attribute. This will wrap the text around.
        ```
        img {
            float: right;
        }
        ```
    - When adding a footer, sometimes the footer alignment can get messed-up if having an image float above it, as the image will float next to text in the footer. Best practice is to 'clear' the float in relation to the footer in the CSS, like so:
        ```
        this should be going after the float

        footer {
            clear: both;
        }
        ```
### Section 4: CSS Box Model
1. #### ***Box Model***
    - Good to use 'inspect' browser dev tools to look at box model to better understand the layout
    - CSS box model is structured like so: https://www.w3schools.com/css/css_boxmodel.asp
    - Div's are crucial to structuring a site. They break up sections into containers that we can style and manipulate through CSS. Most sites do parent-child div's - i.e. divs within divs
        ```
        We assign a <div></div> anywhere in the body, but we should assign a custom class so we can link it to the CSS
        <div class="custom-class"> Can put text here </div>

        Then in the CSS, reference the class like a new selector
        .custom-class {
            border: 5px red;
            whatever other things I want to add to the div element
        }
        ```
    - Padding is the space on the inside of the div element border
        ```
        Padding goes clockwise starting at the top
        padding: 5px 3px 3px 5px;
        padding: top right bottom left;

        Or we can just do padding for all 4 sides with just 1 number
        padding: 5px;

        Or, we can to top/bottom and left/right like so:
        padding: 5px 5px;
        padding: top/bottom left/right;
        ```
    - Margin is the space on the outside the div element border
        ```
        Same as padding - clockwise
        margin: 5px 3px 5px 5px;
        ```
    - To change the content area in the box model, we can simply assign a height and width
        ```
        .boxmodel {
            height: 30px;
            width: 30px;
        }
        ```

2. #### ***Sizing***
    - There are more sizing attributes than just pixels and percentages
        ```
        Adding an inline em attribute will multiply the size relative to the other referenced, containing element. For example:
        There is a <p> tag within our html and it's font-size is assigned in the CSS. If we add an inline element like <span> within that <p> tag, we can then add the <span> element to the CSS and specify the font-size with an em, which will multiply the size to whatever the <p> size is.
        span {
            font-size: 5em; //this will be 5x the <p> value
        }
        ```

### Section 5: Advanced CSS
1. #### ***Display Types***
    - Most elements will default to display: block. What does that mean?
        - This means that block elements will appear on the page stacked atop of each other. Each new element will start on a new line. 
        - For example, a simple paragraph in HTML is a block. Put an outline around the paragraph to see what it looks like.
        - By default they have a width of 100%. This could be limited by the parent element.
            - Even if you put width at 50%, the blocks will still stack vertically.
    - A standard inline element is something like span or paragraph tags.
        - The problem about trying to add CSS to these elements is overlapping margins. This is fine for things like links, but if we want to make an actual element like a button, then the inline block is better.
    - Inline block elements do not stack on each other and will be within the same line. An example of this is an HTML link in an anchor tag.
        - The benefits of using inline blocks elements is that you can give margin, padding, etc to inline items without overlapping issues
        - These aren't used much anymore as flexbox can accomplish the same outcome with better features. 
        - Common uses include buttons being side-by-side
            - You would use display: inline-block

2. #### ***Flexbox***
    - Flexbox is used to make modern designs easier than using traditional Grid.
    - We activate flexbox by assigning the flex attribute in CSS
        ```
        .container {
            display: flex;
        }
        This assumed .container is part of a div, so we are saying that everything inside that div is part of flexbox.
        ```
    - We then can add different properties to the flexbox, such as:
        ```
        .container {
            display: flex;
            flex-wrap: wrap; //this wraps the images for a responsive design
        }

        justify-content: center;
        this will center all content in all responsive situations
        ```
    - We can add a property like transform and hover to add some animations
        ```
        img {
            transition: all 1s; //says that I want all images to transition when an action has taken place, and add a 1-second duration
        }
        then we need to add
        img:hover {
            transform: scale(1.1);
        }
        this part says that when I hover, I want the image to scale to 1.1* its size
        ```

### Section 6: Website Setup
1. #### ***Bootstrap***
    - The purpose of using things like Bootstrap is the same as using HubSpot; modules and snippets of code are already built out and you can search their database of what you are looking for, and adapt it for your own needs.
    - The interesting thing with bootstrap is that we don't even have to download the files if we don't want to. We can add their CDN (Content Delivery Network) css/js href link in our header. 
    - After some googling, it seems most devs will use it minimally. For example, maybe a button or a simple function. Or maybe they'll use it to get a quick site prototype up and make sure the backend works. Then they'll just redo it with cleaner code. 
    - Any element definitions we make within our stylesheet will override bootstrap items.
        ```
        So if we define a bootstrap button like:
        btn-danger
        in the style.css as

        .btn-danger {
            background-color: orange;
        }

        It will override the bootstrap button color of red.
        ```
    - Bootstrap's power comes from the responsiveness of its grid system. 
        - The layout is done via a column format: 12 total
        - In the div class itself - called 'col' as an element name by bootstrap, you can specify it changing as it moves across screen sizes, as seen here: https://getbootstrap.com/docs/5.1/layout/grid/
        - You can specify multiple different attributes in the div class, meaning you can have it do different actions as it shrinks and expands. For example, having a mobile menu expand outward when it goes into a 1920 screen.
        ```
        An example of code would be:
        <div class="row">
            <div class="col" col-sm-6 col-md-12 col-lg-12">
            1 of 2
            <div class="col" col-sm-3 col-md-6 col-lg-12">
            1 of 2
        </div>
        Whereas the numbers next to the size are the width size out of the total of the 12 columns that bootstrap uses. 
        ```