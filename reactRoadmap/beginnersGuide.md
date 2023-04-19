# React Beginners Guide Reading Notes

## [React Beginners Guide](https://www.freecodecamp.org/news/react-beginners-guide/)

## What do I need to install on my computer?

To build full-scale React projects on your computer, there are a few essential tools every developer needs:

- [Node / NPM](https://nodejs.org/en)(Start with the "LTS" version as it's the most supported version)
- a good code editor (I use [Visual Studio Code](https://code.visualstudio.com/), great for all levels.)
- Git (install it at [Git-SCM.com](https://git-scm.com/) and create a free account at [Github.com](https://github.com/))

**Node** is defined as a JavaScript runtime. When combined with a package manager like **NPM**(which you get at the same time you install Node), it serves as a powerful tool to easily manage libraries within your React projects.

Without Node and PM, if you wanted to add a new JavaScript library to your React project(like [day.js](https://day.js.org/), a library used for formatting dates), you would need to manually add a set of `<script>` tags and manage them yourself.

With Node and NPM (or another package manager like Yarn), we can simply run a command to install whatever JavaScript library we like. To install day.js, we would run:

```javascript
npm install dayjs
```

And NPM will automatically grab that library's code and add it to our `node_modules` folder ✨

**Note:** Node / NPM is not require to create a React project. But it lets you use helpful tools like ~~[Create React App](https://create-react-app.dev/)~~(React Developer team have recently removed `create-react-app` from official documentation. Pull request with reasoning [here](https://github.com/reactjs/react.dev/pull/5487)) and [Next.js](https://nextjs.org/) that make managing your React applications much easier.

Other alternatives include:

1. [Vite](https://vitejs.dev/)
   - Vite is a build tool that aims to provide a faster and leaner development experience for modern web projects.
   - `npm create vite@latest` - in your CLI to get started.
   - Vite is much faster than CRA(Create-React-App) in development because it builds your application on-demand, with tools like native `es modules` and `es build` that scale much better for big projects, It provides a starting point for SPA creation, but doesn't deal with server-side rendering our routing out-of-the-box(it's something you would have to configure yourself), unlike react rendering frameworks such as Next.js.
2. [Nx](https://nx.dev/packages/react)
   - Nx makes scaling easy. Modern techniques such as distributed task execution and computation caching make sure your CI times remain fast, even as you keep adding projects to your workspace.
   - `npx create-nx-workspace@latest --preset=react` - in your CLI to get started.
   - Nx is a tool known for building [monorepos](https://semaphoreci.com/blog/what-is-monorepo), but it's CLI can also build plain React apps that have nothing to do with monorepos. Nx can build standalone React applications with some features that you won't find in Vite. you have to option to choose your own bundler, such as Vite or [Webpack](https://webpack.js.org/)
3. [Next.js](https://nextjs.org/)
   - Next.js enables you to create full-stack web applications by extending the latest React features, and integrating powerful Rust-based JavaScript tooling for the fastest builds.
   - `npx create-next-app@latest` - in your CLI to get started.
   - The main difference when building a Next.js application is that you have a special directory such as `pages` or `app` that can structure routing for a _multi-page_ application. It also comes with server-side rendering, and server-side data fetching with React server components to build fullstack applications with few external dependencies.
4. [Remix](https://remix.run/)
   - Focused on web standards and modern web app UX, you're simply going to build better websites.
   - `npx create-remix@latest` - in your CLI to get started.
   - Recently acquired by [Shopify](https://techcrunch.com/2022/10/31/shopify-acquires-remix-to-bolster-its-storefront-design-tools/), Remix provides many of the same features as Next.js. The biggest difference is related to data fetching - Next.js uses React server components, while Remix does not. <br>
     Both frameworks solve many of the same problems, but they each have subtle differences. We will probably be seeing a lot more of Remix as we progress into 2023.
5. [Gatsby](https://www.gatsbyjs.com/)
   - Gatsby enables developers to build fast, secure, and powerful websites using a React-based framework and innovative data layer that makes integrating different content, APIs, and services into one web experience incredibly simple.
   - `npm init gatsby` in your CLI to get started.
   - Although Gatsby had a major decline in use over the last few years, Gatsby was recently [acquired by Netlify](https://www.gatsbyjs.com/blog/gatsby-is-joining-netlify/). This acquisition will surely see a spike in Gatsby usage. Originally, Gatsby was built for developing static, content-heavy frontends, but now also supports server-side rendering.
6. [Astro](https://astro.build/)
   - Astro is a popular web framework for building perfomant, content-focused websites. Our next-gen frontend architecture (known as Astro Islands) can optimize your site to load 33% faster with 90% less JavaScript using the UI frameworks you already love like React, Svelte, and Vue.
   - `npx create astro@latest` - in your CLI to get started.
   - React takes over the entire DOM. Astro has it's own templating language for handling most of your static content, but allows you to introduce interactivity as needed. This both simplifies your code and introduces huge performance gains.

A good code editor is also essential to be able to:

- Easily manage all files and folders in our React project
- Provide syntax highlighting to style our code to make it easier to read
- Run commands to develop, test, and build our project using an integrated terminal
- Install extensions to provide additional helpful functionality.

**Visual Studio Code** (or VSCode) does all of these things and has great default setting for React development, in addition to being entirely free.

Finally, **Git** and **GitHub** are essential for saving changes that you make to your React projects. Git gives you "version control," a fancy name for a tool that enables you to save your code and restore past saves if necessary.

GitHub is essential as well because it allows us to save all of our code remotely, that is, on our GitHub account. You can save your code and the changes you've made to it with Git and then "push" all of those changes to your GitHub account.

As a result, GitHub serves both as helpful backup for all the work we've done on our React projects and an essential way for others to see our code and make changes to it, too.

[<---BACK](README.md)
