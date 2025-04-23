# Frontend Mentor - Ricky's Social links Profile Solution

This is a solution to the [Social links profile challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/social-links-profile-UG32l9m6dQ). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview
I used <a href="https://www.w3schools.com/" target="_blank">W3Schools Resources</a> and a course on Udemy by <a href="https://www.udemy.com/user/4b4368a3-b5c8-4529-aa65-2056ec31f37e/" target="_blank">Dr. Angela Yu, Developer and Lead Instructor</a> as my resources. I did complete this project by myself (i.e., all placements, HTML, and designs), however, I should have left corrections after submitting, since Frontend Mentor gives you the opportunity to improve your design. 

All that said, I took my time playing around with the containers and the body, inputting the flex-box, margins and height to see what worked for me.

At first I was just inputting it but didn't necessarily know exactly what it was doing or why. This back and forth, lead me to finally understand how to correctly make the spacing for the mobile design, and how it corresponds to the rest of the design. I then realized I needed to hover the links and make sure the anchors sent you to the website, this took me down another rabbit hole in making the list items and anchors work together. It took me from 9am-noon to finally figure out the adjusments. I've not only learnt how to correctly add spacing, combined the 'li' and 'a' tags, but also how easy it is to use the 'transition' animation CSS rule. This project was definitely a breakthrough for me, super motivated. 

### The challenge

Users should be able to:

- See hover and focus states for all interactive elements on the page

### Screenshot

<img src="./Desktop Social Links Design.png"/>
<img src="./Mobile Social Links Design.png"/>



## My process

HTML:
I began the design by adding the correct tags to the content. Then proceeded to add the selectors right after. 

For the socila links, I went with a unordered list with 5 list items. There was not particular reason for in why I chose this method, but I was considering adding buttons instead. 

I then followed up with adding the anchors within the list items so you could be able to go to the websites. 

CSS: 

My process this time around started with targeting the universal selector adding 0 for margin adn padding, finishing with a box-sizing: border-box for better responsivness. I've always overlooked this but I realize now that this is critical for repsonsive design. 

I then went to the body and set the background-color, font, and added the overflow:hidden again in regard to the .attribution section.

Created the .profile-container for center alignment using flex-box

I then began designing the .profile-card and fixing it sizing, and aligning everything with flex-direction: column.  

I followed up with the correct sizing of the image for better placement within the .profile-card

I then group the image, and .london inside a .header class in order to better adjust the margin-bottom for space inbetween the paragraph below it.

I then started adding all the font-weight, font-size and colors to all the tags that needed it. 

I finished off the design with designing the list and removing the bullets. Then followed with editing the anchors (which caused me to really figure out why it wasn't working; more on this in the #what-i-learned section)

Finally, edited the .attribution class by adding a media queries so it can become a column once it hits a width of 375px for the mobile design. 



### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Desktop-first workflow

### What I learned

What I've learnt so far was how to:

- Correctly add margin spacing to your code. In return, it helped me achieve a responsive design when sizing down to 375px. 
This was relief once I figured it out, since it lead me to find out why my design wasn't responsive. This was the incorrect version of my code:

body {
    background-color: hsl(0, 0%, 8%);
    color: hsl(0, 0%, 100%);
    font-family: 'Inter', sans-serif;
    overflow: hidden;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}

/*Missing a container for .profile-card. This made the design not correctly read the margin: 0 1em within my .profile-card.*/

.profile-card {
    background-color: hsl(0, 0%, 12%);
    width: 400px;
    display: flex;
    flex-direction: column;
    text-align: center;
    padding: 30px 30px;
    border-radius: 8px;
    margin: 0 1em;
}

I then updated it by adding a .profile-container around the 
.profile-card and moving the height, display:flex, and putting the margin: 0 1em within the .profile-container:

body {
    background-color: hsl(0, 0%, 8%);
    color: hsl(0, 0%, 100%);
    font-family: 'Inter', sans-serif;
    overflow: hidden;
}

.profile-container {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0 1em;
}

.profile-card {
    background-color: hsl(0, 0%, 12%);
    width: 400px;
    display: flex;
    flex-direction: column;
    text-align: center;
    padding: 30px 30px;
    border-radius: 8px;
}
This correction helped me achieve the margin spacing I was looking for, and also, when sizing the window down to a width of 375px, it was showing better responsive fluidity. 


The next thing I learned was: 

- how to combined the list item with the anchor tag. It was more difficult than I anticipated but I figured it out: 

So without the anchor tag, the list items were easy to code, and a hover rule was quickly executed, however, the challenge started when I inputted the anchor tags within the list items.
This lead to a problem, everytime I hovered over the li tag, the words weren't changing to the color black because it wasn't within the content of the anchor, nor did it show the click finger icon due to the same reason:


li {
    list-style-type: none;
    background-color: hsl(0, 0%, 20%);
    color: hsl(0, 0%, 100%);
    margin: 20px 0;
    padding: 20px;
    border-radius: 8px;
}

li a {
    text-decoration: none;
    color: hsl(0, 0%, 100%);
    display: block;
}

li:hover {
    background-color: hsl(64, 96%, 57%);
    color:hsl(0, 0%, 0%);
}

li a:hover {
    color: hsl(0, 0%, 0%); /*I had this as li:hover a which was not targeting the anchor tag, causing more challenges for me*/
}

To fix this I first was planning to display the anchors as block elements to take up space but it was to diffcult to positioned them in the center. So I ended up adding a Flex-box within the li selector in order to center the anchors, and then made the anchors width and height to 100% and add the same padding as the li of 20px, to take up the whole space. I was getting a 40px padding for the list items, making it bigger than what I needed.So all I had to do was remove the 20px padding fromm the li selector, the anchor had a padding of 20px covering the whole space. This eneded up working great!:

li {
    list-style-type: none;
    background-color: hsl(0, 0%, 20%);
    color: hsl(0, 0%, 100%);
    margin: 20px 0;
    border-radius: 8px;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: background-color 0.3s;
}

li a {
    border: 1px solid black;
    text-decoration: none;
    color: hsl(0, 0%, 100%);
    width: 100%;
    height: 100%;
    padding: 20px;
}

li:hover {
    background-color: hsl(64, 96%, 57%);
}

li:hover a {
    color: hsl(0, 0%, 0%);



### Continued development

I'll continue to focus on these types of projects and creating my own designs. That way I can continue practicing all I have learnt so far. 

### Useful resources

<a href="https://www.w3schools.com/" target="_blank">W3Schools Resources</a>
<a href="https://www.udemy.com/user/4b4368a3-b5c8-4529-aa65-2056ec31f37e/" target="_blank">Dr. Angela Yu, Developer and Lead Instructor</a>

## Author

- Website - <a href="https://rarroyoharo.com" target="_blank">rarroyoharo.com</a>
- Frontend Mentor - <a href="https://www.frontendmentor.io/profile/RiickyRiick" target="_blank">@RiickyRiick</a>


## Acknowledgments

<a href="https://www.w3schools.com/" target="_blank">W3Schools Resources</a>
<a href="https://www.udemy.com/user/4b4368a3-b5c8-4529-aa65-2056ec31f37e/" target="_blank">Dr. Angela Yu, Developer and Lead Instructor</a