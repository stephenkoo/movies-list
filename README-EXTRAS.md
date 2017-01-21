### Folder Structure

#### React folders
This project is organized based on [Mangin’s React structure](https://medium.com/@alexmngn/how-to-better-organize-your-react-applications-2fd3ea1920f1).

- Components: Isolatable, functionally-independent blocks of UI
- Pages: Technically also components, but related to setting up generic page elements. Usually known as ‘scenes’.
- Services: Non-UI functions used by components or pages.
- Data: Bridge between the server API and the client.

#### Style folders
This project uses a hybrid of [CSS modules](https://css-tricks.com/css-modules-part-1-need/) for high-specificity styles and [ITCSS](https://www.xfive.co/blog/itcss-scalable-maintainable-css-architecture/) for low-specifity styles.

ITCSS layers of increasing specificity:

0. Settings: Global settings (e.g. font, colors palettes, config switches). Used by preprocessors. No CSS output.
1. Tools: Globally used mixins and functions. No CSS output.
2. Generic: CSS resets, normalize.css, global box-sizing rules, etc.
3. Elements: Styling bare HTML elements (e.g. `H1`, `A`)
4. Objects: Class-based selectors which define non-cosmetic design patterns (e.g. OOCSS media object, `.wrapper`, `.inner`, `.container`)
5. Components:

Styles with higher specificity are implemented as CSS modules.

### Resources
These resources helped shape this project.

- [Awesome README: A curated list of awesome README](https://github.com/matiassingers/awesome-readme) (github.com)
- [How to better organize your React applications?](https://medium.com/@alexmngn/how-to-better-organize-your-react-applications-2fd3ea1920f1) (medium.com)
- [Manage large CSS projects with ITCSS](http://www.creativebloq.com/web-design/manage-large-css-projects-itcss-101517528) (creativebloq.com)
- [Intro to ITCSS for Web Developers](http://www.hongkiat.com/blog/inverted-triangle-css-web-development/) (hongkiat.com)
- [Managing CSS Projects with ITCSS](http://csswizardry.net/talks/2014/11/itcss-dafed.pdf) (csswizardry.net)
- [How I Shrank my CSS by 84kb by Refactoring with ITCSS](https://medium.com/@jordankoschei/how-i-shrank-my-css-by-84kb-by-refactoring-with-itcss-2e8dafee123a) (medium.com)
- [ITCSS: Scalable and Maintainable CSS Architecture](https://www.xfive.co/blog/itcss-scalable-maintainable-css-architecture/) (xfive.co)

### Potential features

- Temporary floating notification when movie is added, or removed.
- Multiple lists of movies
- Floating information page for movies
- Mobile responsive views

### Some thoughts about the project code

- Aware of rigorously turning common HTML elements into components. Purpose is to maintain well-defined, consistent universal styling without duplicate CSS elements. For instance, the container component may in the future assign class to elements like panels, callout boxes, wells, and structural elements like `main`, `section`, `article`, `header`, `footer`, `nav`, and `aside`.
- Aware of the rather unconventional use of text components to assign styling to elements like `p`, `H1`. This is something I picked up working on a project where the brand has a predefined set of text styles (much like a colour palette), but use them differently depending on context. A `p` tag may require the use of `h3` styling in some circumstances. I believe that this is a great way of thinking about text styling. Just as colour palettes shouldn't be prescribed to certain HTML elements to allow for greater flexibility and context-dependent design, neither should text types.
- I like Mangin’s clear division of components, pages, services & data. I hope to build upon this structure in future projects.
- Although I see the benefits of organizing CSS using ITCSS, I feel that the names of these layers aren’t as expressive as other naming conventions and the distinctions between certain layers may be too granular. However, the benefits of ITCSS may be more apparent in large-scale applications.
