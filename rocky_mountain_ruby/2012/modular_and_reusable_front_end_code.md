# Modular & Reusable Front-end Code

## Roy Tomeij

  - [@roy](http://twitter.com/roy)
  - [http://roytomeij.com](http://roytomeij.com)


## Truth
  
  A web page is a collection of modules


## When Writing Code

  - Each module gets its own scope
  - Class names start with mod-
  - Use generic class names
  - Use shallow selectors
    - Do ```p.note```
    - Do not ```table#box div p.note```

## Nested modules

### fail

    <aside>
      <div class="mod-articles"></div>
    </aside>

    aside.mod-articles
      width: 50%


### win

    <aside>
      <div class="mod-articles narrow"></div>
    </aside>

    .mod-articles
      width: !00%

      &.narrow
        width: 50%


## Media

  .mod-articles
    @media (max-width: 400px)
      background: green


## This is not OOCSS or SMACSS

  Less class names, more element selectors.


## Using ID's in CSS is evil

  - Save your untested styling from breaking
  - Use class names for styling only
  - Use ID's for JS and testing only
  - Data attributes (HTML5), fix the rest


## HTML5 data attributes

    # HTML
    <span data-gender="male" class="father">Bob</span>
    <span data-gender="female" class="mother">Jennifer</span>

    # CSS
    span[data-gender="male"] {
      background: blue;
    }


## Thoughts

  The idea of approaching our back-end code like solid, reusable front-end code is a very interesting concept. The ability to re-use decoupled code across multiple use-cases, expected or not, is extremely effective.


