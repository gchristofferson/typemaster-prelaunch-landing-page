# Frontend Mentor - Typemaster pre-launch landing page solution

This is a solution to the [Typemaster pre-launch landing page challenge on Frontend Mentor](). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Frontend Mentor - Typemaster pre-launch landing page solution](#frontend-mentor---typemaster-pre-launch-landing-page-solution)
- [Table of contents](#table-of-contents)
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

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover states for interactive elements

### Screenshot

![](./assets/shared/screenshot.jpg)


### Links

- Solution URL: [https://github.com/gchristofferson/typemaster-prelaunch-landing-page](https://github.com/gchristofferson/typemaster-prelaunch-landing-page)
- Live Site URL: [https://gchristofferson.github.io/typemaster-prelaunch-landing-page/](https://gchristofferson.github.io/typemaster-prelaunch-landing-page/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- BEM methodology


### What I learned

This was my first 'Junior' level challenge that I decided to tackle.  The scope of the project was much larger than the individual component layouts I had previously done. However, I learned that when working on a larger project, it's very important to work in a modular way, finishing one section before moving to the next.  This naturally helps to make code and components that are reusable, which is especially important for a multi-page site or larger application.  

There are also a few elements, properties and methods that I used in this project that I hadn't used before or at least not as extensively:
- `overflow: hidden` and `overflow-x: hidden` to ensure there was no side scrolling for images placed outside the screen area, like the shape in the upper-right corner and lower-left corner of the main info section on the desktop layout, as well as the hero image on the mobile and tablet layouts.
- `<picture>` element along with the nested `<source>` elements for responsive images and for optimal performance
- Git's branch and merge features to experiment with different methods and layouts

The most exciting of these for me was the `<picture>` element for responsive images.  I had never used this before and I had often worked on image heavy projects where this could have saved a lot unnecessary media queries and bandwidth.  Here's how I marked up the hero image using this element:

```html
<picture class="hero__img-wrapper">
  <source class="hero__img" srcset="assets/desktop/image-keyboard.jpg" media="(min-width: 1200px)">
  <source class="hero__img" srcset="assets/tablet/image-keyboard.jpg" media="(min-width: 535px)">
  <img src="./assets/mobile/image-keyboard.jpg" alt="keyboard" class="hero__img">
</picture>
```
What I learned about using this tag, is that you want the `<img>` tag to use your default image, which would be the mobile image if using a mobile-first approach.  Then, for the images to load properly at the right breakpoints, I had to stack 2 `<source>` tags on top of the `<img>` tag in the order of priority, tablet being 2nd, in the middle and the desktop image being 3rd on the top.  The way the `<picture>` element works is by looking first at your media attribute of the first `<source>` tag and if it doesn't apply it will then go to the next and will continue until a rule applies. If none apply then the browser will download the default image.  It will also use the alt text of the `<img>` tag across all sources and will only download the image that is needed.  If a user is browsing from a mobile phone, the browser will not download the tablet and desktop images, thus saving bandwidth and speeding up site performance.


### Continued development

I really would like to refine my use of the `overflow` property.  I struggled a bit at first with this layout because of the offset images that extend beyond the screen, but `overflow` came to the rescue.  I also want to see how I can possibly make my code more 'DRY' (Don't repeat yourself).  I feel like I probably wrote too much CSS and I could probably refactor it and make it more concise.  Lastly, I found the `<picture>` element to be very useful and will continue using it going forward, especially on image heavy or larger projects.

### Useful resources

- [MDN Web Docs: overflow-x](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x) - This article really helped me to understand that if I need to use `overflow: hidden` on the body, I better use `overflow-x: hidden` instead, otherwise the user won't be able to scroll down the page! 
- [MDM Web Docs: <picture>: The Picture element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture) - This is a great article for anyone who wants to learn how to use the picture element in there projects.  It includes examples and explanations of the necessary `<source>` element and it's attributes needed to get this to work.
- [Git Branching - Basic Branching and Merging](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging) - This article helped me see how I can use Git branching and merging to do some experimenting without worrying about messing up my master branch and how I can merge the changes to my master branch if I like them.  

## Author

- Frontend Mentor - [@gchristofferson](https://www.frontendmentor.io/profile/gchristofferson)
- Twitter - [@GreggChristoff2](https://twitter.com/GreggChristoff2)

## Acknowledgments

I want to give a big thank you to [@sweenejp](https://www.frontendmentor.io/profile/sweenejp) for helping me clear up my doubts about using `overflow: hidden`.  Turns out I didn't even need it on the flex containers that had fixed widths and flex-wrap set to nowrap.  That did the trick. I still needed to use it on the grid container though, but now I understand when to use it and when it's not needed thanks to [@sweenejp](https://www.frontendmentor.io/profile/sweenejp)!

I also want to tip my hat to [@grace-snow](https://www.frontendmentor.io/profile/grace-snow) who gave me some awesome tips to improve the structure and accessibility of my document.  Some changes I implemented from her suggestions included changing my font-sizes from pixels to rems, using aria-labelledby instead of aria-label on the sections, moving my features section to live inside main element, adding overflow-x: hidden to the body and fixint the alt text of the logo.


