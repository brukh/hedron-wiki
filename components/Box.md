## Box Component

The `<Box />` component contains elements inside of your flex container (`<Container />`).

### Box Props

| Property Name | Type               | Description                                                  | Default |
|--------------:|:-------------------|:-------------------------------------------------------------|:--------|
|        noFlex | `Bool`             | Sets `display` property to `block` if true                   | `false` |
|          flex | `String`           | Sets shorthand `flex` property on container                  | `null`  |
|          grow | `Bool` or `String` | Sets `flex-grow` property to `1` if true or the string value | `null`  |
|         fluid | `Bool`             | Removes padding from container                               | `false` |
|            xs | `String`           | Width during `xs` breakpoint.                                | `null`  |
|            sm | `String`           | Width during `sm` breakpoint.                                | `null`  |
|            md | `String`           | Width during `md` breakpoint.                                | `null`  |
|            lg | `String`           | Width during `lg` breakpoint.                                | `null`  |
|       xsShift | `String`           | Width of left margin during `xs` breakpoint.                 | `null`  |
|       smShift | `String`           | Width of left margin during `sm` breakpoint.                 | `null`  |
|       mdShift | `String`           | Width of left margin during `md` breakpoint.                 | `null`  |
|       lgShift | `String`           | Width of left margin during `lg` breakpoint.                 | `null`  |
