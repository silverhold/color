# Color Helper
A scss tool to generate bunch of color helper class.

## Usage
Include to your scss stylesheet the `color-helper.scss` file, and just before set a scss variable named $colors with this pattern :

```
$colors: (
    red: #df3949,
    white: #fff,
    black: #000,
)
```

And you are all set ! It will generate class to attribute with those colors for the color, background-color and border-color attributes on this pattern : `color-{color}`, `background-color-{color}`, `border-color-{color}`.

### Disable generation
You can disable the generation of class for one the three property supported by resetting to false the following three variables :
* `$color-helper--enable--text-color`
* `$color-helper--enable--background-color`
* `$color-helper--enable--border-color`

### Custom class name
You don't like the class name generated ? You can override it by resseting the following variable for each property :
* `$color-helper--selector--background-color` (`'bg-color-'` as default);
* `$color-helper--selector--text-color` (`'color-'` as default);
* `$color-helper--selector--border-color` (`'border-color-'` as default);


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
