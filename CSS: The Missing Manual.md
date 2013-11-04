## CSS Basic

- tag selectors

    `p`

- class selectors

    `.special`

- ID selectors

    `#banner`

- group selectors

    `h1, p, .copyright, #banner`

- the universal selector

    `*`

- descendent selectors 

    + `li a`    (means all `a` elements inside `li`)
    + `ul li a` (descendent selectors can contain more than 2 elements)
    + `.intro a`
    + `p.intro a`

- pseudo-classes and pseudo-elements

    + pseudo-classes for links

        * `a:link`
        * `a:visited`
        * `a:hover`
        * `a:active`

    + pseudo-elements

        * `:first-letter`
        * `:first-line`
        * `:before`
        * `:after`
        * `:first-child` (NOTE: the syntax is `CHILD:first-child`)

        * `:hover`
        * `:focus`

    + more pseudo-classes

        * `:hover`
        * `:focus`

- child elements

    `body > h1`

- adjacent sibling

    `h2 + p`

- attribute selectors

    + `img[title]`
    + `input[type="text"]`
    + `a[href^="http://"]`    ("`^=`" means "begins with")
    + `a[href$=".pdf"]`       ("`$=`" means "ends with")
    + `img[src\*="headshot"]`  ("`*=`" means "contains")

- inheritance (following are properties being inherited)

    + text-related properties

        * `font-family`
        * `font-size`
        * `font-style`
        * `font-variant`
        * `font-weight`
        * `font`
        * `letter-spacing`
        * `line-height`
        * `text-align`
        * `text-indent`
        * `text-transform`
        * `word-spacing`

    + list-related properties

        * `list-style-image`
        * `list-style-position`
        * `llis-style-type`
        * `list-style`

    + the `color` property

- style cascading

    + same property from multiple ancestors

        * inherited styles accumulate
        * nearest ancestor wins
        * the directly appiled style wins

    + one tag, many styles

        * specificity (inherited properties don't have any specificity)

            - a tag selector 1 point
            - a class selector 10 points
            - an ID selector 100 points
            - an inline style 1000 points
            - a pseudo-element 1 point
            - a pseudo-class 10 points

        * last style wins

        * !important overrules specificity


## Applied CSS

- benefit of using line-height: 1.5 instead of line-height: 150%

    as the line-height property can be inherited, when using 150%, the calculated value is inherited, while in the former case, all the descendant tags simply multuplies their font size by 1.5.

- IE6 bugs and fixes:

    + using overflow: hidden to prevent backgrounds and borders from awkwardly running under floating elements will fail in IE6

        fix: add 'zoom: 1' to the css

- CSS shorthand properties