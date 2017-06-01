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
