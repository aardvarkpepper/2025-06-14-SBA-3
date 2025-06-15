# SBA 3: Design and Development

![When Bootstrap meets Pixel Perfect meets Good Coding Practices](./tgtbtu.png)

*Image source: [Facebook](https://www.facebook.com/movieclips/photos/throwback-clip-the-good-the-bad-and-the-ugly-standoff-httpswwwyoutubecomwatchv5p/10153171726572139/?_rdr) , a composite from the movie "The Good, The Bad and the Ugly" 1966 directed by Sergio Leone, modified using imgflip.*

>*Perfect is the enemy of good.* - Voltaire

Obviously Voltaire was a big fan of Bootstrap.

## Overview

>In this assessment, you will take a Figma design from Frontend Mentor and implement it using Bootstrap. This project simulates a real-world task where you receive a design handoff and are expected to create a responsive, pixel-perfect webpage. You will apply your knowledge of Bootstrap’s grid system, components, and utility classes while utilizing version control through Git.

[Frontend Mentor Link to Testimonials Grid Section Challenge](https://www.frontendmentor.io/challenges/testimonials-grid-section-Nnw6J7Un7)

The assignment states pixel-perfect so generic Bootstrap clearly does not suit.  We are instructed to use components "where appropriate".

>2. Bootstrap Implementation
>. . .
>Include Bootstrap components like cards, buttons, navbars, or accordions where appropriate.

[Bootstrap documentation on cards](https://getbootstrap.com/docs/5.3/components/card/) does not state specifically what each card class changes.  This is fine and expected for Bootstrap's expected use case of building fast but limited websites, but no good for this assignment use case of "pixel perfect".  *Therefore, using the component is not appropriate.*

Among other Bootstrap/pixel perfect/good coding practice conflicts that may be expected, detailed in later sections, a pro account was required to download Figma files off Frontend Mentor.  We could download other files; I moved some of them into Figma and worked with them to get pixel sizes.

## Reflection

Bootstrap should not be used for pixel-perfect projects, unless those project specifications coincide exactly with Bootstrap's presets.  The assignment explicitly mentioned multiple times the importance of "pixel perfect", so I used SASS enough that it would have been far simpler and easier to ignore Bootstrap and use regular CSS instead.  I did use Bootstrap wherever possible, to meet assignment requirements.

I would not make "improvements" given more time.  Bootstrap is suited to building quick projects where its limitations are kept firmly in mind, with minimal use of SASS and/or !important.  Building pixel perfect projects with design specifications not created with Bootstrap in mind is entirely besides the point of using Bootstrap in the first place.

## References

https://getbootstrap.com/docs/5.3/components/card/
https://stackoverflow.com/questions/29820791/git-ignore-node-modules-folder-everywhere

## Bash Commands

npm i bootstrap@5.3.6

I did not actually use "npm install -g sass" below, as it should be a global install that I had already performed for Lab 3-3.
npm install -g sass

sass scss/custom.scss:FirstChallenge/customsass.css