## BreakpointProvider component

This works similarly to the
[`<ThemeProvider>`](https://github.com/styled-components/styled-components/blob/master/docs/theming.md)
component in [`styled-components`](https://github.com/styled-components/styled-components).
Any hedron component inside `<BreakpointProvider>` will use these breakpoints.

``` jsx
import { BreakpointProvider, Row, Column } from 'hedron';
...
<BreakpointProvider breakpoints={{ sm: 300, md: 568, lg: 900 }}>
  <Row>
    <Column>My breakpoints are different!</Column>
  </Row>
</BreakpointProvider>
```

If any of the breakpoints are not given, the default values will be used.

``` jsx
// Here the 'lg' breakpoint defaults to 1100
<BreakpointProvider breakpoints={{ sm: 300, md: 900 }} />
```

Usually you would wrap your entire app into a `<BreakpointProvider>` so that you can access the breakpoints anywhere. However, you can place your `<BreakpointProvider>` anywhere inside your component tree and only the children will utilize those breakpoints. You can also nest multiple `<BreakpointProvider>` components if you want to have multiple different breakpoints on a single page.

## withBreakpoints

What if you need to get the breakpoints in your component? The purpose of `withBreakpoints` is to do exactly that.

Just use this Higher Order Component to get access to the breakpoints as props.

``` jsx
import { withBreakpoints } from 'hedron';

const MyComponent = (props) => <div>Breakpoints: {...props.breakpoints}</div>

export default withBreakpoints(MyComponent);
```

As long as your component is a child of `<BreakpointProvider>`, the `breakpoints` prop will be defined.
