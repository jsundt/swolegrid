# swolegrid
A simple grid system for browsers that lift.
Use with autoprefixer.


# basics html grid

```html
<section class="gym gym--primary"><!-- optional padding and background colour -->
  <div class="max-reps"><!-- container to set max widths -->
    <div class="get-swole"><!-- display flex -->
      <div class="bench"></div><!-- flex item -->
      <div class="bench bench-lg-first"></div><!-- flex item ordered first on lg size and up -->
      <div class="bench"></div><!-- flex item -->
    </div>
  </div>
</section>
```





# breakpoints and utility classes
swole grid generates classes based on your grid breakpoints, here's the defaults:

```scss
$grid-breakpoints: (
  xs: 0,      // Extra small screen / phone
  sm: 34em,   // Small screen / phone
  md: 48em,   // Medium screen / tablet
  lg: 62em,   // Large screen / desktop
  xl: 75em    // Extra large screen / wide desktop
) !default;
```

For breakpoint this is created:
```scss
.bench-#{$break}-first, .item-#{$break}-first { order: -1; }
.bench-#{$break}-reset, .item-#{$break}-reset { order: 0; }
.bench-#{$break}-last, .item-#{$break}-last   { order: 1; }

.guns-#{$break}, .horizontal-#{$break}    { flex-direction: row; }
.leg-day-#{$break}, .vertical-#{$break}   { flex-direction: column; }

.guns-#{$break}-start, .justify-#{$break}-start   { justify-content: flex-start; }
.guns-#{$break}-center, .justify-#{$break}-center { justify-content: center; }
.guns-#{$break}-end, .justify-#{$break}-end       { justify-content: flex-end; }

.swole-#{$break}-top, .row-#{$break}-top        { align-items: flex-start; }
.swole-#{$break}-center, .row-#{$break}-center  { align-items: center; }
.swole-#{$break}-stretch, .row-#{$break}-stretch{ align-items: stretch; }
.swole-#{$break}-bottom, .row-#{$break}-bottom  { align-items: flex-end; }

.bench-#{$break}-top, .item-#{$break}-top        { align-self: flex-start; }
.bench-#{$break}-center, .item-#{$break}-center  { align-self: center; }
.bench-#{$break}-stretch, .item-#{$break}-stretch{ align-self: stretch; height: auto !important; }
.bench-#{$break}-bottom, .item-#{$break}-bottom  { align-self: flex-end; }
```