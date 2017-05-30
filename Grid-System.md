## Break Points

Hedron comes with 3 built-in break points. These are the break-points that I've found to be most useful in responsive website design.

Hedron is built mobile-first, which means that all styles that should be displayed on a mobile device are placed outside of all media queries. Whenever I refer to the `xs` breakpoint, I'm referring to the default break-point that comes before all media queries.

``` jsx
{
  sm: 500,
  md: 768,
  lg: 1100,
}
```

These can be customized using the [`<LayoutProvider>`](https://github.com/JSBros/hedron/wiki/BreakPoints) component.

## Grid Components Overview

The hedron grid system includes three main layout components, `<Section />`, `<Container />`, and `<Box />`. Below is an example of their respective hierarchy.

``` jsx
import { Section, Container, Box } from 'hedron';
...
<Section> <-- wrapper component
  <Container> <--- flex container
    <Box> <--- flex children container
      <p>Hedron rocks!!</p> <--- your awesome content 👊
    </Box>
  </Container>
</Section>

```

## Section Component

The `<Section />` component is the topmost component in the hedron grid system. It is designed to be a fixed (or fluid) width container which holds all your flex `<Container />` components.

### Section Props

| Property Name | Type     | Description                                                      | Default |
|--------------:|:---------|:-----------------------------------------------------------------|:--------|
|     className | `String` | Set a css class if you wish to override the styles               | `null`  |
|         fluid | `Bool`   | Enabling fluid mode disables the fixed width and sets it to 100% | `false` |
|         width | `String` | If not using `fluid`, sets a custom width.                       | `null`  |
|        height | `String` | Sets a custom height                                             | `null`  |
|      absolute | `Bool`   | Absolutely positions the containing `div`                        | `false` |
|           top | `String` | Sets top edge of containing element                              | `null`  |
|        bottom | `String` | Sets bottom edge of containing element                           | `null`  |
|         right | `String` | Sets right edge of containing element                            | `null`  |
|          left | `String` | Sets left edge of containing element                             | `null`  |


## Container Component

The `<Container />` component is the parent flex container. It makes flexbox properties easy to configure and remember.

### Container Props

| Property Name | Type     | Description                                             | Default      |
|--------------:|:---------|:--------------------------------------------------------|:-------------|
|     direction | `String` | Sets `flex-direction` of the contained elements         | `horizontal` |
|        vAlign | `String` | Sets the vertical alignment of the contained elements   | `null`       |
|        hAlign | `String` | Sets the horizontal alignment of the contained elements | `null`       |
|          wrap | `Bool`   | Sets the `flex-wrapped` property to `wrap` if true      | `false`      |
|          grow | `Bool`   | Sets the `flex-grow` property to `1` if true            | `false`      |
|        height | `String` | Sets a custom height                                    | `null`       |


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

## Hidden Component

The `<Hidden />` component hides children at given breakpoints. Check out the [layout examples](#hidden-component) for example usage.

### Hidden Props

| Property Name | Type   | Description                     | Default |
|--------------:|:-------|:--------------------------------|:--------|
|            xs | `Bool` | Hidden on xs breakpoint if true | `null`  |
|            sm | `Bool` | Hidden on sm breakpoint if true | `null`  |
|            md | `Bool` | Hidden on md breakpoint if true | `null`  |
|            lg | `Bool` | Hidden on lg breakpoint if true | `null`  |

## Layout Examples

### Sidebar

``` jsx
import { LayoutProvider, Section, Container, Box } from 'hedron';

...

<LayoutProvider debug={{ enabled: true }}>
    <Section>
        <Container direction='vertical' hAlign='center'>
            <Box xs="50%" lg="40%">Header</Box>
            <Box xs='100%'>Navigation</Box>
        </Container>

        <Container wrap>
            <Box xs='100%' md='30%' lg='40%'>
                <Container direction='vertical'>
                    <Box>Sidebar</Box>
                    <Box>Some links</Box>
                    <Box>Or other things</Box>
                </Container>
            </Box>

            <Box xs='100%' md='70%' lg='60%'>
                <Container direction='vertical'>
                    <Box>First Post</Box>
                    <Box>Second Post</Box>
                    <Box>Third Post</Box>
                </Container>
            </Box>
        </Container>
    </Section>
</LayoutProvider>
```

### Hidden Component

``` jsx
import { LayoutProvider, Section, Container, Box, Hidden } from 'hedron';

...

<LayoutProvider debug={{ enabled: true }}>
  <Section debug>
    <p>
      This row is hidden on lg
    </p>
    <Hidden lg><Container><Box /></Container></Hidden>
  </Section>
```
