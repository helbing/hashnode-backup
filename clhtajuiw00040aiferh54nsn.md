---
title: "The Pros and Cons of Tailwind CSS"
seoTitle: "The Pros and Cons of Tailwind CSS"
seoDescription: "Tailwind CSS is worth trying"
datePublished: Thu May 18 2023 15:33:07 GMT+0000 (Coordinated Universal Time)
cuid: clhtajuiw00040aiferh54nsn
slug: the-pros-and-cons-of-tailwind-css
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1684423898150/65560619-4a69-4785-90f8-f1e84e97b8df.png
tags: tailwind-css

---

[Tailwind CSS](https://tailwindcss.com/) is a utility-first CSS framework. It not only provides a set of classes that are commonly used for development but also supports custom styles.

# Why I use Tailwind CSS

In the past, we developed websites with HTML, JavaScript, and CSS files and we need to always switch tabs when developing. After that, with the popularity of [JSX](https://facebook.github.io/jsx/), I started using React and went from three files to two files during development. The reason that I use Tailwind CSS is simple, I just want to develop in a single file.

I have used [Tailwind CSS](https://tailwindcss.com/) for a long time, and I've seen a lot of praise and questions about Tailwind CSS. In this post, I will tell you some pros and cons of TailWind CSS with my experiences.

# Pros and Cons

> No Silver Bullets, We Just Trade-off

## Pros: Increase development speed

As I mention, Tailwind CSS provides a set of classes that are commonly used for development, that why It can increase development speed. In the past, we develop like:

```xml
<style>
.my-class {
  border-radius: 50%;
  padding-left: 0.5rem;
  padding-right: 0.5rem;
  margin-top: 0.25rem;
  margin-bottom: 0.25rem;
  text-align: center;
}
</style>

<div class="my-class">Hello World</div>
```

But now, we develop with Tailwind CSS, it looks like this:

```xml
<div class="rounded-full px-2 py-1 text-center">Hello World</div>
```

You can find that we can develop with HTML/JSX and Tailwind CSS in the same place, it's very intuitive. But it also has its issues, and we will talk about it later.

Tailwind CSS also supports [**Responsive Design**](https://tailwindcss.com/docs/responsive-design), [**Dark Mode**](https://tailwindcss.com/docs/dark-mode) **and** [**Custom Styles**](https://tailwindcss.com/docs/adding-custom-styles). Compared to before, Tailwind CSS greatly increases development speed and reduces a lot of work.

## Cons: A lot of classes

That's one thing a lot of people don't like about Tailwind CSS, including me. Look like that:

%[https://codesandbox.io/embed/white-river-t2bh1q?fontsize=14&hidenavigation=1&theme=dark] 

## Cons: Redesign CSS

Some people think that Tailwind CSS is redesigned CSS, and I agree with it. When I first time to use Tailwind CSS, it pains me a lot, my knowledge of CSS was useless, and that let me had to always read the documentation while I writing Tailwind CSS.

However, when I went through several projects using Tailwind CSS, I started to like it, and it made development more efficient.

The Redesign is not necessarily a bad thing, depending on the pros and cons it brings. No silver bullets, we just trade-off.

# Is Tailwind Worth Trying?

Yes, Tailwind CSS is worth trying, but you need to learn CSS first. Tailwind CSS is not for beginners, it requires you to have some knowledge of CSS before you can learn it.

If you prefer CSS-in-JS, that’s ok, everyone has his/her styles. It's as if some people prefer JavaScript over TypeScript because JavaScript doesn't have Type identification and can code more freely. Some people prefer TypeScript over JavaScript because TypeScript has Type identification and can code more safely.