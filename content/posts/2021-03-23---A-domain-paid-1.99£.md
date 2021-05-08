---
title: A domain paid 1.99£
date: "2021-03-23T22:00:00.000Z"
template: "post"
draft: false
slug: "a-domain-paid-1.99£"
category: "General"
tags:
  - "GatsbyJS"
  - "React"
  - "GraphQL"
description: "My idea is to finally create a website where to post things, more often."
socialImage: "/media/a-domain-paid-1.99£.jpg"
---

At the moment, the domain _rossanodan.me_ redirects to [my DEV account](dev.to/rossanodan) because I don't have a real personal website. I don't have one since I don't write so much even if I'd like to. So what? Since I paid for it, I want to use it properly and not only as a mere redirect to _dev.to_.

PS. I bought my domain on [GoDaddy](https://uk.godaddy.com/). Take a look, you may find some good deals like mine.

## My idea

My idea is to create a website where to post things, more often. You can clearly see two challenges here, one more difficult than the other. Creating my personal website shouldn't be so hard since I'm quite familiar with React and GraphQL. But posting regularly.. That's where things become tough. But I want to try, for real this time. I have to find inspiration and start writing more often. It hasn't to be always about the code.

## A starting point

As I said, at the moment I possess a domain, _rossanodan.me_, which redirects to [my DEV account](dev.to/rossanodan). I posted some interesting stuff there but unconstantly and maybe with errors. I am not used to review what I write. I do it impulsively, like in a sort of a short but intense nirvana. Then I don't write anything for months.

I'd like to use my domain as the domain for my website. But where can I host the website? [GitHub Pages](https://pages.github.com/) maybe..? It's an idea. Firebase? Too much work for what I'd like to do.. I don't want to deal with cloud functions, deploying and all that stuff for now. I want something easy to update when I post some content.

I found this [How Gatsby Works with GitHub Pages](https://www.gatsbyjs.com/docs/how-to/previews-deploys-hosting/how-gatsby-works-with-github-pages/) and it looks perfect. Gatsby uses React and GraphQL and I can host it on GitHub for free. And there are a lot of templates to start from. It's settled. Gatsby to the rescue.

The starter template I picked is this one https://www.gatsbyjs.com/starters/gatsbyjs/gatsby-starter-blog/.

## Everything starts with a proper setup

I needed to setup the `gatsby-cli` and luckily they made it so easy to follow in [this guide](https://www.gatsbyjs.com/docs/tutorial/part-zero/).

With the `gatsby-cli` installed, it's enough one command to getting started with my project

```bash
gatsby new rossanodan https://github.com/gatsbyjs/gatsby-starter-blog
```

And it all begins with a good looking message

```bash
You can now view gatsby-starter-blog in the browser.
⠀
  http://localhost:8000/
⠀
View GraphiQL, an in-browser IDE, to explore your site's data and schema
⠀
  http://localhost:8000/___graphql
⠀
Note that the development build is not optimized.
To create a production build, use gatsby build
```

So, `http://localhost:8000/` for the site and `http://localhost:8000/___graphql` for GraphiQL (where to explore data performing queries against a GraphQL-based environment).

I think I have all the necessary to get started building my website!

### The development enviroment

The starter template provides some commands to perform basic operations like building or testing. The commands are

- `npm run build` to build the project, for example before deploying it
- `npm run develop` to start the project locally with hot reload
- `npm run format` to run Prettier to format the code
- `npm start` a.k.a. `npm run develop`
- `npm run serve` to serve the production build of the site for testing
- `npm run clean` to wipe out the cache (.cache folder) and public directories
- `npm test` to test the code

Basic commands, nothing special but it's useful having them ready to use.

The first file to edit is `gatsby-config.js`. Here lives the core configuration module

```javascript
module.exports = {
  siteMetadata: {
    title: '',
    author: {
      name: '',
      summary: '',
    },
    description: '',
    siteUrl: '',
    social: {
      twitter: '',
      ...
    },
  },
  ...
}
```

All I did for now is commenting out some stuff like the Bio component since I want to redesign it a little bit.

So if you were searching of a tutorial about how to use Gatsby.. you're in the wrong place, buddy. I'm sorry. More techinal stuff will come, I promise.

This is just the beginning.