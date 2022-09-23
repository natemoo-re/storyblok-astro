<div align="center">
	<a  href="https://www.storyblok.com?utm_source=github.com&utm_medium=readme&utm_campaign=storyblok-astro" align="center">
		<img  src="https://a.storyblok.com/f/88751/600x200/cc68aca8ea/storyblok-astro.jpg" width="300" height="100" alt="Storyblok + Astro">
	</a>
	<h1 align="center">@storyblok/astro</h1>
	<p align="center">Astro module for the <a href="http://www.storyblok.com?utm_source=github.com&utm_medium=readme&utm_campaign=storyblok-astro" target="_blank">Storyblok</a> Headless CMS.</p> <br />
</div>

<p align="center">
  <a href="https://npmjs.com/package/@storyblok/astro">
    <img src="https://img.shields.io/npm/v/@storyblok/astro/latest.svg?style=flat-square" alt="Storyblok Astro" />
  </a>
  <a href="https://npmjs.com/package/@storyblok/astro" rel="nofollow">
    <img src="https://img.shields.io/npm/dt/@storyblok/astro.svg?style=flat-square" alt="npm">
  </a>
  </p>

<p align="center">
  <a href="https://discord.gg/jKrbAMz">
   <img src="https://img.shields.io/discord/700316478792138842?label=Join%20Our%20Discord%20Community&style=appveyor&logo=discord&color=09b3af">
   </a>
  <a href="https://twitter.com/intent/follow?screen_name=storyblok">
    <img src="https://img.shields.io/badge/Follow-%40storyblok-09b3af?style=appveyor&logo=twitter" alt="Follow @Storyblok" />
  </a><br/>
  <a href="https://app.storyblok.com/#!/signup?utm_source=github.com&utm_medium=readme&utm_campaign=storyblok-nuxt">
    <img src="https://img.shields.io/badge/Try%20Storyblok-Free-09b3af?style=appveyor&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAB4AAAAeCAYAAAA7MK6iAAAABGdBTUEAALGPC/xhBQAAADhlWElmTU0AKgAAAAgAAYdpAAQAAAABAAAAGgAAAAAAAqACAAQAAAABAAAAHqADAAQAAAABAAAAHgAAAADpiRU/AAACRElEQVRIDWNgGGmAEd3D3Js3LPrP8D8WXZwSPiMjw6qvPoHhyGYwIXNAbGpbCjbzP0MYuj0YFqMroBV/wCxmIeSju64eDNzMBJUxvP/9i2Hnq5cM1devMnz984eQsQwETeRhYWHgIcJiXqC6VHlFBjUeXgav40cIWkz1oLYXFmGwFBImaDFBHyObcOzdW4aSq5eRhRiE2dgYlpuYoYSKJi8vw3GgWnyAJIs/AuPu4scPGObd/fqVQZ+PHy7+6udPOBsXgySLDfn5GRYYmaKYJcXBgWLpsx8/GPa8foWiBhuHJIsl2DkYQqWksZkDFgP5PObcKYYff//iVAOTIDlx/QPqRMb/YSYBaWlOToZIaVkGZmAZSQiQ5OPtwHwacuo4iplMQEu6tXUZMhSUGDiYmBjylFQYvv/7x9B04xqKOnQOyT5GN+Df//8M59ASXKyMHLoyDD5JPtbj42OYrm+EYgg70JfuYuIoYmLs7AwMjIzA+uY/zjAnyWJpDk6GOFnCvrn86SOwmsNtKciVFAc1ileBHFDC67lzG10Yg0+SjzF0ownsf/OaofvOLYaDQJoQIGix94ljv1gIZI8Pv38zPvj2lQWYf3HGKbpDCFp85v07NnRN1OBTPY6JdRSGxcCw2k6sZuLVMZ5AV4s1TozPnGGFKbz+/PE7IJsHmC//MDMyhXBw8e6FyRFLv3Z0/IKuFqvFyIqAzd1PwBzJw8jAGPfVx38JshwlbIygxmYY43/GQmpais0ODDHuzevLMARHBcgIAQAbOJHZW0/EyQAAAABJRU5ErkJggg==" alt="Follow @Storyblok" />
  </a>
