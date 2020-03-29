# breakpoint-sass-mixins
Media query breakpoint mixins for Sass.

## Variables
There are already predefined breakpoints in pixels. If necessary, you can of course use your own breakpoints here, even in a different unit such as REM
```scss
$breakpoints: (
  small: 0,
  medium: 480px,
  large: 1024px,
  ultra: 1200px,
) !default;
```

## Mixins
There are two mixins to write media queries with either `min-width` or `max-width`.
```scss
.container {
    width: 500px;

    @include breakpoint-up(medium) {
        width: 800px;
    }

    @include breakpoint-down(large) {
        border: solid 1px green;
    }    
}
```

## Functions
There are also helper functions to find out whether it is the first or last breakpoint. These must be handled separately, as a media query may not make sense. For example, you do not need a media query for `min-width > 0`
```scss
@debug is-last-breakpoint("ultra"); // true
@debug is-first-breakpoint("small"); // true
@debug get-next-breakpoint("small"); // medium
```

---
Made with &#10084; in Bielefeld
