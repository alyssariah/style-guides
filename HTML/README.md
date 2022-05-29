# HTML Guide

## Table of Contents

1. [General Formatting](#general-formatting)
2. [HTML Line Wrapping](#html-line-wrapping)
3. [HTML Quotation Marks](#html-quotation-marks)
4. [Semantics](#semantics)
5. [Multmedia Fallback](#multimedia-fallback)
6. [Attributes](#attributes)

## General Formatting

- Use new line for every block. list, or table element, and indent every such child element

        <blockquote>
            <p><em>Space</em>, the final frontier.</p>
        </blockquote>

## HTML Line Wrapping

- Break long lines over a print width of 180 characters for readability. 
  
- Each attribubte should be put on a new line when wrapping HTML.

        <md-progress-circular 
          md-mode="indeterminate"
          class="md-accent"
          ng-show="ctrl.loading"
          md-diameter="35">
        </md-progress-circular>

## HTML Quotation Marks

- Use double (" ") rather than single quotation marks (' ') around attribute values.
  
        <a class="maia-button maia-button-secondary">Sign in</a>


## Semantics

- Use HTML according to its purpose

## Multimedia Fallback  

- Provide alternative contents for mulimedia with alt tag

        <img src="spreadsheet.png" alt="Spreadsheet screenshot.">

## Attributes 

- Omit type attributes for style sheets and scripts.
  
- Do not use type attributes for style sheets (unless not using CSS) and scripts (unless not using JavaScript).
  
- Specifying type attributes in these contexts is not necessary as HTML5 implies text/css and text/javascript as defaults. This can be safely done even for older browsers.

        <link rel="stylesheet" href="https://www.google.com/css/maia.css">
        <script src="https://www.google.com/js/gweb/analytics/autotrack.js"></script>
