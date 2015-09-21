# Color Helper
A scss tool to generate bunch of color helper class.

## Installation
Color helper is available via bower :
```
$ bower install color-helper
```

## Usage
Include to your scss stylesheet the `color-helper.scss` file, and just before set a scss variable named $colors with this pattern :

```
$colors: (
    red: #df3949,
    white: #fff,
    black: #000,
)
```

And you are all set ! It will generate class to attribute with those colors for the color, background-color, border-color, fill (opt-in) & stroke (opt-in) attributes on this pattern : `color-{color}`, `background-color-{color}`, `border-color-{color}`, `fill-{color}`, `stroke-{color}`.

### Disable generation
You can disable the generation of class for one the three property supported by resetting to false the following three variables :
* `$color-helper--enable--text-color`
* `$color-helper--enable--background-color`
* `$color-helper--enable--border-color`
* `$color-helper--enable--fill-color`
* `$color-helper--enable--stroke-color`

### Custom class name
You don't like the class name generated ? You can override it by resseting the following variable for each property :
* `$color-helper--selector--background-color` (`'bg-color-'` as default);
* `$color-helper--selector--text-color` (`'color-'` as default);
* `$color-helper--selector--border-color` (`'border-color-'` as default);
* `$color-helper--selector--fill-color` (`'fill-'` as default);
* `$color-helper--selector--stroke-color` (`'stroke-'` as default);


### Responsive classes
You can turn to `true` the opt-in variable `$color-helper--enable--breakpoints` in order to generate responsive classes like `bg-color-{breakpoint}`. Each breakpoint name and min-width value (because we are using a mobile-first scheme) and settable in the following variable (show the default value for the demo):

```
$color-helper--breakpoints: (
    'xs': 0,
    'sm': 768px,
    'md': 992px,
    'lg': 1200px
);
```

### State classes
You can turn to `true` enable color classes to a specific color, property and state (hover, active, focus, visited) with the following variables :
* $color-helper--enable--state-hover
* $color-helper--enable--state-active
* $color-helper--enable--state-focus
* $color-helper--enable--state-visited

You can also custom the class suffix for each state, by redefine each parameter below (with the default value for the example) :
* `$color-helper--selector__suffix--state-hover: '-hover'`
* `$color-helper--selector__suffix--state-active: '-active'`
* `$color-helper--selector__suffix--state-focus: '-focus'`
* `$color-helper--selector__suffix--state-visited: '-visited'`

It is also possible to control on what selector (like &:hover or &.hover) by redefine each parameter below (with the default value for the example) :
* `$color-helper--selector__append--state-hover: '&:hover'`;
* `$color-helper--selector__append--state-active: '&:active'`;
* `$color-helper--selector__append--state-focus: '&:focus'`;
* `$color-helper--selector__append--state-visited: '&:visited'`;

### The pick color utility
`pick-color.scss` is a function NOT INCLUDED in color-helper that could be interesting for your usages. It will just return the value of the color name passed as argument.

```
.pod {
    color: pick-color(red);
}

/* compiles to */
.pod {
    color: #df3949;
}
```

## Using Color Helper with performance
Color Helper can generates a lot of css, and it could be very costly on a performance perspective. In order to fully enjoy color helper without any generated classes unused we recommand the usage of [unscss](https://github.com/giakki/uncss)
