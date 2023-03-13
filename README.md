# Sanity Plugin Schema Visualizer

A custom Tool to visually represent schema registered in a Sanity Studio. 

Not intended to be feature complete or as a schema builder/editor. 

There are known issues:

- [ ] Full schema is not displayed, and some inner fields are not retrieved
- [ ] On the initial load, the "card" for each document schema is shown in a horizontal bar, not grouped, but can be dragged into position
- [ ] The arrows aren't great :/

![Screenshot 2023-03-13 at 11 33 39](https://user-images.githubusercontent.com/9684022/224690516-d68d1a85-5129-40df-8855-117c663de5a2.png)

## Installation

```sh
npm install sanity-plugin-schema-visualizer
```

## Usage

Add it as a plugin in `sanity.config.ts` (or .js):

```ts
import {defineConfig} from 'sanity'
import {schemaVisualizer} from 'sanity-plugin-schema-visualizer'

export default defineConfig({
  // ...
  plugins: [
    // ...all other plugins
    schemaVisualizer()
  ],
})
```

Optionally, you can configure some defaults for displayed and hidden document cards.

```ts
schemaVisualizer({
  defaultSchemaTypes: ['movie'],
  hiddenSchemaTypes: ['person'],
})
```

## License

[MIT](LICENSE) © Simeon Griggs

## Develop & test

This plugin uses [@sanity/plugin-kit](https://github.com/sanity-io/plugin-kit)
with default configuration for build & watch scripts.

See [Testing a plugin in Sanity Studio](https://github.com/sanity-io/plugin-kit#testing-a-plugin-in-sanity-studio)
on how to run this plugin with hotreload in the studio.


### Release new version

Run ["CI & Release" workflow](TODO/actions/workflows/main.yml).
Make sure to select the main branch and check "Release new version".

Semantic release will only release on configured branches, so it is safe to run release on any branch.