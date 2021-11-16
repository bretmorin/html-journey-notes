
# HTML Journey Notes
The goal of this section is to record an HTML and CSS cheat-sheet for a future reference guide so I don't have to rely on a mass amount of bookmarks and look-up. 

I'll keep things barebones for my own understanding while providing some reference links if I want to explore other niche areas further. 

# Reference Links
- HTML Cheat Sheet
    - https://htmlcheatsheet.com/
    - https://overapi.com/html
- CSS Cheat Sheet
    - https://htmlcheatsheet.com/css/
    - https://overapi.com/css
    - https://cssreference.io/
    - https://css-tricks.com/almanac/

## Table of Contents
- [HTML Journey Notes](#html-journey-notes)
- [Reference Links](#reference-links)
    - [Table of Contents](#table-of-contents)
    - [Section 1: HTML Basics](#section-1-html-basics)
    - [Section 2: CSS Basics](#section-2-css-basics)
    - [Section 3: Adaptive Sizing](#section-3-adaptive-sizing)
    - [Section 4: Box Model and Page Structure](#section-4-box-model-and-page-structure)
    - [Section 5: Web Components and Layout Patterns](#section-5-web-components-and-layout-patterns)
    - [Section 6: Responsiveness](#section-6-responsiveness)
    - [Section 7: Frameworks](#section-7-frameworks)

### Section 1: HTML Basics
- HTML is creating the structure of the page, and CSS is the design

1. #### ***HTML Boilerplate Page Setup***
    - The homepage should always be named index.html as servers will look for it by default
    - **To trigger the boilerplate code all the below in VScode, just type "!" without the quotes**

    - Boilerplate Setup: 
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
2. #### ***HTML Foundations***
    - Commenting in HTML: 
        ```
        <!-- this is a comment -->
        ```
    - If working within the body element with no other elements inside, it will just output 1 long line of text without proper formatting

    - Elements 
        - In HTML, almost everything is pieces of content wrapped in some sort of container. Almost all elements need an opening and closing tag. 
        - https://developer.mozilla.org/en-US/docs/Web/HTML/Element  
        - Utilize above cheat sheets for more<br/><br/>
        
    - Common elements   
        - Reference cheat sheet links for more   
        - Paragraph: will add a new line after the closing tag
            ```
            <p></p>
            ```
        - Headings: Simply creating a hierarchy
            ```
            <h1></h1> through <h6>
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
        - Navigation in a header is typically done through the nav tag, indicating that many links will be contained inside, typically via an unordered list.
            ```
            <nav></nav>
            then
            <nav>
                <ul>
                </ul>
            </nav>
            ```
        - Strong: makes text bold, but in a way that affects accessibility, as it marks the text as being important in things like screen readers.
            ```
            <strong></strong>
            ```
        - Em: same thing as strong, but for italicized text. Creates an emphasis on a certain text.
            ```
            <em></em>
            ```
            
3. #### ***HTML Links and Images***
    - Creating Links: Utilize the anchor element to create a link
        ```
        <a></a>
        ```
        - We now have to add an attribute to the anchor tag to tell it where to go. An attribute is made of two parts: a name and a value. In this case, we add a Hyperlink reference (href) to tell it where to go
            ```
            <a href="https://www.theodinproject.com/about">click me</a>
            ```
        - By default, anchor tags have a blue color and underline.
            - This is called an Absolute link
        - For Internal, i.e. Relative links, we reference the filename path. If there is another HTML file in the same folder to reference titled 'about.html', it would be:
            ```
            <a href="about.html">About</a>
            ```
        - The same file in a folder called 'Pages' in the same directory would be:
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
        - Common self-closing tags
            ```
            <br> = Line break
            <hr> = Horizontal line added
            ```
        - Differences in image types and when to use them:
            - PNG: Ideal for icons, technical diagrams, logos etc as they utilize colors and opacity better than JPG, but are larger in size.
            - SVG: Vector is ideal for all the same thing as PNG, as they scale without losing quality, making them ideal for responsive design. First choice in those scenarios, but not always available. The only downside is text scaling, which can be solved by converting to outlines using Sketch or Illustrator.
            - JPG: Ideal for photos due to file size scaling, but does not show transparent pixels. 

4. #### ***HTML Forms***
    - Using the form tag:
        - Within the form tags, we have to specify the input type
            ```
            <form>
                (you can put text before the input box here)
                <input type="text">
            </form>
            ```
        - To add a button, just change input type to "submit"
        - To specify the name, you would add a 
            ```
            value="" attribute
            <input type="submit" value="register">
            ```
        - To clean the information in the form, the input type "reset" works
            ```
            <input type="reset">
            ```
        - There are other input type's such as "email" which will check if the information entered is in the email format. "Date" is another popular one.<br/><br/>

    - Other types of input types
        - "Radio" will create clickable buttons
        - "Checkbox" will be selectable boxes
        - "Password" will hide all typed responses
            ```
            Gender <br>
                <input type="radio">Male<br>
                <input type="radio">Female<br>
            ```
        - However, when adding multiple buttons, they will all remain clickable as there is nothing that specifies they are connected. We have to use the "name" attribute to link them.
            ```
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
        - We can add attributes to the select tag, such as "multiple", which allows for multiple selections.<br/><br/>

    - Form submission
        - We have to specify the internal names of the data fields so the query is sent to the back-end in a clean manner. To do this, we just add a name= attribute to every field
            ```
            Last Name <input type="text" name="lastName"><br>
            ```
        - For a "radio"-like input type, we have to add a value as well for specification
            ```
            Gender <br>
            <input type="radio" name="gender" value="male">Male<br>
            <input type="radio" name="gender" value="female">Female<br>
            ```
        - We have to do the same for the <value> tag as well, but this time it's not needed for the input type individually
            ```
            <select name="cars">
            <option value="audi" name="audi">Audi</option>
            <option value="BMW" name="bmw">BMW</option>
            </select>>
            ```

### Section 2: CSS Basics
- Utilizes style.css
- 'Cascading' in CSS (Cascading Style Sheet) means that it will execute commands in order, like a waterfall method, so the last command will override previous requests for potentially the same item. 
    - As a result, it's best practice to add selectors in the stylesheet in the same heirarchy as the HTML - i.e. head selectors coming before body selectors
1. #### ***CSS Fundamentals***
    - Telling the HTML file to look at our CSS file. We want to put this in the header section
        ```
        <link rel="stylesheet" type="text/css" href="style.css">
        ```
        - Type means the media type and rel means relationship to this (html) file. Then in href, put the link to style.css, wherever it lies in the folder. Will have to do this to every HTML page I want to share that particular css file. I can do different styles on different pages by adding a different css file for those pages, and linking appropriately.<br/><br/>
    - Commenting-out:
        ```
        Can use command+/ hotkey, or:
        /* text here */
        ```
    - In essence, we have to identify the 'selector', the 'property, and the value of that property. The code looks like this: Note, these are placeholders
        ```
        selector {              // selector = what is being selected
            property: value;    // property = what to change, and value = how much
        }
        ```
        - So if we wanted to apply a color to a something like an h2 in our code, the same code structure would be:
            ```
            h2 {
                color: red;
            }
            ```
        - We can also add multiple properties within the h2 selector, like 
            ```
            h2 {
                color: red;
                text-align: center;
                border: 5px solid purple;
            }
            ```
    - Good practice to define max width and height, especially if using something like Bootstrap/Tailwind. 
        ```
        body, html {
            width: 100%; //making sure the body and html are max width
            height: 100%;
            font-family: 'Montserrat', sans-serif; 
        }
        ```
    - Sometimes our browser has built-in CSS that causes white space / margins around our page. We can remove that in the CSS like so:
        ```
        body {
            margin: auto 0;
        }
        ```
2. #### ***CSS Selectors***
    - A universal selector which will apply to everything unless something overrides it in the cascade.
        ```
        * {
            property: value;
        }
        ```
        - It is very common to do a 'global reset' with the universal selector to take away default page elements so we can easily customize the page ourself
            ```
            * {
                margin: 0;
                padding: 0;
            }
            ```
    - ID vs Class Selector
        - ID isn't necessary, but is good if we only want to select that one line, as opposed to a Class which will reference the code underneath it, in a hierarchy. 
            - You can also use the Class selector multiple times, whereas ID names can only be used to reference one thing
        - For ID, we would write
            ```
            HTML:
            <p id="author"> </p>

            CSS: uses # instead of .
            # author {
                font-style: italic;
            }
            ```
    - Selectors are powerful as we can create our own elements, in that we can define a section that already might have a CSS element, but there are certain ones that we want excluded from the main CSS properties into their own definition
        - We want to define a class name in the HTML so we can identify our selectors in the CSS file. 
            - For example, adding a name to a paragraph section
                ```
                <p class="custom-name">Lorum Ipsum</p>
                ```
            - Then in the CSS, add a reference to the new selector
                ```
                .custom-name {
                    border: 5px dashed green;
                }
                ```
            - We can add multiple classes to same line as well. So paragraph would be:
                ```
                <p class="class1 class2">
                ```
    - Selectors default to select everything underneath it, as-in child elements. For example:
        ```
        In the HTML:
            <div class="container">
                <h2>some text here</h2>
                    <p>some text here</p>
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
        - Now only the h2 text would have 100% width, not the paragraph text.<br><br>
    - Element within Element says that the selector only applies if Element2 is within Element1.
        - This example will only work if there is a paragraph within a div.
        ```
        div p {
            background-color: yellow;
        }
        ```
    - Hover can be added to an element to give a hover effect
        ```
        p:hover{
            text-align:center;
        }
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
    - Pseudo-Class Selectors
        - Select multiple elements by using a comma. This is often done as the start of the CSS with something like font family, or assigning colors to all headers, and we would later override individual elements as we want
            ```
            h1, p {
                font-color: blue;
            }
            ```
            - If this gets long, it's good pratice to separate selectors by line
            ```
            h1,
            p,
            body {
                font-color: blue;
            }
            ```
        - To select all child elements within another element, we add a space. This example selects all p elements within a footer element
            ```
            footer p {
                font-color: blue;
            }
            ```
            - Just be wary if you have multiple parent elements that meet the same conditions. If that is the case, we can do this with another parent layer
            ```
            article header p {
                font-color: blue;
            }
            ```
        - We can create a condition for our selectors like so
            ```
            li:first-child {
                font-weight: bold;
            }
            ```
            - This says to select the first child of its parent container, in this case the 'li' probably has a parent of 'ul', and only that first child will be bold. 
        - If we wanted to select a middle child element, we would have to do
            ```
            li:nth-child(2){
                font-weight: bold;
            }
            ```
            - In the '()' we would specify which child we want to select, with this '2' being the 2nd. We can also specify 'odd' or 'even'
    - Pseudo-Elements
        - Similar to pseudo classes, these specify things within an element on a micro scale; uses 2 colon's
            ```
            h1::first-letter {
                font-style: italic;
            }
            or
            p::first-line {
                color: red;
            }
            ```
    - When there are multiple declarations for the exact same element, CSS works in a non-cascading hierarchy
        - ID is the highest priority, then class/pseudo-class, then element (p, header, etc)

3. #### ***Text, Fonts, Colors, and Images***
    - Font placement
        - To add a Google Font to our page, we do this:
            1. Get the tag html from google fonts, for ex: 
                ```
                <link href="https://fonts.googleapis.com/css2?family=Roboto:ital,wght@1,100&display=swap" rel="stylesheet"> 
                ```
            2. Add the link tag to the 
                ```
                <head>
                ```
            3. 'font-family' is how we define what font we want to use. Most people use 'sans-serif' as a fallback as everyone has it installed on their computer. Google Fonts will say what to add to our CSS, for ex:
                ```
                font-family: 'Roboto', sans-serif;
                ```
            4. Add the style to whereever we want to use the font in our style.css, defined in HTML via the Google Fonts link
                - If something is using multiple words, you have to use quotation marks around it
                - If doing a custom font, it's always best to have a fallback option. In this example, the fallback is sans-serif
                ```
                body, html {
                    font-family: 'Montserrat', sans-serif; //
                }
                ```
    - Text decoration can highlight an entire section in something like underline
        ```
        p {
            text-decoration: underline;
        }
        or
        p {
            text-decoration: line-through;
        }
        ```
    - Text transform can change the font style to all uppercase and other features 
        ```
        p {
            text-transform: uppercase;
        }
        ```
    - Font Weight we can specify a number or something like bold, and font style can specify things like italic
        ```
        p {
            font-weight: bold;
            font-style: italic;
        }
        ```
    - Line Height will add a multiplier to the line spacing 
        ```
        p {
            line-height: 1.5;
        }
        ```
        - This adds 1.5x the amount of line spacing from the default
        - Good to add this to the body as 1, and then change if needed on specific elements
    - Colors and real-world usage
        - There is Hexadecimal and RGB. Most devs use Hex codes unless transparency is needed. This is how to write both 
            ```
            rgb(red, green, blue)
            color: #hexcode
            ex:
            color: rgb(244, 179, 63);
            color: #00ffff;
            ```
            - RGB Alpha adds transparency 
            ```
            rgba(red, green, blue, transparency value)
            ex: 
            color: rgba(244, 179, 63, 0.7);
            ```
    - Adding border colors
        - We can do this in shorthand by doing just 'border', or we can specify a direction
            ```
            .box {
                border: 5px solid #1098ad;
            }
            or
            .box {
                border-top: 5px solid #1098ad;
            }
            ```
    - Add background colors by using the 'background-color' property
        ```
        .main-header {
            background-color: #f7f7f7;
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
4. #### ***Positioning Tricks***
    - To make a top nav sticky on scroll, we simply need to add a class to the nav, and then do this in the CSS:
        ```
        .sticky {
            position: fixed;
            top: 0;
            width: 100%;
        }
        ```
### Section 3: Adaptive Sizing
1. #### ***Sizing Relevance***
    - We utilize more adaptive sizing rather than by pixels and percentages, as these tend to break when working with multiple screen sizes
        - It's good practice to specify the document HTML font-size initially so we can reference it through adaptive sizing later
            ```
            html {
                font-size: 100%; //or 16px/1em
            }
            ```
            - The % is good for accessibility as the user might have already increased their font
    - REM (root EM)
        - This is the multiplier of the font size of the browser, meaning it looks at the 'root' of the size of the overall HTML element as a reference point, and is a multiple or fraction of that
            ```
            .customrem h1 {
                font-size: 2.5rem;
            }

            .customrem p {
                font-size: 1rem;
            }
            ```
        - This would be 2x the browser's font size. 
    - EM
        - This is in-relation-to (parent to child) the above element
        - This is typically used only for elements within elements, where we might want some more size control, vs larger page elements like margin on divs, etc, where REM would be better used
        - For example, the below means that the paragraph is 2.5x less than the h1
            ```
            .customem h1 {
                font-size: 2.5em;
            }

            .customem p {
                font-size: 1em; //typically 16px = 1em
            }
            ```
        - This also says that everything compounds ontop of each other, so it can get out of hand if we keep adding 'em' in the same div. REM's solves the compounding issue we can face <br><br>
    
    - For responsive height/width sizing, vh (viewport height) or vw is a best-practice sizing method
        - So for having an element always be 50% of viewport height:
            ```
            .custom-element {
                height: 50vh 
            }
            ```

### Section 4: Box Model and Page Structure
1. #### ***Box Model***
    - **CSS box model structure**: https://www.w3schools.com/css/css_boxmodel.asp
        - Use 'inspect' browser dev tools to look at box model to better understand the layout<br><br>
    - The site should be broken up into sections by using Div's in the HTML
        - By doing this, we can easily align all elements within these containers and throughout the page, as opposed to trying to align 50 individual elements
        - Divs within divs is common when structuring a site, as it allows you to add margin between elements within a bigger div
        - We assign a div anywhere in the body, but we should assign a custom class so we can link it to the CSS
            ```
            <div class="custom-class">
            </div>
            ```
        - Then in the CSS, reference the class like a new selector
            ```
            .custom-class {
                border: 5px red;
            }
            ```
        - It's best practice to encapulate all page content in one overarching div to easily manage page margins
            ```
            <div class="container">
                <body>
            </div>

            .container {
                width: 700px;
                margin-left: auto;
                margin-right: auto;
            }
            ```
    - Padding is the space on the inside of the div element border, whereas Margin is on the ouside of the div.
        - Padding and Margin goes clockwise starting at the top
            ```
            padding: 5px 3px 3px 5px;
            padding: top right bottom left;
            ```
        - Or we can just do padding for all 4 sides with just 1 number
            ```
            padding: 5px;
            ```
        - Or, we can to top/bottom and left/right like so:
            ```
            padding: 5px 5px;
            padding: top/bottom left/right;
            ```
    - The page 'normal flow' will be in the order of the box structure, but we can specify different elements to break away from that normal flow to be 'out of flow' and exist as if there are no boxes.
        ```
        button {
            position: absolute;
        }
        ```
        - You can add padding, make it left:0 or right:0, etc
        - The problem with this is that it will position itself based on the viewport which will cause responsiveness issues, so it should be based on a parent element on the page 
        ```
        body {
            position: relative;
        }
        ```
        - For the button, we would have to make its parent of 'body' as a relative position so the element will always be positioned based on where it is on the page, instead of the viewport
            - If we added it under a different container, it would be restricted by that container's dimensions

2. #### ***Display Types***
    - Most elements will default to 
        ```
        display: block
        ```
        - This means that block elements will appear on the page stacked atop of each other. Each new element will start on a new line 
        - For example, a simple paragraph in HTML is a block. Add a border to see what it looks like
        - By default they have a width of 100%. This could be limited by the parent element
            - Even if you put width at 50%, the blocks will still stack vertically.
        - We then utilize div's with Flexbox and/or CSS Grid to add responsive elements and horizontal+vertical layouts 
    - If we want to ever hide a section, we can do the following code within our container, instead of trying to comment everything out
        ```
        .container {
            display: none;
        }
        ```
3. #### ***Flexbox***
    - Reference Guides:
        - https://darekkay.com/flexbox-cheatsheet/
        - http://flexboxgrid.com/
        - https://css-tricks.com/understanding-flex-grow-flex-shrink-and-flex-basis/
        - https://css-tricks.com/the-thought-process-behind-a-flexbox-layout/
    - To activate flexbox in an element, we utilize this inside a container of some sort (any element with child elements)
        ```
        .container {
            display: flex;
        }
        or
        .div 2 {
            display: flex;
        }
        ```
        - This assumed .container is part of a div, so we are saying that everything inside that div - i.e. the children / flex items - are activated for flexbox now
        - In Flexbox, the 'main axis' is horizontal, and the 'cross axis' is vertical
        - The easiest way to align items with flexbox, is by creating a div around the elements you want, and assigning it as a flex display
    - Different properties are generally assigned to the container vs the flex items themselves
        - Flex Container
            - Justify Content on the main axis
                - To center items horizontally, we would do
                ```
                justify-content: center;
                ```
                - This property can be used in other easy ways like this, which adds the same margin between horizontal items
                    ```
                    justify-content: space-between
                    ```
                - Other key properties:
                    ```
                    justify-content: flex-start;
                    justify-content: flex-end;
                    justify-content: space-around;
                    justify-content: space-evenly;
                    ```
            - Align items on the cross axis
                - By default, all flex items are horizontally as wide as to fit the content inside, like so
                ```
                align-items: stretch; //default value
                ```
                - However, they are all the same vertical size as their tallest item, assuming one of them specifies the height
                - If we do something like
                    ```
                    align-items: center;
                    ```
                    - The container will still take the height of the tallest item, but all other items will only be as tall as their content, and will be centered in the container vertically
                - Other key properties:
                    ```
                    align-items: flex-start;
                    align-items: flex-end;
                    align-items: baseline;
                    ```
            - To create space between the flex items without having to use margin for every item, we can use gap
                ```
                gap: 0;
                ```
            - Flex Wrap will wrap images into a new line if they are too large
                ```
                flex-wrap: wrap;
                flex-wrap: nowrap;
                ```
            - Flex Direction will define which is the main axis
                ```
                flex-direction: row;
                flex-direction: column;
                ```
        - Flex Items
            - Align Self can override the align-items property for individual flex items
                ```
                align-self: auto;
                align-self: stretch;
                etc...same as align-items, applied to one flex item
                ```
            - The Flex property consists of 3 flex definitions. The easiest way to think of this is as 'Max, Min, Ideal sizes'
                - Flex Grow will determine if elements are allowed to grow as large as they can to fill the container, or not
                    ```
                    flex-grow: 0; //default value
                    flex-grow: 1; //fills remaining space
                    ```
                    - If we set it to higher than a value of 1, then the flex item will be multiplied by the availability of empty space it takes over the other flex items
                    ```
                    flex-grow: 2; //double the empty space amount vs other flex items
                    ```
                - Flex Shrink tells the browser if it's allowed to shrink flex items to fit the container, or not
                    ```
                    flex-shrink: 1; //default value, will shrink
                    ```
                - Flex Basis is used to assign width to items within the container as a target size (recommendation), and the browser will figure out the optimal length to fit the items to the container, evenly.
                    - So if the content is bigger than what we assign in Basis, then the content's size takes priority. If the content is smaller than what we put as Basis, then the target size will be hit
                    ```
                    flex-basis: auto; //default value
                    ```
                    - 'Auto' says that the content size is the ideal size
                - Thus the Flex property defaults to:
                    ```
                    flex: 0 1 auto; //defaults
                    /grow /shrink /basis
                    ```
                    - By setting flex to 1, we are saying to change flex grow to 1 and keep the other properties default
                    ```
                    flex: 1;
                    or we could reference all values
                    flex: 1 1 auto;
                    ```
4. #### ***CSS Grid***
    - Reference Guides:
        - https://grid.malven.co/
        - https://css-tricks.com/snippets/css/complete-guide-grid/
        - https://learncssgrid.com/#grid-container
    - Most devs use CSS Grid in conjunction with Flexbox, opting for Grid when they have multiple grid items that need to be responsive, and opting for Flexbox when they have a single row or column by design
        - The only downside to using CSS Grid is it doesn't have the same browser compatability as Flexbox, though it's still good
    - Just like Flexbox, we have a grid container, and grid items, as opposed to flex container and items
        - We also want to activate it within our container with
            ```
            .container {
                display: grid;
            }
            ```
    - Grid Container Properties
        - Now we have to define our 2-dimensional layout - i.e. columns and rows
            - To define width values, we use
                ```
                .container {
                    grid-template-columns: 100px 100px;
                }
                ```
                - The following will generate 2 columns, because we put 2 numbers
                - It will also make those columns with the width of 100px each, because those are the values we assigned
                - Thus this will define how many rows we get, as we now have a min width amount, and all content will go underneath
            - If we've never defined our height anywhere, then the height of each grid item would simply be the height of the content of the tallest grid item
                - This means we can define the individual height of a grid item by just doing so within the grid item class, and that height won't change when we define the grid column height
                - To define the column height, it's the same process
                    ```
                    .container {
                        grid-template-rows: 100px 100px;
                    }
                    ```
        - Grid relies on the Gap property and doesn't use margins
            ```
            gap: 50px;
            ```
            - This will create a gap between both columns and rows
            - We can define separate gaps between the columns and rows, something that flexbox cannot do
                ```
                .container {
                    display: grid;
                    column-gap: 30px;
                    row-gap: 20px;
                }
                ```
        - Just like in flexbox, we use justify and align to adjust the rows and columns
            - To align items inside rows and columns (horizontally/vertically)
                ```
                justify-items: stretch; //horizontal
                align-items: center; //vertical
                ```
                - Also has: 'start', 'end'
            - To align entire grid inside grid container. This only applies if the container is larger than the grid
                ```
                justify-content: start;
                align-content: center;
                ```
                - Also has: 'end', etc...
    - Grid Items Properties
        - To place a grid item into a specific cell based on line numbers, which are always listed in the inspect element grid lines area
            ```
            grid-column: <start line> / <end line>;
            grid-row: <start line> / <end line>;
            ```
        - To overwrite justify-items / align-items for single items
            ```
            justify-self: stretch;
            align-self: start;
            ```
            - Also has: 'center', 'end'
    - Grid Item Sizing
        - The problem with using px sizing is that it sets a hard size on grid items, and that means items can overflow a container if that size is breached
        - CSS Grid offers its own responsive sizing usage: fraction - as-in a fraction of the total grid size
            - 1 fr will only result in 1 column filling the remaining space, while 1fr 1fr will give 2 50% columns filling the remaining space (of the grid)
                ```
                grid-template-columns: 1fr 1fr;
                ```
            - In this example, the 3fr would result in half the grid spacing. This is because 3 + 1 + 1 + 1 = 6, and 3 being 1/2 of 6
                ```
                grid-template-columns: 3fr 1fr 1fr 1fr;
                ```
            - By adding 'auto' for a column, it will only fill the remaining grid space that is required to allow the content to be filled properly
                ```
                grid-template-columns: 3fr 1fr 1fr auto;
                ```
        - Shorthand for the above uses the 'repeat' function
            - The first number is the amount of columns, and the 2nd number is how large they should be
                ```
                grid-template-columns: repeat(4, 1fr);
                ```
        - Rows have height defined by the tallest content, or if we previously defined the height either for the entire container or one element. This means that 1fr would be that tallest height
        - You can specify different elements to be in specific grid columns or rows
            - When you inspect the page, click on the 'grid' button in the html and you'll see the grid layout which makes it easier to count
                ```
                .random-item-in-grid {
                    grid-column: 2/4;
                }
                ```
                - This would move the .random item to between the 2nd and 4th grid columns
                ```
                .random-item-in-grid {
                    grid-row: 1/2;
                }
                ```
                - This would move the .random item between the 1st and 2nd row
            - This can also be done without having to specify the exact column, and rather just using the span command to have the grid cell 'span' a specific amount of cells
                ```
                .random-item-in-grid {
                    grid-column: 1, span 3;
                }
                ```
                - If we simply want an item to expand all the way to the end without thinking about it, we can just use -1
                ```
                .random-item-in-grid {
                    grid-column: 1, -1;
                }
                ```
    - Grid movement of items within a container
        - This can be done the same way as flexbox, where we use justify and align to move the grouping of items, along the container tracks, within a container
            ```
            .container {
                display: grid;
                justify-content: center;
            }
            ```
            - This will move all items horizontally within that container to the center of the container
                - Other properties like 'space-between', 'start', 'end' work just like in flexbox
            ```
            .container {
                display: grid;
                align-content: center;
            }
            ```
            - This will align the grid items vertically within the container. Can also use the same properties as justify
    - Aligning the grid items inside the grid container cells
        - By using 'align-items' we can move items vertically inside the grid cell
            ```
            .container {
                display: grid;
                align-items: center;
            }
            ```
            - Or if we want to align horizontally
            ```
            .container {
                display: grid;
                justify-items: center;
            }
            ```
        - To override these settings on an individual item, we use align-self to a specific item
            ```
            .specific-item {
                align-self: end;
                justify-self: end;
            }
            ```
### Section 5: Web Components and Layout Patterns
1. #### ***Website Building Process***
    - There are 4 stages that websites are typically built
        1. Started by building elements first, like paragraphs, images, buttons, which will contain our actual content
        2. Then we assemble these elements into common components like a card, pricing table, etc
        3. Then we take all the components we designed, and use them to build a layout using common layout patterns
        4. Finally, we take all our minor layouts and assemble a final webpage
    - The most common elements, components, section components, and layout patterns
        - Visual examples included Here: **put link here**
        - Common Elements
            - Text
            - Buttons
            - Images
            - Input Elements
            - Tags
        - Common Components
            - Breadcrumbs
            - Pagination
            - Alert and status bars
            - Statistics
            - Gallery
            - Feature Box
            - Preview and profile cards
            - Accordion
            - Tabs
            - Carousel
            - Customer testimonials
            - Customer logos
            - Featured-in logos
            - Steps
            - Forms
            - Tables
            - Pricing Tables
            - Modal windows
        - Common Section Components
            - Navigation
            - Hero Section
            - Footer
            - CTA section
            - Feature row
        - Common Layout Patterns
            - Row of cards/boxes
            - Grid of cards/boxes
            - Z-pattern
            - F-pattern
            - Single-column
            - Sidebar
            - Multi-column/magazine
            - Asymmetry/Experimental
2. #### ***Accordion Component***
    - This will construct an accordion component, however without the ability to open items unless we add javascript later
    - Start by building a separate HTML doc; something like 01-accordion.html
    - It's easiest to just add CSS style elements within the 1 small HTML page, so just add a style tag and put design elements inside
        ```
        <style>
        </style>
        ```
    - Add some general styles wanted for the font, box sizing, etc
        ```
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
        font-family: sans-serif;
        color: #343a40;
        }
        ```
    - Then create a div class in the body
    - Next add width and margin to the new div class. As an example: 
        ```
        .accordion {
           width: 700px;
           margin: 100px auto; 
           background-color: grey;
        }
        ```
    - Within that div, we need to create a new div that contains all items, current and future
        ```
        <div class="accordion">
            <div class="item">
            </div>
        </div>
        ```
    - Next add a paragraph class, or two, if you want a numbering system next to the text
        ```
        <div class="accordion">
            <p class="number">
                02
            </p>
            <p class="test">
                How long do I have to return my chair?
            </p>
        </div>
        ```
    - Get an icon for opening the accordion, like chevron-down, and copy svg, and paste it within the div after the paragraphs
        - Change the class name for easier reference, if needed
    - Then add a new div class for the text that will show once the box is opened on click. This should be within the original div and after the icon paste. For example:
        ```
        <div class="hidden-box">
            <p>
                Lorem ipsum 
            </p>
        </div>
        ```
    - We now have to add visual styles. Using the above example:
        ```
        .icon {
            width: 24px; /* references icon suggested size*/
            height: 24px;/* references icon suggested size*/
            stroke: #087;
        }

        .number, .text {
            font-size: 24px;
            font-weight: bold;
            color: #087;
            margin-bottom: 24px;
            line-height: 1.6;
        }
        ```
    - As everything is in a horizontal, predictable layout, using flexbox is the easiest option. Apply this to the .item class
        ```
        display: flex;
        flex-direction: column;
        ```
        - One note is that when switching flexbox direction to be column, all directional properties are reversed; align-items will be vertical instead of horizontal, for example









### Section 6: Responsiveness
1. #### ***Responsive Setup***
    - The first thing we need to do is include this line of code in the head element
        ```
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        ```
        - This makes it so the page will match the screen's width when on smaller devices like Phones, as opposed to the normal behavior of zooming-out of the page to fit it on the screen
2. #### ***Media Queries***
    - Many devs like to group these in their own file, like 'queries.css'
        - Make sure to link it in the HTML
    - The best way to determine optimal breakpoints is to determine when the design breaks. So when testing and going through all device screen sizes, if the design breaks when browsing, for example, on the new iPhone, we can set a breakpoint there
        - Breakpoints were typically determined based on the grouping of screen size categories. For example, all phones are under 600px, all vertical tablets under 900px, all horizontal tablets under 1200px, and all desktops are bigger
    - These are used to define breakpoints on screen size so we can define elements, for example
        - This asks if the current viewport width is equal or smaller than 600px:
            ```
            @media (max-width: 600px)
            ```
            - If it is, then all the code that applies to this media query applies
        - If there are 2 media queries like so:
            ```
            @media (max-width: 600px)
            @media (max-width: 1200px)
            ```
            - And the user's phone size is 400px, then they are both valid. But the smaller number - 600px - will take precedence
    - We would add css elements under the @media definition like so:
        ```
        @media (max-width: 1200px) {
            .section-hero {
                background-color: red;
            }
        }
        ```
3. #### ***Misc Responsiveness***
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
### Section 7: Frameworks
1. #### ***Bootstrap***
    - The purpose of using things like Bootstrap is that modules of code are already built-out and you can search their database of what you are looking for
        - We don't even have to download the files if we don't want to. We can add their CDN (Content Delivery Network) css/js href link in our header. 
    - Any element definitions we make within our stylesheet will override bootstrap items
        - So if we define a bootstrap button like
            ```
            btn-danger
            in the style.css 
            
            as

            .btn-danger {
                background-color: orange;
            }
            ```
        - It will override the bootstrap button color of red.
    - Bootstrap's power comes from the responsiveness of its grid system 
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
            ```
            - Whereas the numbers next to the size are the width size out of the total of the 12 columns that bootstrap uses. 
        - So if we have something like a header or a section, we can apply the column layout to it, like so:
            ```
            <header class="text-center col-12"> </header>
            or
            <section class="text-center col-12"> </section>
            ```
    - Bootstrap offers an easy-to-copy meta tag to copy for responsiveness. You can grab this off this page: https://getbootstrap.com/docs/5.1/getting-started/introduction/
        ```
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        ```
        - Viewport is the user's visible area on the page. This means that we are telling the browser that this page will be designed for mobile first, and content will expand from there. 
    - Bootstrap offers some quick classes that can easily be added to our HTML instead of having to do it via CSS 
        - To look up other bootstrap classes, just do a search here: https://getbootstrap.com/docs/5.1/getting-started/introduction/
        - So if wanted to change our H1 to all uppercase
            ```
            <h1 class="text-uppercase"> Text here </h1>
            ```
        - So if we wanted to add a button style, we searched for buttons and found the class. We would add this to our already-created HTML button tag. Remove the 'type' part they have.
            ```
            <button class="btn btn-primary">Primary</button>
            ```
        - Now we can take this a step further, and customize these quick classes to our liking via css. First we would make them our own custom element. Using the above example: 
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
2. #### ***Tailwind***