
# HTML Journey Notes
The goal of this section is to record an HTML and CSS cheat-sheet for a future reference guide so I don't have to rely on a mass amount of bookmarks. 

I'll keep things barebones for my own understanding while providing some reference links if I want to explore other niche areas further. 

## Table of Contents
- [HTML Journey Notes](#html-journey-notes)
    - [Table of Contents](#table-of-contents)
        - [Learning Process](#learning-process)
    - [Section 1: HTML Basics](#section-1-html-basics)
    - [Section 2: ](#)

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
    - In the page header, we will put metadata that is not viewable to the user
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
    - Lists:
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
    -   Utilize the anchor element to create a link
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
    - Images
