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

## Is Wordpress better than Nextjs?

The thing is not necessarily a matter of one being "better" than the other, as they are designed for different purposes and can be used to achieve different goals.

WordPress is a content management system (CMS) that is primarily used for creating and managing websites that primarily consist of static content such as text, images, and videos. It is known for its ease of use and wide range of plugins and themes that can be used to customize and extend its functionality. WordPress is particularly well-suited for creating blogs, news websites, and other types of websites that require frequent updates and the ability to easily add and manage content.

Next.js, on the other hand, is a framework for building server-rendered or statically exported React.js applications. It is designed to make it easy to build performant, scalable, and SEO-friendly web applications using React. Next.js is particularly well-suited for building complex web applications that require server-side rendering, automatic code splitting, and optimized performance.

In general, if you are looking to create a simple website with static content, WordPress might be a good choice. If you are building a more complex web application that requires advanced features like server-side rendering and optimized performance, Next.js might be a better fit. In the end, the best choice depends on the goals of the project.

Here is a comparison of WordPress and Next.js:

### WordPress

#### Pros:

- **Easy to use**: WordPress has a user-friendly interface and a large community of users, which means that there is a lot of documentation and support available.
  Wide range of plugins and themes: WordPress has a large ecosystem of plugins and themes that can be used to customize and extend the functionality of the website. This means that you can easily add features like contact forms, e-commerce functionality, and more without having to build them from scratch.
  **Suitable for static content**: WordPress is primarily designed for creating and managing websites that consist of static content such as text, images, and videos. This makes it a good choice for creating blogs, news websites, and other types of websites that require frequent updates.

#### Cons:

- **Limited flexibility**: While WordPress is relatively easy to use, it can be difficult to customize beyond the options provided by plugins and themes. This means that if you want to build a more complex or customized website, you may need to do a lot of custom coding.
- **Security risks**: Because WordPress is so widely used, it is a common target for hackers. This means that it is important to keep the WordPress installation and plugins up to date to minimize security risks.

### NextJS

#### Pros:

- **Server-side rendering**: Next.js is designed to make it easy to build server-rendered React applications. It's improving the performance and SEO of the web application, as the server can pre-render the content and send it to the client, rather than relying on the client to render the content.

- **Automatic code splitting**: Next.js automatically splits the code into smaller chunks, which can improve the performance of the web application by loading only the code that is needed for the current page.

- **Optimized performance**: Next.js is designed to be performant out of the box, with features like automatic optimization of images and automatic generation of service workers for offline support.

#### Cons:

- **Requires knowledge of React**: In order to use Next.js, it needs to have a working knowledge of React. Meaning that it needs to be familiar with concepts like components, state, and props.

- **Not suitable for static content**: While Next.js can be used to build static websites, it is primarily designed for building server-rendered or statically exported web applications. This means that it may not be the best choice for creating simple websites with static content.

## Case Study

Why have I switched from WordPress to Next.js to blog? I have been blogging with Wordpress since 2011 and I have no problem with it. But until there were too many things changed, one of them is Gutenberg editor. I found it a bit frustrating to use it in terms of navigating the editor and I prefer the classic editor to gutenberg. That's one of the thing.

Ok, now let’s talk about the website using WordPress one by one:
In my opinion, there are some reasons not to use Wordpress

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
