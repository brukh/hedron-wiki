## Break Points

Hedron comes with 3 built-in break points. These are the break-points that I've found to be most useful in responsive website design.

Hedron is built mobile-first, which means that all styles that should be displayed on a mobile device are placed outside of all media queries. Whenever I refer to the `xs` breakpoint, I'm referring to the default break-point that comes before all media queries.

``` js
{
  sm: 500,
  md: 768,
  lg: 1100,
}
```

Eventually I'd like to implement a way to customize these break-points on a per-project basis.

## Row Component 

``` jsx
import { Row } from 'hedron';
...
<Row />
```

Although this is the most basic usage, you would never use a `Row` in the above way. In order for a `Row` to be useful, it needs to be filled with [`Column`](#column-component) components. Currently it's advised to __only__ put `Column` or `Row` components directly inside `Row` components, because of the way the property inheritance system works in hedron.

### Row Options

| Property Name  |      Type     |  Description  |
| -------------: | ------------- | ------------- |
|          debug |      Bool     | Draws all child columns with "bounding boxes" for easy visualization of the grid. (Default: `false`) |
|      divisions |     Number    | The amount of horizontal columns this row creates. (Default: `12`) |

## Column Component

``` jsx
import { Row, Column } from 'hedron';
...
<Row>
  <Column><p>By default, this renders a div at 100% width.</p></Column>
</Row>
```

### Column Options

| Property Name  |      Type     |  Description  |
| -------------: | ------------- | ------------- |
|          fluid |      Bool     | If true, disable padding. |
|             xs |     Number    | Width during `xs` breakpoint. |
|             sm |     Number    | Width during `sm` breakpoint. |
|             md |     Number    | Width during `md` breakpoint. |
|             lg |     Number    | Width during `lg` breakpoint. |
|        xsShift |     Number    | Width of left margin during `xs` breakpoint. |
|        smShift |     Number    | Width of left margin during `sm` breakpoint. |
|        mdShift |     Number    | Width of left margin during `md` breakpoint. |
|        lgShift |     Number    | Width of left margin during `lg` breakpoint. |


## Layout Example

``` jsx
import { Row, Column } from 'hedron';
...
<Row divisions={2}>
  <Column lg={1}>
    <h1>Site Title</h1>
  </Column>
  <Column lg={1}>
    <h2>Site Slogan</h2>
  </Column>
</Row>

<Row divisions={9}>
  <Column xs={3} lg={1} lgShift={3}>
    <h4>Section Title</h4>
    <p>Etiam pretium libero massa, vitae lacinia nibh ultricies ut.</p>
  </Column>
  <Column xs={3} lg={1}>
    <h4>Section Title</h4>
    <p>Etiam pretium libero massa, vitae lacinia nibh ultricies ut.</p>
  </Column>
  <Column xs={3} lg={1}>
    <h4>Section Title</h4>
    <p>Etiam pretium libero massa, vitae lacinia nibh ultricies ut.</p>
  </Column>
</Row>

<Row>
  <Column sm={4}>
    <h4>Footer Title</h4>
    <p>Etiam pretium libero massa, vitae lacinia nibh ultricies ut.</p>
  </Column>
  <Column sm={8}>
    <ul>
      <li><a href="#">Footer Link</a></li>
      <li><a href="#">Footer Link</a></li>
      <li><a href="#">Footer Link</a></li>
    </ul>
  </Column>
</Row>
```