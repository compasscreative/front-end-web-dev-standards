# Front-end web dev standards

As a marketing/brand agency, typical Compass websites tend to be  fairly simple in regards to information architecture. Although adhering to consistent typography and grids, our sites are  artfully designed. If you intend to use a robust CSS framework, you may end up with excess overhead. Please assess the visual design first, then consider the best framework suited for the project.

For a CMS agnostic example, see our [Platypus Boilerplate](https://github.com/jeremydouglas/base-sass). This is the system that we use in-house as our starting point for web projects.

## Code Spacing
- Use 4 spaces for indentation, not tabs.
- Group blocks of code with a full line return between each block.

## URL formatting 
- Page urls should use hyphens for spaces
- urls should end with no file extensions or trailing slash

## CSS
When if comes to CSS guidelines, we think Mr. Harry Roberts nailed it with his [CSS Guidelines](http://cssguidelin.es). Even if you are familiar with this document, please take a moment to review and freshen up on the details.

### Highlights we feel that are important:
- Do not style based on an ID, only style based on classes.
- In blocks, do not style based on a selector, only style based on classes.
- Keep specificity as low as possible. With BEM, we can keep this to one!
- Make reusable blocks where it makes sense.

### BEM
- Although more verbose, With BEM, we are able to easily see a separation of blocks and which pieces are tied to that block.
- Our syntax is based off of BEM, specifically the [CSS Wizardry implementation](http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/).
- Double underscore (__) for an element 
- Double dash (--) for a modifier.


### Example code SCSS

    
    .block-name {
        colour: blue;

        // media queries are typically best grouped 
        // with the element they refer to.
        @media only screen and (min-width: 768px) {
            colour: yellow;
        }

        &--modifier-name {
            color: red;
        }

        &__element-name {
            // Position properties (sorted alphabetically)
            clear: both;
            position: relative;
            top: 10px;
    
            // Box properties (sorted alphabetically)
            height: 500px;
            margin: 0 10px 5px 2px;
            padding: 5%;
    
            // Decoration properties (sorted alphabetically)
            background: #000;
            colour: black;
            font-family: Arial;
        }
    }
   

### Grid frameworks
If you would like to use an external grid framework, feel free to add it, but keep html tags separated from the BEM tag structure. For instance:

```
<div class="row columns-12">
    <div class="column span-4 offset-1">
        <aside class="sidebar">
            <h2 class="sidebar__heading"></h2>
            <p class="sidebar__paragraph"></p>
        </aside>
    </div>
    <div class="column span-4">
        <article class="blog-article">
            <h2></h2>
            <p></p>
        </article>
    </div>
    <div class="column span-2">
        <div class="callout-ad">
            <h2 class="callout-ad__title"></h2>
            <a href="" class="callout-ad__button"></a>
        </div>
    </div>
</div>
```

In the above, we can see a separate grid structure that can be targeted separately from the content blocks.

### Additional technology
- Use [SASS](http://sass-lang.com/) as a pre-processor, with scss syntax.
- Vendor prefixing is done with [autoprefixer](https://github.com/ai/autoprefixer).
- Use [gulp](http://gulpjs.com) for task running.


## HTML

We adhere by the [Google HTML/CSS Style Guide](https://google.github.io/styleguide/htmlcssguide.xml) 

In particular, we’d like to highlight these points:

- Use the correct doctype: <!doctype html>
- Use lower case attribute names
- Indent by 4 spaces at a time. (This differs from Google, but adheres to [PSR-2](http://www.php-fig.org/psr/psr-2/) standards.)

## Microformats
Use standard [microformats](http://microformats.org/wiki/examples) where possible.

## Social
Be sure to check what images a Facebook share or a Pinterest pin pulls in.

## Javascript
Our sites are typically fairly light on javascript. When javascript is needed, please follow the guidelines of the framework you’re using and conventions laid out in the above HTML/CSS guidelines.