</p>

## Live Demo

If you are in a hurry, check out our official **[live demo](https://stackblitz.com/edit/astro-sdk-demo)** on StackBlitz.

## 🚀 Usage

> If you are first-time user of Storyblok, read the [Getting Started](https://www.storyblok.com/docs/guide/getting-started?utm_source=github.com&utm_medium=readme&utm_campaign=storyblok-nuxt) guide to get a project ready in less than 5 minutes.

## Installation

Install `@storyblok/astro`:

```bash
npm install @storyblok/astro
# yarn add @storyblok/astro
```

Add the following code to `astro.config.mjs` and replace the `accessToken` with the preview API token of your Storyblok space.

```js
import { defineConfig } from "astro/config";
import storyblok from "@storyblok/astro";

export default defineConfig({
  integrations: [
    storyblok({
      accessToken: "<your-access-token>",
    }),
  ],
});
```

### Options

When you initialize the module, you can pass all [_@storyblok/js_ options](https://github.com/storyblok/storyblok-js#features-and-api)

```js
// Defaults
storyblok({
  accessToken: "<your-access-token>",
  bridge: true,
  apiOptions: {}, // storyblok-js-client options
  use: [apiPlugin],
});
```

> Note: if you don't use `apiPlugin`, you can use your preferred method or function to fetch your data.

## Getting started

### 1. Creating and linking your components to the Storyblok Visual Editor

In order to link your Astro components to their equivalents you created in Storyblok:

First, you need to load them globally by specifying their name and their path in `astro.config.mjs`:

```javascript
components: {
  page: "storyblok/Page",
  feature: "storyblok/Feature",
  grid: "storyblok/Grid",
  teaser: "storyblok/Teaser",
},
```

> Note: The `src` folder is automatically added to the beginning of the path, so in this example your Astro components should be located here:
>
> - `src/storyblok/Page.astro`
> - `src/storyblok/Feature.astro`
> - `src/storyblok/Grid.astro`
> - `src/storyblok/Teaser.astro`
>   You can choose any other folder in the `src` directory for your Astro components.

For each component, use the `storyblokEditable()` function on its root element, passing the `blok` property that they receive:

```html
---
import { storyblokEditable } from '@storyblok/astro';

const { blok } = Astro.props
---

<div {...storyblokEditable(blok)}>
  <h2>{blok.headline}</h2>
</div>
```

Finally, you can use the provided `<StoryblokComponent>` for nested components; it will automatically render them (if they have been registered globally beforehand):

```html
---
import { storyblokEditable } from '@storyblok/astro';
import StoryblokComponent from '@storyblok/astro/StoryblokComponent.astro';

const { blok } = Astro.props
---

<main {...storyblokEditable(blok)}>
  {blok.body?.map(blok => {return <StoryblokComponent blok={blok} />})}
</main>
```

> Note: The `blok` is the actual blok data coming from [Storblok's Content Delivery API](https://www.storyblok.com/docs/api/content-delivery/v2?utm_source=github.com&utm_medium=readme&utm_campaign=storyblok-astro).

#### Using partial hydration

If you want to use partial hydration with any of the [frameworks supported by Astro](https://docs.astro.build/en/guides/integrations-guide/#article), follow these steps:

1. [Install the official Astro integration for your desired framework](https://docs.astro.build/en/guides/integrations-guide/#automatic-integration-setup)
2. Create an Astro component that serves as a wrapper and utilizes the most suitable [client directive](https://docs.astro.build/en/reference/directives-reference/#client-directives)
3. Create the actual component in Vue, Svelte, React or any other supported framework

For working examples, please refer to the [Live Demo on Stackblitz](https://stackblitz.com/edit/astro-sdk-demo).

### 2. Getting Storyblok Stories and using the Storyblok Bridge

### Fetching one Story

Use the `useStoryblokApi` function to have access to an instance of `storyblok-js-client`:

```html
---
import { useStoryblokApi } from "@storyblok/astro";
import StoryblokComponent from "@storyblok/astro/StoryblokComponent.astro";

const storyblokApi = useStoryblokApi();
const { data } = await storyblokApi.get("cdn/stories/home", {
  version: "draft",
});

const story = data.story;
---

<StoryblokComponent blok={story.content} />
```

> Note: The available methods are described in the [storyblok-js-client] repository(https://github.com/storyblok/storyblok-js-client#method-storyblokget)

### Dynamic Routing

In order to dynamically generate Astro pages based on the Stories in your Storyblok Space, you can use the [Storyblok Links API](https://www.storyblok.com/docs/api/content-delivery/v2#core-resources/links/links) and the Astro [`getStaticPaths()` function](https://docs.astro.build/en/reference/api-reference/#getstaticpaths) similar to this example:

```html
---
import { useStoryblokApi } from "@storyblok/astro";
import StoryblokComponent from "@storyblok/astro/StoryblokComponent.astro";

export async function getStaticPaths() {
  const storyblokApi = useStoryblokApi();
  
  const { data } = await storyblokApi.get("cdn/links", {
    version: "draft",
  });
  let links = data.links;
  links = Object.values(links);

  return links.map((link) => {
    return {
      params: { slug: link.slug },
    };
  });
}

const { slug } = Astro.params;

const storyblokApi = useStoryblokApi();

const { data } = await storyblokApi.get(`cdn/stories/${slug}`, {
  version: "draft",
});

const story = data.story;
---

<StoryblokComponent blok={story.content} />
```

### Using the Storyblok Bridge

The Storyblok Bridge is automatically activated by default. If you would like to disable it or enable it conditionally (e.g. depending on the environment) you can set the `bridge` parameter to `false` in `astro.config.mjs`:

> Note: Since Astro is not a reactive JavaScript framework and renders everything as HTML, the Storyblok Bridge will not provide real-time editing as you may know it from other frameworks. However, it automatically refreshes the site for you whenever you save or publish a story.

#### Rendering Rich Text

You can easily render rich text by using the `renderRichText` function that comes with `@storyblok/astro`. Then you can use the [`set:html` directive](https://docs.astro.build/en/reference/directives-reference/#sethtml):

```html
---
import { renderRichText } from '@storyblok/astro';

const { blok } = Astro.props

const renderedRichText = renderRichText(blok.text)
---

<div set:html={renderedRichText}></div>
```

## API

### useStoryblokApi()

Returns the instance of the `storyblok-js-client`.

## Acknowledgements

A huge thank you goes to the Astro Team. In particular to [Tony Sull](https://github.com/tony-sull), who has provided extraordinary support and made automagically rendering Storyblok components a reality.

## 🔗 Related Links

- **[Live Demo on Stackblitz](https://stackblitz.com/edit/astro-sdk-demo)**
- **[Storyblok CLI](https://github.com/storyblok/storyblok)**: A simple CLI for scaffolding Storyblok projects and fieldtypes.

## ℹ️ More Resources

### Support

- Bugs or Feature Requests? [Submit an issue](/../../issues/new);
- Do you have questions about Storyblok or you need help? [Join our Discord Community](https://discord.gg/jKrbAMz).

### Contributing

Please see our [contributing guidelines](https://github.com/storyblok/.github/blob/master/contributing.md) and our [code of conduct](https://www.storyblok.com/trust-center#code-of-conduct?utm_source=github.com&utm_medium=readme&utm_campaign=storyblok-astro).
This project use [semantic-release](https://semantic-release.gitbook.io/semantic-release/) for generate new versions by using commit messages and we use the Angular Convention to naming the commits. Check [this question](https://semantic-release.gitbook.io/semantic-release/support/faq#how-can-i-change-the-type-of-commits-that-trigger-a-release) about it in semantic-release FAQ.