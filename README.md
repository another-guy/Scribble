# Scribble

![un-md](https://i.imgur.com/j7PwKGe.png)

## Legend

|Status|Review|Kind|Format|
|---|---|---|---|
| ✔️ have read/used | ❗ important | 🔧 practice | 💻 course |
| ➖ have not read/used yet | 👍 liked | 📄 theory | 📺 video/presentation |
| | 👋 mixed feelings | 🏋️ exercise | |
| | 👎 disliked | | |
| | ❌ | | |

## Learning Materials

### Metalearning

* ➖❗👍📄 **Pragmatic Thinking and Learning** by [Andy Hunt](https://twitter.com/PragmaticAndy). [[the Pragmatic Bookshelf]](https://pragprog.com/book/ahptl/pragmatic-thinking-and-learning) [[Amazon.com]](https://www.amazon.com/Pragmatic-Thinking-Learning-Refactor-Programmers/dp/1934356050).
* ✔️👍📺📄[Making Badass Developers](https://youtu.be/FKTxC9pl-WM) by [Kathy Sierra](https://twitter.com/seriouspony). A talk on how to learn faster and more efficiently.

### JavaScript

* ✔️👍📺📄 [What the heck is the event loop anyway?](https://youtu.be/8aGhZQkoFbQ) by [Philip Roberts](https://twitter.com/philip_roberts).
* ✔️👍📺📄 [Further Adventures of the Event Loop](https://youtu.be/u1kqx6AenYw) by [Erin Zimmer](https://twitter.com/erinjzimmer).
  * [✏️ My Notes](./notes/Erin-Zimmer--Further-Adventures-of-the-Event-Loop.md).
* ➖📺📄[Asynchrony: Under the Hood](https://youtu.be/SrNQS8J67zc) by [Shelley Vohr](https://twitter.com/codebytere).
* ✔️📺📄[JavaScript Engines: The Good Parts™](https://youtu.be/5nmpokoRaZI?list=WL7) by [Mathias Bynens](https://twitter.com/mathias) and [Benedikt Meurer](https://twitter.com/bmeurer).

### Front-end

#### React

* ✔️👍📺🔧 [Simply React (Composable & Extensible Components)](https://www.youtube.com/watch?v=AiJ8tRRH0f8&t=1053s) by [Kent C Dodds](https://twitter.com/kentcdodds).
* ✔️👎📺💻📄🔧 [mobx-state-tree (MST) tutorial](https://egghead.io/lessons/react-describe-your-application-domain-using-mobx-state-tree-mst-models) by [Michel Weststrate](https://twitter.com/mweststrate?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor). Somewhat outdated; doesn't work quite right with TypeScript; doesn't cover debugging and other in-depth tool; only great as a shallow introduction.

### Microservices

* ➖📄 [.NET Microservices: Architecture for Containerized .NET Applications](https://docs.microsoft.com/en-us/dotnet/standard/microservices-architecture/) by [Cesar de la Torre](https://twitter.com/cesardelatorre).

## CSS

* ✔️👍📺🔧 [CSS Grid Changes Everything (About Web Layouts)](https://youtu.be/txZq7Laz7_4) by [Morten Rand-Hendriksen](https://twitter.com/mor10?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor).
  * [✏️ My Notes](./notes/Morten--Rand-Hendriksen--CSS--Grid--Changes--Everything.md).
  * [Building Production-Ready CSS Grid Layouts Today](https://www.smashingmagazine.com/2017/06/building-production-ready-css-grid-layout/).
* ➖🏋️ [Flexbox Froggy](https://flexboxfroggy.com/)
* ✔️👍🏋️ [Grid Garden](http://cssgridgarden.com/)

## Building Tools

### Windows

* ✔️👍🔧 [VS Code](https://code.visualstudio.com/) - extensible code editor.
  * ➖🔧 [Jest Snippets (extension)](https://marketplace.visualstudio.com/items?itemName=andys8.jest-snippets)
  * ➖🔧 [ES7 React/Redux/GraphQL/React-Native snippets (extension)](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets)
* ✔️👍🔧 [Git Bash](https://git-scm.com/downloads) - bash for Windows (part of Git).
* ✔️👍🔧 [ConEmu](https://conemu.github.io/) - multiple console terminal for Windows. 
* ✔️👍🔧 [Yarn](https://yarnpkg.com/en/) - alternative NPM package manger.

### Global NPM packages

* ✔️👍 [create-react-app](https://www.npmjs.com/package/create-react-app): Create React apps with no building configuration.
* ✔️👍 [@angular/cli](https://www.npmjs.com/package/@angular/cli): Scaffold Angular apps.
* ✔️👍 [vue-cli](https://www.npmjs.com/package/vue-cli): A simple CLI for scaffolding Vue.js projects.
* ✔️👍 [generator-node-typescript](https://www.npmjs.com/package/generator-node-typescript): A minimal Yeoman Generator for creating NodeJS modules using TypeScript.
* ✔️👍 [lerna](https://lernajs.io/): A tool for managing JavaScript projects with multiple packages.
* ➖ [nodemon](https://www.npmjs.com/package/nodemon): Simple monitor script for use during development of a node.js app.
* ✔️👍 [hotel](https://www.npmjs.com/package/hotel): Local domains for everyone and more!
* ✔️👍 [json-server](https://www.npmjs.com/package/json-server): Serves JSON files through REST routes.
* ✔️👍 [npm-check-updates](https://www.npmjs.com/package/npm-check-updates): Find newer versions of dependencies than what your package.json or bower.json allows.
* ✔️👍 [http-server](https://www.npmjs.com/package/http-server): A simple zero-configuration command-line http server.
* ✔️👍 [serve](https://www.npmjs.com/package/serve): Serve static files.
* ✔️👍 [source-map-explorer](https://www.npmjs.com/package/source-map-explorer): Analyze and debug space usage through source maps.
* ✔️👍 [yeoman](https://www.npmjs.com/package/yeoman-generator): Rails-inspired generator system that provides scaffolding for your apps.
* ✔️👍 [tldr](https://www.npmjs.com/package/tldr): Simplified and community-driven man pages.

Install individually via `yarn global add <package-name>`

...or install 'em all:

`npm install --global create-react-app @angular/cli vue-cli generator-node-typescript lerna nodemon hotel json-server npm-check-updates http-server serve source-map-explorer yo tldr`

### Candidates

* ➖ [FuseBox](https://github.com/fuse-box/fuse-box): A blazing fast js bundler/loader with a comprehensive API 🔥.
* ➖ [Storybook](https://storybook.js.org/): The UI Development Environment You'll ♥️ to use.
* ➖ [jsonata](http://jsonata.org/): JSON query and transformation language.
* ➖ [TensorFlow.js](https://js.tensorflow.org/): A JavaScript library for training and deploying ML models in the browser and on Node.js.
* ➖ [enzyme](https://airbnb.io/enzyme/): JavaScript Testing utility for React that makes it easier to assert, manipulate, and traverse your React Components' output.
* ➖ [axe-core](https://www.deque.com/axe/): Axe is an open source rules library for accessibility testing. It was developed to empower developers to take automated accessibility testing into their own hands and to avoid common pitfalls of other automated accessibility tools. [Found here; some examples](https://youtu.be/l95VFLj3e2w).

### Recipes

* ✔️👍 [Debug Jest tests via VS Code](https://github.com/Microsoft/vscode-recipes/tree/master/debugging-jest-tests#configure-launchjson-file-for-your-test-framework)

## Productivity Tools

* ✔️👍🔧 [Greenshot](http://getgreenshot.org/): The most awesome tool for making screenshots on Windows.
* ✔️👍🔧 [Emojipedia](https://emojipedia.org/): Quick'n'dirty replacement for SVG icons.
