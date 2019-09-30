# svg2vue

> a command line tool to optimize svg and wrap it into vue component


## Install

```sh
# install global
yarn global add svg2vue

# install for project
yarn add svg2vue -D
```


## Usage
### Generate icon
#### CLI
```sh
svg2vue <source_directory> <target_directory>

Options:
  --svgo-config     Svgo config file
  --base-component  Vue component that all icon components extends from
```

#### Package script
```json
{
  "scripts": {
    "gen-icons": "svg2vue <source_directory> <target_directory>"
  }
}
```

### Use icon
```vue
<template>
  <div class="demo">
    <!-- use fill -->
    <icon-example fill="#fff" />
    <!-- use style -->
    <icon-example style="color: #fff;" />
  </div>
</template>

<script>
import IconExample from '<target_directory>/IconExample'
// or
import { IconExample } from '<target_directory>'

export default {
  components: { IconExample }
}
</script>
```


## Custom

### Svgo config

pass a svgo config file or json string to replace [default config](./svgo.yml)

```sh
svgo2vue <source_directory> <target_directory> --svgo-config="./svgo.yml"
```


### Base component

pass a vue component file to replace [default component](./lib/BaseComponent.vue)

```sh
svgo2vue <source_directory> <target_directory> --base-component="./BaseComponent.vue"
```

### Color

keep `fill` attr on `<path>`, and it's color will not changed by attr `fill` or style `color` on the component root attrs