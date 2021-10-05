
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
    - 
