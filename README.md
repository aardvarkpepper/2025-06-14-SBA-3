# SBA 3: Design and Development

![When Bootstrap meets Pixel Perfect meets Good Coding Practices](./tgtbtu.png)

*Image source: [Click to see original Facebook image source](https://www.facebook.com/movieclips/photos/throwback-clip-the-good-the-bad-and-the-ugly-standoff-httpswwwyoutubecomwatchv5p/10153171726572139/?_rdr) , a composite from the movie "The Good, The Bad and the Ugly" 1966 directed by Sergio Leone, further modified using imgflip.*

---

>*Perfect is the enemy of good.* - Voltaire

Obviously Voltaire was a big fan of Bootstrap.

## Overview

>In this assessment, you will take a Figma design from Frontend Mentor and implement it using Bootstrap. This project simulates a real-world task where you receive a design handoff and are expected to create a responsive, pixel-perfect webpage. You will apply your knowledge of Bootstrap’s grid system, components, and utility classes while utilizing version control through Git.

*Deviations from the design, even intentional, will be considered incorrect, and points deducted.*
*Add any custom CSS needed to achieve the required design fidelity.*

[Frontend Mentor Link to Testimonials Grid Section Challenge](https://www.frontendmentor.io/challenges/testimonials-grid-section-Nnw6J7Un7)

>2. Bootstrap Implementation . . . Include Bootstrap components like cards, buttons, navbars, or accordions where appropriate.

[Click to see Bootstrap documentation on cards](https://getbootstrap.com/docs/5.3/components/card/) *We are allowed discretion, and I'm using it.  There are loads of associated Bootstrap classes none of which are well documented, I'm not spending hours going through generated code to change behaviors with SASS, in the process breaking Bootstrap's original functionalities, then hunting down emergent behavior, in the end leaving Bootstrap's original functionality in shambles.  Extensive changes to Bootstrap classes is completely besides the point of Bootstrap supposedly making things fast and simple.*

## Description of Approach

I read through the assignment, noted "pixel perfect" requirement and that we were allowed to use our own CSS.  I then thought about how to approach the problem.

As I understand it, Bootstrap has a lot of predefined code that's useful for fast builds with limited flexibility.  It's useful for, say, webpages that want to fit ever-changing content into familiar formats, where components may change in size, be added or removed, according to some general rules.  This is quite different to building pixel-perfect adaptations of design specifications that were not created with Bootstrap's limitations firmly in mind.

Bootstrap features a limited number of predefined variables that cannot be increased in number, and changed only with some small difficulty.  Measurements are made in increments of fixed values, further restricting flexibility in meeting elaborate design specifications.

As part of Bootstrap's core utility is speed and a framework many developers may be familiar with, I thought spending excessive time on workarounds creating hard-to-read code and breaking a lot of Bootstrap's normal behavior would be quite besides the point.  I did use SASS to effectively redefine some Bootstrap classes, to meet assignment requirements, and I did use Bootsrap's grid system to some limited degree.  For the rest, I just used CSS and Google Fonts.

I first considered structure; what components I would place in what components and so forth.  Even if not strictly necessary for this assignment, building components that could be re-used is pretty standard.  However, the wide frame really didn't allow for free movement of components, and it seemed clear the design was a 'one-off', at least for the wide frame.

With the wide frame, Each card seemed to be fairly filled with pictures and text to the margin, which argues for dynamic design.  But cards were laid out in a complicated pattern, with uniform distances between them, with the cards being different sizes (540x282, 255x282, 255x266, 540x266, 255x572), with text elements looking the same size compared between components (no text resizing or graphics added to cards to fill out space).

[Link to Figma file I used for this assignment.](https://www.figma.com/design/IiEnTAxpMNPVszV11R28VE/SBA-3?node-id=0-1&t=i7L8XBdx3mNSNTln-1)

## Challenges

The biggest issue for me was hunting down bugs, often caused by my bad class naming practices resulting from my insufficient conceptualization.  For example, I would call things "column", when they were "rows", or I would label generic components with "x" or "y" rather than having strict naming conventions.  Had some issue with VSCode autoformat splitting long lines of text into separate lines.  Some organization issues from divs within divs; hunting down typos inclding missed or extra tags entered by accident was a bother.

After realizing VSCode was auto-splitting long lines of text, I briefly looked up how to fix it, but did not find a quick fix I could implement.  As the core functions of the code were not affected, I left VSCode settings alone for expedience, and did a final single HTML edit at the end to reunite split lines of code.

I worked with div soup by using empty lines as break points, and HTML comments to state where specific components ended.

Frontend Mentor did not allow access to Figma file without a paid account.  We were able to download design specifications and assets; I took .jpg files and put in Figma, drew shapes and lines to get pixel sizes etc. (e.g. corner rounding specifications).

Late in the process I thought simple visual comparison inadequate, so took screenshots of website, copied into Figma, and applied 30% opacity to use as an overlay.

I encountered some unexpected behaviors in Bootstrap (e.g. not being able to redefine 'muted' as I'd done with other redefinitions in SASS, and possibly Bootstrap classes taking precedence over classes implemented in CSS, causing an intended display: none element to render.)  These were only minor inconveniences, as I'd implemented then tested features step by step, so I was easily able to get things back to a working point then go from there.

## Reflection

Bootstrap should not be used for pixel-perfect projects, unless those project specifications coincide exactly with Bootstrap's presets.  The assignment explicitly mentioned multiple times the importance of "pixel perfect", so I used SASS enough that it would have been far simpler and easier to ignore Bootstrap and use regular CSS instead.  I did use Bootstrap wherever possible, to meet assignment requirements.

Most challenges I faced during the assignment, I think will be addressed with more experience - better conceptualization of naming practices and element roles.  Absent any major encountered issues, two challenges I thought an issue even if indirectly -

First, I don't know what alternate implementations may be better.  I don't know what I don't know; possibly some action I discounted might have been best, or something I've never heard of.

Second, I think I need to figure out some way of communication with others in the class.  Though I was satisfied with my personal progress, I think others will have questions, which they are reluctant to share.  I think I cannot reasonably be responsible for others' actions or lack of action, but I'll have to keep mindful of ways to encourage reaching out.

I would not make improvements to the work I did on the assignment given more time.  Bootstrap is suited to building quick projects where its limitations are kept firmly in mind, with minimal use of SASS and/or !important.  Building pixel perfect projects with design specifications not created with Bootstrap in mind is, I think, besides the point of using Bootstrap in the first place.

## References

https://getbootstrap.com/docs/5.3/components/card/
https://stackoverflow.com/questions/29820791/git-ignore-node-modules-folder-everywhere

## Customizing Bootstrap with SASS

https://www.freecodecamp.org/news/how-to-customize-bootstrap-with-sass/

Prerequisites:  Node.js with npm or yarn, code editor (using VSCode), understanding SASS.

npm i bootstrap@5.3.6

I did not actually use "npm install -g sass" below, as it should be a global install that I had already performed for Lab 3-3.  I did use it at that time though. 
npm install -g sass

Entered in HTML head

```
<link rel="stylesheet" href="./node_modules/bootstrap/dist/css/bootstrap.min.css">
<link rel="stylesheet" href="customsass.css">
```

Created custom_scss folder in repository folder.
Created custom.scss in custom_scss folder.

Entered in custom.scss
`@import "../node_modules/bootstrap/scss/bootstrap";`

Note import should always be last line.

>Variables are suffixed with a !default (a Sass flag) in Bootstrap. The !default flag tells the compiler to set the value only if the value is not defined.

>So, we set the variables before the @import directive so that, later, the compiler sets our value instead of the default ones.

Set up test HTML code

```
<body>
  <div class="bg-primary">
    Test Default Blue
  </div>
  <div class="bg-secondary">
    Test Default Gray
  </div>
</body>
```

View to verify first div is blue, second div is gray.

Add to beginning of custom.scss file

$primary: teal;
$secondary: red;

In Bash, enter

`sass custom_scss/custom.scss:custom_bootstrap.css`

(Can generate file in subdirectory, using sass custom_scss/custom.scss:subdirectory/custom_bootstrap.css)

Change HTML head from

`<link rel="stylesheet" href="custom.css">`

to

`<link rel="stylesheet" href="custom_bootstrap.css">`

After every edit of custom.scss, above Bash command must be entered.

The HTML file should show blue and gray divs before entering the above Bash command, aqua and red divs afterwards.  If not, debug.

## Processing .jpg Through Figma

I copied provided .jpg files into Figma, then used Shape Tools to draw rectangles to fit each component, with 100% transparency and stroke of different colors to create outlines.  Used corner radius as necessary.

## Processing Figma into Bootstrap

Style guide states widths of 375 and 1440 used, respectively.  Screenshots are provided of 1440x900 and 375x1996.

I think it clear the 375-width view is intended to be vertically scrollable.

For 1440x900 resolution, the cards fit together too neatly to use dynamically sized cards, especially considering there is no obvious rule indicating when lengthy text should break to the next line.  So the five cards will be fixed in size for this resolution.  As the cards are fixed in size and relation to one another, they may be considered collectively as a single element of size 1110x572.

[Click to view webpage on Bootstrap breakpoints.](https://getbootstrap.com/docs/5.0/layout/breakpoints/)

I intend to use default xl 1200px Bootstrap breakpoint to display the fixed element of 1110x572.  All narrower resolutions will use dynamically sized components with top margin of 71px and left/right margin of 24px consistent with displayed design.

## Balancing Assignment Requirements

The assignment states multiple times that pixel perfect is important.  It only states once "Use Bootstrap’s grid system to create a responsive layout that adjusts for different screen sizes."  I do not believe it possible to use a responsive layout using Bootstrap's grid system for the challenge I chose for the assignment.

The problem is the challenge does not feature elements that may be reasonably dynamically sized.  Bootstrap's grid system uses twelve columns, making the minimum fraction 1/12 (0.08333333).  The margin at 1440 width is 165; 165/1440 = 0.11458333, enough to accommodate one column on each side.  However, the margin at 1200 width is only 45; 45/1200 = 0.0375.  The margin at 375 width is 24; 24/375 = 0.064.

Explicitly, Bootstrap's grid system could be used to create a three-column setup, with left and right columns varying in width in one-twelfth increments of screen width (minmum one-twelfth), and the main content taking up the rest of the room depending on screen size.  But any responsive design would not come from use of Bootstrap's grid system, but dynamically resizing the component in the center column using code that has nothing to do with Bootstrap's grid system.

Further, Bootstrap's grid system that uses twelve width increments can't even be usefully used with three or more columns for a lot of wider screen sizes below 1400, as the minimum column size on left and right would make margins wider than specified in the design specs.

I can imagine ways to meet the use Bootstrap's grid system to create a responsive layout that adjusts for different screen sizes, for example integrating Javascript to split single elements into multiple elements, including fractions of geometric shapes, fractions of letters, but that is beyond the scope of the assignment, would take more time than I would care to spend, and would be terrible coding practice.

So I implement a single column using Bootstrap's grid system and use media queries to adjust for different screen sizes.  That is all that can reasonably be done for this particular challenge.

## Oddities

I could not use SASS to overwrite 'muted' to apply to Bootstrap's 'text-muted' class.  'Muted' may reference another color as a baseline.

Using Bootstrap "d-flex flex-row" and commenting out my 'xframewide' references to display: flex; and flex-direction: row; caused the wide frame to be visible in smaller screen sizes.  Though I left the HTML element with the xframewide class, it seems the media query switching .xframewide to display: none may have been invalidated.  Probably has something to do with HTML classes taking precedence over CSS rules, or Bootstrap classes taking precedence, or ordering of stylesheet references in the HTML head.  Regardless, reverted to remove Bootstrap classes.

```
@media (max-width: 1199px) {
  .xframewide {
    display: none;
  }
}
```
Did not implement Bootstrap margin or padding classes in place of px references.  [Follow link to Bootstrap spacing documentation.](https://getbootstrap.com/docs/4.0/utilities/spacing/)  $spacer seems to be linked to rem, which is dependent on the font size of the root element - though set at 16, user preferences may that unit of measurement, which would affect spacer, which would affect margins.  Besides, as often the case in Bootstrap, fixed increments had to be used, and pixel measurements often weren't in accord with those fixed increments.  Rather than elaborate workarounds or inconsistent code, I decided to stick with px measurements.


## Resources

https://www.youtube.com/watch?v=kCvGE9sTj7c
https://convertcolorcode.com/hsla-to-hex