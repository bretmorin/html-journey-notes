
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

    - Navigation in a header is typically done through the nav tag, indicating that many links will be contained inside, typically via an unordered list.
        ```
        <nav></nav>
        then
        <nav>
            <ul>
            </ul>
        </nav>
        ```
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
    - A common practice for the body and HTML is to define it in the CSS for a few things, like:
        ```
        body, html {
            width: 100%; //making sure the body and html are max width
            height: 100%;
            font-family: 'Montserrat', sans-serif; //quoted font defined in html via Google Fonts link, and sans-serif being the fallback
        }

        This is good when combining with things like bootstrap, just to make sure everything is utilizing max width
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
    - Selectors default to select everything underneath it - i.e. child elements. For example:
        ```
        <div class="container">
            <p>some text here</p>
                <h2>some text here</h2>
        </div>

        In the CSS:
        .container {
            width: 100%;
        }
        ```
        - In this above example, the H2 would have a width of 100%.
        - Now, if we add a greater than symbol in the css element field, that would limit it to only 1 descendent. For example:
        ```
        .container > p {
            width: 100%;
        }
        ```
        - Now only the paragraph text would have 100% width, not h2.
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
    - The more common font size is 'rem' which is the multiplier of the font size of the browser. So 2rem would be 2x the browser's font size. This is typically seen as the easiest way to deal with font with responsive designs.
    - Another font alternative is 'em'. Many devs find this a bit overcomplicated but it is still quite common.
        - Adding an inline em attribute will multiply the size relative to the other referenced, containing element. For example:
        - There is a <p> tag within our html and it's font-size is assigned in the CSS. If we add an inline element like <span> within that <p> tag, we can then add the <span> element to the CSS and specify the font-size with an em, which will multiply the size to whatever the <p> size is.
        ```
        span {
            font-size: 5em; //this will be 5x the <p> value
        }
        ```
    - For responsive height sizing, vh (viewport height) is a best-practice sizing method
        ```
        .custom-element {
            height: 50vh //this means it will always be 50% of 
            viewport height
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
3. #### ***Advanced CSS Grid***
    - A quick note: if in firefox, can easily inspect all grid boxes by dev tools->layout (on the right) and clicking on the container.
    - Look at the differences between CSS grid and flexbox: https://www.google.com/search?q=css+flexbox+vs+grid&client=firefox-b-d&sxsrf=AOaemvLWJ2PytCy02CBlsePEPZ_MT8f2tQ:1634150062335&source=lnms&tbm=isch&sa=X&ved=2ahUKEwjJ9OWvg8jzAhXuQzABHWJCDeoQ_AUoAXoECAEQAw&biw=790&bih=762&dpr=2
        - these can be complimentary tools, as opposed to having to use each one by itself
        - CSS grid is great for when you have both columns and rows of different sizes, and flexbox is great for when you have one dimension (all rows or all columns)
    - Once we determine CSS grid is the way to go, we need to create a container and put everything in there.
        ```
        <div class="container"></div>
        ```
    - We then have to add CSS to our container, similar to flexbox, and change the display type. We also need to add grid-template-columns to tell the page how many columns we want to use.
        ```
        .container {
            display: grid;
            grid-template-columns: 300px 300px; //this will act as 2 grids because there is 2 numbers
        }
        ```
    - Another one we can add is grid-gap, which will add spacing between grid items
        ```
        .container {
            display: grid;
            grid-template-columns: 300px 300px; 
            grid-gap: 20px;
        }
        ```
    - Now the issue with defining size as pixels is that it's not very responsive. When you get smaller, those grids will still remain at the pixel amount, which may seem big. CSS grid gives us a tool that is the best to use for sizing: a fraction - fr - a total fraction of the total page size.
        ```
        1 fr will only result in 1 column, while 1 fr 1fr will give 2 50% columns

        grid-template-columns: 1fr 1fr;
        ```
        - There is a shortcut for fractions with the repeat property
        ```
        grid-template-columns: repeat(3, 1fr);
        This will repeat 1fr, 3 times
        ```
        - There is another way to do this with the auto property
        ```
        grid-template-columns: auto 1fr 2fr;
        This will auto resize(scale) to fit the content. 
        ```
        - Now perhaps the best way to do this for responsiveness is to do:
        ```
        grid-template-columns: repeat(auto-fill, minmax());
        Inside the minmax we want to define
        1. the minimum size wanted
        2. the maximum size wanted of each item. This means the container itself will auto adjust in size based on the viewport to keep that item the specified size.

        so...
        grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
        This will be minimum 300px. As soon as it goes above 300px in viewport, it expands the grid and keeps each item at 300px
        ```
    - CSS grid also allows us to define rows as well; not just columns. 
        ```
        If using fr for sizing, it will compare the other rows
        grid-template-rows: 1fr 2fr

        This will result in the 2nd row being twice as big as the first
        If there are more than 2 rows in this example, the 1fr will keep
        repeating after the 2fr
        ```
    - Now everything above was done within a container. What if we want to apply CSS grid to our functions? 
        - We can specify a certain item to cover a certain amount of grid areas.
        ```
        .element-item-here {    
            grid-column-start: 1;
            grid-column-end: 4;
        }
        This will make that item cover the size of 1 to 4 grids. 
        ```
        - The short-hand way to do this is:
        ```
        .element-item-here {
            grid-column: 1/4;
        }
        ```
        - Another way to do this is to span it across a few grids. This means there is no start area for it, and it will take up that space wherever. It will, however, never span less than the amount specified.
        ```
        .element-item-here {
            grid-column: span 2;
        }        
        ```
        - The problem with this is that it removes responsiveness because it makes sure the specified size matches what we told it to do.To help with responsiveness, we can add a '-1' that means it will go all-the-way to the end of the viewport.
        ```
        .element-item-here{
            grid-column: 1/-1;
        }
        ```

### Section 6: Website Setup
1. #### ***Bootstrap***
    - The purpose of using things like Bootstrap is the same as using HubSpot; modules and snippets of code are already built out and you can search their database of what you are looking for, and adapt it for your own needs.
    - The interesting thing with bootstrap is that we don't even have to download the files if we don't want to. We can add their CDN (Content Delivery Network) css/js href link in our header. 
    - After some googling, it seems most devs will use it minimally. For example, maybe a button or a simple function. Or maybe they'll use it to get a quick site prototype up and make sure the backend works. Then they'll just redo it with cleaner code.
    - The majority of bootstrap elements can be done just using flexbox and CSS grids, and knowing bootstrap isn't exactly impressive on a resume. 
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
        - So if we have something like a header or a section, we can apply the column layout to it, like so:
        ```
        <header class="text-center col-12"> </header>
        or
        <section class="text-center col-12"> </section>
        ```

2. #### ***Quick Code***
    - Sometimes our browser has built-in CSS that causes white space / margins around our page. We can remove that in the CSS like so:
        ```
        body {
            margin: auto 0;
        }
        ```
    - For a full responsive background image, you can just get css code from css-tricks
        ```
        html { 
            background: url(images/bg.jpg) no-repeat center center fixed; 
            -webkit-background-size: cover;
            -moz-background-size: cover;
            -o-background-size: cover;
            background-size: cover;
        }
        ```
    - Bootstrap offers an easy-to-copy meta tag to copy for responsiveness. You can grab this off this page: https://getbootstrap.com/docs/5.1/getting-started/introduction/
        ```
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        ```
        - Viewport is the user's visible area on the page. This means that we are telling the browser that this page will be designed for mobile first, and content will expand from there. 
    - Bootstrap offers some quick classes that can easily be added to our HTML instead of having to do it via CSS. For example:
        ```
        So if wanted to change our H1 to all uppercase
        <h1 class="text-uppercase"> Text here </h1>
        ```
        - To look up other bootstrap classes, just do a search here: https://getbootstrap.com/docs/5.1/getting-started/introduction/
        - So if we wanted to add a button style, we searched for buttons and found the class. We would add this to our already-created HTML button tag, with some common sense. Remove the 'type' part they have.
        ```
        <button class="btn btn-primary">Primary</button>
        ```
        - Now we can take this a step further, and custom these quick classes to our liking via css. First we would make them our own custom element. Using the above example: 
        ```
        Add name-here after btn-primary
        <button class="btn btn-primary name-here">Primary</button>
        ```
        - Then we just add the new class to the CSS
        ```
        .name-here {
            padding: 1rem 2rem;
        }
        ```
        - And/or we can specify the general class as an element and alter that
        ```
        .btn {
            font-weight: 700;
        }
        ```
        - If we add to the next one, we can 
        ```
        .btm-primary {
            background-color: #f05F44;
        }
        ```
    - With Bootstrap, we can add h-100 to a class to do 100% height. A good example is using this with a div container to make sure it utilizes the whole page:
        ```
        <div class="container d-flex align-items-center h-100"></div>
        d-flex is activating flexbox via bootstrap
        align-items-center centers via bootstrap
        h-100 makes sure the container height is always 100%
        ```
    - animate.style offers some easy CSS we can plug-and-play with. We can include it in our HTML via this, similar to bootstrap: 
        ```
        <head>
              <link
                rel="stylesheet"
                href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"
                />
        </head>
        ```
        - Once we want to animate something, we can just copy the class from animate.style and insert it:
        ```
        every class starts off with animate__animated
        animate__bounceIn //this was copied from site
        <h1 class="animate__animated animate__bounceIn">H1 text here</h1> //how to insert
        ```
        - their page has easy-to-follow instructions for adding css or infinite animation properties
    - Media Queries are used to specify what is the intended use case of the webpage, and does that change when the page is used at different sizes. Using these can be good to resolve potential issues the site is having rendering things properly.
        ```
        @media only screen //says 'this is intended use case'
        @media only screen and (max-width: 600px) {

        } //says 'use these properties that we are about to define,
        but only when the max width is 600px. As soon as this is less
        than 600px in width, apply the secondary defined properties.

        @media only screen and (max-width: 600px) {
            .custom-element-reference {
                font-size: 0.5em;
                padding: 0;
            }
        }
        //so now when we pull the screen past 600px, it restores
        the original default sizing with our specified font-size
        ```
    - To make a top nav sticky on scroll, we simply need to add a class to the nav, and then do this in the CSS:
        ```
        .sticky {
            position: fixed;
            top: 0;
            width: 100%;
        }
        ```