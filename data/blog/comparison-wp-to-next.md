---
title: 'Which blogging platform to choose?Wordpress or NextJS'
date: 2022-12-27T15:32:14Z
lastmod: '2022-12-27'
tags: ['next-js', 'wordpress', 'blogging']
draft: false
summary: 'Indeed, statistically wordpress is the most used as blogging platform and 43.2% of all websites on the internet make use of it. Since 20122, the usage of Wordpress is increasing 12% per year. However,'
layout: PostSimple
bibliography: references-data.bib
canonicalUrl: https://tailwind-nextjs-starter-blog.vercel.app/blog/new-features-in-v1/
---

## Overview

A post on the new features introduced in v1.0. New features:

## Is Wordpress better than Nextjs?

Inspired by [Docusaurus](https://docusaurus.io/docs/next/markdown-features/inline-toc) and Gatsby's [gatsby-remark-table-of-contents](https://www.gatsbyjs.com/plugins/gatsby-remark-table-of-contents/),
the `toc` variable containing all the top level headings of the document is passed to the MDX file and can be styled accordingly.
To make generating a table of contents (TOC) simple, you can use the existing `TOCInline` component.

For example, the TOC in this post was generated with the following code:

## Newletter component (v1.1.3)

Introduced in v1.1.3, the newsletter component gives you an easy way to build an audience. It integrates with the following providers:

- [Mailchimp](https://mailchimp.com/)
- [Buttondown](https://buttondown.email/)
- [Convertkit](https://convertkit.com/)

To change the default Inter font:

1. Install the preferred [font](https://fontsource.org/fonts) - `npm install -save @fontsource/<font-name>`
2. Update the import at `pages/_app.js`- `import '@fontsource/<font-name>.css'`
3. Update the `fontfamily` property in the tailwind css config file

## Upgrade guide
