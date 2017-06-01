
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
