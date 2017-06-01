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
