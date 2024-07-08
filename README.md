# Crowdin Knowledge Base

- [Site](https://support.crowdin.com/)

## Getting Started

[![Built with Starlight](https://astro.badg.es/v2/built-with-starlight/tiny.svg)](https://starlight.astro.build).

### Project Structure

```
.
├── public/
├── src/
│   ├── assets/
│   ├── content/
│   │   ├── docs/
│   │   ├── sidebrs/
│   │   └── config.ts
│   └── env.d.ts
├── astro.config.mjs
├── package.json
├── tailwind.config.mjs
└── tsconfig.json
```

- `src/content/sidebrs` - sidebar configuration for Crowdin KB, Crowdin Enterprise KB, Developer Portal.
- `src/content/docs` - contains groups describing the documentation for each product.

Starlight looks for `.md` or `.mdx` files in the `src/content/docs/` directory. Each file is exposed as a route based on its file name.

Images can be added to `src/assets/` and embedded in Markdown with a relative link.

Static assets, like favicons, can be placed in the `public/` directory.

### Commands

All commands are run from the root of the project, from a terminal:

| Command                   | Action                                           |
| :------------------------ | :----------------------------------------------- |
| `npm install`             | Installs dependencies                            |
| `npm run dev`             | Starts local dev server at `localhost:4321`      |
| `npm run build`           | Build your production site to `./dist/`          |
| `npm run preview`         | Preview your build locally, before deploying     |
| `npm run astro ...`       | Run CLI commands like `astro add`, `astro check` |
| `npm run astro -- --help` | Get help using the Astro CLI                     |

### Learn More

- [Starlight’s docs](https://starlight.astro.build/)
- [Astro docs](https://docs.astro.build)
- [Tailwind CSS docs](https://tailwindcss.com/)
- [Astro Discord server](https://astro.build/chat)

## Authoring Content

### Icons

You can use Starlight's [`Icon`](https://starlight.astro.build/guides/components/#icon) component. It provides some basic set of icons.

```mdx
import { Icon } from '@astrojs/starlight/components';

<Icon name="approve-check" />
```

Also, you can use [Astro Icon](https://www.astroicon.dev/guides/components/) component with [Material Design icons](https://icones.js.org/collection/mdi). It supports Local Icons and various Icon Packs.

For example:

```mdx
import { Icon } from 'astro-icon/components';

<Icon name="mdi:cloud-download" />
```

Use the `inline-icon` class to display icons inline with text:

```mdx
<Icon name="mdi:cloud-download" class="inline-icon" />
```

It's always better to use these icons instead of local, as they are already support for dark mode and are accessible.

### File-based/String-based content differentiation

To differentiate between file-based and string-based content, you can use the `Tabs` component with the `syncKey` prop. This prop allows you to switch between tabs and keep the selected tab in sync across multiple components.

```mdx
Some common content

import { Tabs, TabItem } from '@astrojs/starlight/components';

<Tabs syncKey="projectType">
  <TabItem label="File-based project">
    File-based specific content
  </TabItem>
  <TabItem label="String-based project">
    String-based specific content
  </TabItem>
</Tabs>

Common content
```
