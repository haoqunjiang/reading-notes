- benefit of using line-height: 1.5 instead of line-height: 150%

    as the line-height property can be inherited, when using 150%, the calculated value is inherited, while in the former case, all the descendant tags simply multuplies their font size by 1.5.

- IE6 bugs and fixes:

    + using overflow: hidden to prevent backgrounds and borders from awkwardly running under floating elements will fail in IE6

        fix: add 'zoom: 1' to the css

- CSS shorthand properties