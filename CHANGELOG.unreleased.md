<!--

Format:

- Category: Title ([#PR] by [@user])

  Description

  ```
  // Input
  Code Sample

  // Output (Prettier stable)
  Code Sample

  // Output (Prettier master)
  Code Sample
  ```

Details:

  Description: optional if the `Title` is enough to explain everything.

Examples:

- TypeScript: Correctly handle `//` in TSX ([#5728] by [@JamesHenry])

  Previously, putting `//` as a child of a JSX element in TypeScript led to an error
  because it was interpreted as a comment. Prettier master fixes this issue.

  <!-- prettier-ignore --\>
  ```js
  // Input
  const link = <a href="example.com">http://example.com</a>

  // Output (Prettier stable)
  // Error: Comment location overlaps with node location

  // Output (Prettier master)
  const link = <a href="example.com">http://example.com</a>;
  ```

-->

- Markdown: Do not align table contents if it exceeds the print width and `--prose-wrap never` is set ([#5701] by [@chenshuai2144])

  The aligned table is less readable than the compact one
  if it's particularly long and the word wrapping is not enabled in the editor
  so we now print them as compact tables in these situations.

  <!-- prettier-ignore -->
  ```md
  <!-- Input -->
  | Property | Description | Type | Default |
  | -------- | ----------- | ---- | ------- |
  | bordered | Toggles rendering of the border around the list | boolean | false |
  | itemLayout | The layout of list, default is `horizontal`, If a vertical list is desired, set the itemLayout property to `vertical` | string | - |

  <!-- Output (Prettier stable, --prose-wrap never) -->
  | Property   | Description                                                                                                           | Type    | Default |
  | ---------- | --------------------------------------------------------------------------------------------------------------------- | ------- | ------- |
  | bordered   | Toggles rendering of the border around the list                                                                       | boolean | false   |
  | itemLayout | The layout of list, default is `horizontal`, If a vertical list is desired, set the itemLayout property to `vertical` | string  | -       |

  <!-- Output (Prettier master, --prose-wrap never) -->
  | Property | Description | Type | Default |
  | --- | --- | --- | --- |
  | bordered | Toggles rendering of the border around the list | boolean | false |
  | itemLayout | The layout of list, default is `horizontal`, If a vertical list is desired, set the itemLayout property to `vertical` | string | - |
  ```
