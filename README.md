
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
    - [Section 5: Responsiveness](#section-5-responsiveness)
    - [Section 6: Frameworks](#section-6-frameworks)

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
    - How to make a universal selector which will apply to everything unless something overrides it in the cascade.
        ```
        * {
            property: value;
        }
        ```
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
3. #### ***Text, Fonts, and Images***
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
            3. Google Fonts will say what to add to our CSS, for ex:
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
    - font weight we can specify a number or something like bold
        ```
        p {
            font-weight: bold;
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

### Section 3: Adaptive Sizing
1. #### ***Sizing***
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

2. #### ***Display Types***
    - Most elements will default to 
        ```
        display: block
        ```
        - This means that block elements will appear on the page stacked atop of each other. Each new element will start on a new line 
        - For example, a simple paragraph in HTML is a block. Add a border to see what it looks like
        - By default they have a width of 100%. This could be limited by the parent element
            - Even if you put width at 50%, the blocks will still stack vertically.
        - We then utilize div's with Flexbox and/or CSS Grid to add responsive elements and horizontal+vertical layouts <br><br>

3. #### ***Flexbox***
    - To activate flexbox in an element, we utilize this inside a container of some sort, or to a nested item
        ```
        .container {
            display: flex;
        }
        or
        .div 2 {
            display: flex;
        }
        ```
        - This assumed .container is part of a div, so we are saying that everything inside that div is part of flexbox. <br><br>
    - We then can add different properties to the flexbox, such as:
        ```
        .container {
            display: flex;
            flex-wrap: wrap; //wraps images for a responsive design
            justify-content: center; //centers all content responsively
        }
        ``` 
    - Flexbox Properties:
        - The 'Flex' property is shorthand for flex-grow, flex-shrink, and flex-basis
            - The easiest way to think of this is: max, min, ideal sizes
            - Some help: 
                - https://darekkay.com/flexbox-cheatsheet/
                - http://flexboxgrid.com/
                - https://css-tricks.com/understanding-flex-grow-flex-shrink-and-flex-basis/
                - https://css-tricks.com/the-thought-process-behind-a-flexbox-layout/
        - flex default values are:
            ```
            div {
                flex: 0 1 auto; //grow, shrink, basis
            }
            ```
            ```
            div {
                flex: 1;
            }

            This actually means 
            
            div {
                flex: 1 1 auto;
            }
            ```
        - Flex Grow: how much the applied property would grow based on a comparison container 
            - For example if we did 'flex: 2' to a div inside our container, we are saying that div should be 2x the size of the other div's
            in that container.
                ```
                .flex-container .two {
                    flex: 2 1 auto;
                }
                ```
        - Flex Shrink: determines how much the flex item will shrink relative to the rest of the flex items in the flex container when there isn’t enough space on the row 
            - Setting 'flex-shrink: 0;' would make the item never shrink
            - Using the above example, if our 3 divs from above had a width declaration like: 
                ```
                width: 100px 

                .flex container .two {
                    width
                }
                and .flex-container was smaller than 300px, our divs would have to shrink to fit. 
                ```
        - Flex Basis: sets the initial size of a flex item so any growing or shrinking will start from that baseline size. <br><br>

4. #### ***CSS Grid***
    - Difference between CSS Grid and Flexbox is that Grid can use horizontal and vertical simultaneously, while flexbox is one or the other based on div alignment
        - Firstly, flexbox has more browser compatability
        - So if I have multiple div's in subsequent rows that have content in each other, it would be prudent to use flexbox to align the content inside those div's. 
            - However, those rows may need alignment in relation to the content that is within those div's. This is where CSS Grid shines.
            - CSS Grid also can do things like purposley overlap content
    - Some help:
        - https://grid.malven.co/
        - https://css-tricks.com/snippets/css/complete-guide-grid/
        - https://learncssgrid.com/#grid-container
    - Once we determine CSS grid is the way to go, we need to create a container and put everything in there
        ```
        <div class="container"></div>

        .container {

        }
        ```
    - We then have to add CSS to our container, similar to flexbox, and change the display type. We also need to add grid-template-columns to tell the page how many columns we want to use
        - this will act as 2 grids because there is 2 numbers
            ```
            .container {
                display: grid;
                grid-template-columns: 300px 300px; 
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
    - CSS Grid offers its own responsive sizing usage: fraction - as-in a fraction of the total page size
        -  1 fr will only result in 1 column, while 1 fr 1fr will give 2 50% columns
            ```
            grid-template-columns: 1fr 1fr;
            ```
        - There is a shortcut for fractions with the repeat property
            - This will repeat 1fr, 3 times
            ```
            grid-template-columns: repeat(3, 1fr);
            ```
        - There is another way to do this with the auto property
            - This will auto resize(scale) to fit the content
            ```
            grid-template-columns: auto 1fr 2fr;
            ```
        - Now perhaps the best way to do this for responsiveness is to do:
            ```
            grid-template-columns: repeat(auto-fill, minmax());
            ```
            - Inside the minmax we want to define
                1. the minimum size wanted
                2. the maximum size wanted of each item. This means the container itself will auto adjust in size based on the viewport to keep that item the specified size. Meaning: 
                ```
                grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
                ```
                - This will be minimum 300px. As soon as it goes above 300px in viewport, it expands the grid and keeps each item at 300px
        
    - CSS grid also allows us to define rows as well; not just columns
        - If using fr for sizing, it will compare the other rows
            ```
            grid-template-rows: 1fr 2fr
            ```
            - This will result in the 2nd row being twice as big as the first
            - If there are more than 2 rows in this example, the 1fr will keep repeating after the 2fr
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
        - The problem with this is that it removes responsiveness because it makes sure the specified size matches what we told it to do. To help with responsiveness, we can add a '-1' that means it will go all-the-way to the end of the viewport.
            ```
            .element-item-here{
                grid-column: 1/-1;
            }
            ```

### Section 5: Responsiveness
1. #### ***Responsiveness Learning***
    - Links:
        - 
        - 
        - 
2. #### ***Misc Responsiveness***
    - To make a top nav sticky on scroll, we simply need to add a class to the nav, and then do this in the CSS:
        ```
        .sticky {
            position: fixed;
            top: 0;
            width: 100%;
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
3. #### ***Media Queries***
    - More help: 
        - https://css-tricks.com/a-complete-guide-to-css-media-queries/
        - https://www.w3schools.com/css/css_rwd_mediaqueries.asp
        - https://www.w3schools.com/css/css3_mediaqueries_ex.asp
    - These typically target certain viewport ranges in order to apply custom styles for responsive design, or they detect system preferences and make adaptations based on those, ex: light and dark settings


### Section 6: Frameworks
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