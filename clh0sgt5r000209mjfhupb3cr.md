---
title: "Developing Astro website with AWS Serverless"
seoTitle: "Developing Astro website with AWS Serverless"
seoDescription: "A guide to developing Astro static and SSR website and deploying on the AWS Platform"
datePublished: Fri Apr 28 2023 16:49:19 GMT+0000 (Coordinated Universal Time)
cuid: clh0sgt5r000209mjfhupb3cr
slug: developing-astro-website-with-aws-serverless
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1681292642334/42cd6a0a-bef1-424d-aab6-6a58ab807957.png
tags: aws, aws-cdk, astro

---

# Introduction

[Astro](https://astro.build/) is the all-in-one web framework to build the website. It not only builds the static website but also builds the SSR website via the [Adapter](https://docs.astro.build/en/guides/server-side-rendering/). But unfortunately, Astro officials just support [Cloudflare](https://docs.astro.build/en/guides/integrations-guide/cloudflare/), [Deno](https://docs.astro.build/en/guides/integrations-guide/deno/), [Netlify](https://docs.astro.build/en/guides/integrations-guide/netlify/), [Node.js](https://docs.astro.build/en/guides/integrations-guide/node/) and [Vercel](https://docs.astro.build/en/guides/integrations-guide/vercel/). So I spent a few weeks developing the [AWS Adapter](https://github.com/helbing/astrojs-aws/tree/main/packages/adapter) and [CDK Construct](https://github.com/helbing/astrojs-aws/tree/main/packages/construct). In this post, I will talk about how to develop the Astro website via these packages.

# Get started

First, you need to install the [AWS Adapter](https://github.com/helbing/astrojs-aws/tree/main/packages/adapter).

```bash
npx astro add @astrojs-aws/adapter
```

And then, you should enable SSR features and configure to use AWS Adapter.

```typescript
// astro.config.mjs || astro.config.ts

import aws from "@astrojs-aws/adapter"
import { defineConfig } from "astro/config"

export default defineConfig({
  output: "server", // enable SSR
  adapter: aws(), // use AWS adapter
})
```

If you want to deploy the website to [Lambda@Edge](https://aws.amazon.com/lambda/edge/), you need to configure the following:

```typescript
adapter: aws({
  isEdge: true
})
```

# Deployment

After you build the Astro SSR website, you will get two directories: `dist/server` and `dist/client`. So, how could we deploy them to [AWS](https://aws.amazon.com/)? It depends on whether you want to deploy the website to the edge node. There are two architectures:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1682439168884/ba5ed608-1947-4f45-ba59-7323aa0fcdad.png align="center")

A recommended way is to use the AWS CDK to deploy the website. I also develop the [CDK Construct](https://github.com/helbing/astrojs-aws/tree/main/packages/construct) for it to help to deploy the website.

```typescript
import { LambdaAstroSite } from "@astrojs-aws/construct"

new LambdaAstroSite(this, "LambdaAstroSite", {
  serverEntry: "/path/to/dist/server/entry.mjs",
  staticDir: "/path/to/dist/client",
})
```

# In the end

Hope this post can help you. Happy Coding!