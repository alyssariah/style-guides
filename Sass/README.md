# Sass Guide

## Table of Contents

1. [Class Naming](#class-naming)
2. [Type Selectors](#type-selectors)
3. [ID Selectors](#id-selectors)
4. [Shorthand Properties](#shorthand-properties)
5. [0 and Units](#0-and-units)
6. [Leading 0s](#leading-0s)
7. [Important Declarations](#important-declarations)
8.  [Block Content Indentation](#block-content-indentation)
9.  [Declaration Stops](#declaration-stops)
10. [Declaration Block Separation](#declaration-block-separation)
11. [Selector and Declaration Separation](#selector-and-declaration-separation)
12. [Rule Separation](#rule-separation)
13. [CSS Quotation Marks](#css-quotation-marks)
14. [Comments](#comments)
15. [Property Declarations](#property-declarations)
16. [@include declarations](#@include-declarations)
17. [Nested selectors](#nested-selectors)
18. [Variables](#variables)
19. [Mixins](#mixins)
20. [Lists](#lists)

# CSS

## Class Naming

- Separate words in class names by a hyphen such as `page-contact`
  
- Storybook components conain the prefix `sb-` before the rest of class name

- `--` in class names are for variants such as `sb-button` can have the variant `sb-button--small`

- `__` in class are for child sections within a class such as `form` can have a child cass `form__title`

- Use class names that are as short as possible but as long as necessary.
  
- Try to convey what a class is about while being as brief as possible.
  
- Using class names this way contributes to acceptable levels of understandability and code efficiency.

        .nav {}
        .author {}

- Use meaningful or generic class names.

- Instead of presentational or cryptic names, always use class names that reflect the purpose of the element in question, or that are otherwise generic.

- Names that are specific and reflect the purpose of the element should be preferred as these are most understandable and the least likely to change.

- Generic names are simply a fallback for elements that have no particular or no meaning different from their siblings. They are typically needed as “helpers.”
  
- Using functional or generic names reduces the probability of unnecessary document or template changes.  

[Back to top](#table-of-contents)

## Type Selectors

- Avoid qualifying class names with type selectors.

- Unless necessary (for example with helper classes), do not use element names in conjunction with classes.

- Avoiding unnecessary ancestor selectors is useful for performance reasons.
  
        /* Not recommended */
        ul.example {}
        div.error {}

[Back to top](#table-of-contents)

## ID Selectors

- Avoid ID selectors.

- ID attributes are expected to be unique across an entire page, which is difficult to guarantee when a page contains many components worked on by many different engineers. Class selectors should be preferred in all situations.
  
        /* Not recommended */
        #example {}

        /* Recommended */
        .example {}

[Back to top](#table-of-contents)

## Shorthand Properties

- Use shorthand properties where possible.

- CSS offers a variety of shorthand properties (like font) that should be used whenever possible, even in cases where only one value is explicitly set.

- Using shorthand properties is useful for code efficiency and understandability.

        border-top: 0;
        font: 100%/1.6 palatino, georgia, serif;
        padding: 0 1em 2em;****

[Back to top](#table-of-contents)

## 0 and Units 

- Omit unit specification after “0” values, unless required.

- Do not use units after 0 values unless they are required.

- When dealing with lengths, a 0 value should never ever have a unit.

        margin: 0;
        padding: 0;

[Back to top](#table-of-contents)

## Leading 0s 

- Always include leading “0”s in values.

- Put 0s in front of values or lengths between -1 and 1.

- Never display trailing zeros

        font-size: 0.8em;

[Back to top](#table-of-contents)

## Important Declarations

- Avoid using !important declarations.

- These declarations break the natural cascade of CSS and make it difficult to reason about and compose styles. Use selector specificity to override properties instead.

[Back to top](#table-of-contents)

## Block Content Indentation

- Indent all block content with 2 spaces.

- Indent all block content, that is rules within rules as well as declarations, so to reflect hierarchy and improve understanding.

        @media screen, projection {

            html {
                background: #fff;
                color: #444;
            }

        }

[Back to top](#table-of-contents)

## Declaration Stops

- Use a semicolon after every declaration.

- End every declaration with a semicolon for consistency and extensibility reasons.

- When using multiple selectors in a rule declaration, give each selector its own line.

        .test {
            display: block;
            height: 100px;
        }

[Back to top](#table-of-contents)

## Declaration Block Separation

- Use a space between the last selector and the declaration block.

- Always use a single space between the last selector and the opening brace {} that begins the declaration block.

- The opening brace should be on the same line as the last selector in a given rule.

- Put closing braces } of rule declarations on a new line.

- Put blank lines between rule declarations.

        .video {
            margin-top: 1em;
        }

        .avatar {
            border-radius: 50%;
            border: 2px solid white;
        }

[Back to top](#table-of-contents)

## Selector and Declaration Separation 

- Separate selectors and declarations by new lines.

- Always start a new line for each selector and declaration.

        /* Not recommended */
        a:focus, a:active {
            position: relative; top: 1px;
        }

        /* Recommended */
        h1,
        h2,
        h3 {
            font-weight: normal;
            line-height: 1.2;
        }

[Back to top](#table-of-contents)

## Rule Separation

- Separate rules by new lines.

- Always put a blank line (two line breaks) between rules.

        html {
            background: #fff;
        }

        body {
            margin: auto;
            width: 50%;
        }

[Back to top](#table-of-contents)

## CSS Quotation Marks

- Use single (' ') rather than double (" ") quotation marks for attribute selectors and property values.

        html {
            font-family: 'open sans', arial, sans-serif;
        }

[Back to top](#table-of-contents)

## Comments

- Prefer line comments (// in Sass-land) to block comments.

- Prefer comments on their own line. Avoid end-of-line comments.

- Write detailed comments for code that isn't self-documenting:
  
    - Uses of z-index

    - Compatibility or browser-specific hacks

[Back to top](#table-of-contents) 

## Property Declarations

- Use the .scss syntax, never the original .sass syntax

        .btn-green {
            background: green;
            font-weight: bold;
            // ...
        }

[Back to top](#table-of-contents)

## @include declarations 

- Order your regular CSS and @include declarations logically

- Grouping @includes at the end makes it easier to read the entire selector.
  
        .btn-green {
            background: green;
            font-weight: bold;
            @include transition(background 0.5s ease);
            // ...
        }

[Back to top](#table-of-contents)

## Nested selectors 

- Nested selectors, if necessary, go last, and nothing goes after them. Add whitespace between your rule declarations and nested selectors, as well as between adjacent nested selectors. Apply the same guidelines as above to your nested selectors.

        .btn {
            background: green;
            font-weight: bold;
            @include transition(background 0.5s ease);

          .icon {
                margin-right: 10px;
          }
        }

- Do not nest selectors more than three levels deep!

        .page-container {
            .content {
                .profile {
                // STOP!
                }
            }
        }
  
- When selectors become this long, you're likely writing CSS that is:
  
    - Strongly coupled to the HTML (fragile) —OR—
  
    - Overly specific (powerful) —OR—

    - Not reusable

- Never nest ID selectors!
  
[Back to top](#table-of-contents)

## Variables 

- Prefer dash-cased variable names (e.g. $my-variable) over camelCased or snake_cased variable names. It is acceptable to prefix variable names that are intended to be used only within the same file with an underscore (e.g. $_my-variable).
  
[Back to top](#table-of-contents)

## Mixins 

- Mixins should be used to DRY up your code, add clarity, or abstract complexity--in much the same way as well-named functions. Mixins that accept no arguments can be useful for this, but note that if you are not compressing your payload (e.g. gzip), this may contribute to unnecessary code duplication in the resulting styles.

[Back to top](#table-of-contents)

## Lists

- either inlined or multilines; 
  
- necessarily on multilines if too long to fit on an 80-character line;
  
- unless used as is for CSS purposes, always comma separated;
  
- always wrapped in parenthesis;
  
- trailing comma if multilines, not if inlined.
  
[Back to top](#table-of-contents)