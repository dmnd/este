<a href="https://este.herokuapp.com/"><img alt="Este.js" src="https://cloud.githubusercontent.com/assets/66249/6515265/b91f0fb8-c388-11e4-857e-c90902e0b7a1.png" width="200"></a>

[![Circle CI](https://circleci.com/gh/steida/este.svg?style=svg)](https://circleci.com/gh/steida/este)
[![Join the chat at https://gitter.im/steida/este](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/steida/este)
[![Dependency Status](https://david-dm.org/steida/este.png)](https://david-dm.org/steida/este)
[![devDependency Status](https://david-dm.org/steida/este/dev-status.png)](https://david-dm.org/steida/este#info=devDependencies)
[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

> Robust and comfortable dev stack for isomorphic web apps. Forget about [evil frameworks](http://tomasp.net/blog/2015/library-frameworks/), learn laser focused libraries and patterns instead.

> Forget about PHP, Ruby, Angular, Backbone, whatever client/server only solution. Also, you don't need another me-too-flux library, vanilla Flux is enough. This dev stack is web dev panacea, at least for me :-)

## Techniques

- ES6 and other future JavaScripts dialects with the best transpiler [babeljs.io](https://babeljs.io/). [JSX](http://facebook.github.io/react/docs/jsx-in-depth.html) and [Flowtype](http://flowtype.org/) syntax supported as well. Sourcemaps enabled by default.
- [jest](https://facebook.github.io/jest) unit testing
- Server side rendering.
- Localization with [formatjs.io](http://formatjs.io/), stale browsers supported as well.
- React with Flux with immutable global app state like Om or [Omniscient](https://github.com/omniscientjs/omniscient/wiki/Simpler-UI-Reasoning-with-Unidirectional-Dataflow-and-Immutable-Data).
- Isomorphic architecture with stateless actions and stores.
- Mobile first, offline first, frontend first.
- Vanilla Flux, we don't need over abstracted frameworks.
- Webpack css livereload with hot module reload even for React components.
- Easy undo/redo and app state load/save.
- Super fast rendering with [immutable.js](http://facebook.github.io/immutable-js).
- Well tuned webpack devstack with handy [notifier](https://github.com/mikaelbr/node-notifier).
- Stylesheets in CSS, LESS, SASS or Stylus.
- Optimized for [critical rendering path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path).
- Google Analytics preconfigured.

## Prerequisites

Install [iojs](https://iojs.org/) or [node.js](http://nodejs.org).
Then install [gulp.js](http://gulpjs.com/).
```shell
npm install -g gulp
```

## Create App

```shell
git clone https://github.com/steida/este.git myapp
cd myapp
npm install
```

## Start Development

- run `gulp`
- point your browser to [localhost:8000](http://localhost:8000)
- build something beautiful

## Dev Tasks

- `gulp` run app in development mode
- `gulp -p` run app in production mode
- `gulp test`

## CI Tasks

- `npm start` just run app, remember to set NODE_ENV=production and others enviroment variables.
- `npm postinstall` just alias for `gulp build --production`, useful for Heroku.
- `npm test` just alias for `gulp test`

## Examples

- [Este TodoMVC](https://github.com/steida/este-todomvc)

## Documentation

So you decided to give a chance to this web stack, but where is documentation? Code is documentation itself as it illustrates various patterns, but for start you should read something about [React.js](http://facebook.github.io/react/). Then you should learn [what is the Flux
application architecture](https://medium.com/brigade-engineering/what-is-the-flux-application-architecture-b57ebca85b9e). Now refresh you JavaScript knowledge about "new" JavaScript - [learn ES6](https://babeljs.io/docs/learn-es6/). This stack uses [immutable.js](http://facebook.github.io/immutable-js/) and for a [good reason](https://github.com/facebook/immutable-js/#the-case-for-immutability). Check this nice short [video](https://www.youtube.com/watch?v=5yHFTN-_mOo Ok, Server side you.http://expressjs.com/), to see one of many great advantages of [functional programming](http://www.smashingmagazine.com/2014/07/02/dont-be-scared-of-functional-programming/). [Express.js](http://expressjs.com/) is used on the [Node.js](http://nodejs.org/api/) based server. Application is [isomorphic](http://isomorphic.net/javascript), so we can share code between client and server easily. Congrats, now you're Este.js expert level 1 :-)

## Links

- [stackoverflow.com/questions/tagged/estejs](http://stackoverflow.com/questions/tagged/estejs)
- [twitter.com/estejs](https://twitter.com/estejs)

## Tips and Tricks and Lips and Tits

- App state snapshot: Press `shift+ctrl+s`, then open dev console and type `_appState`.
- With global immutable app state, you don't need IoC container so badly - [SOLID: the next step is Functional](http://blog.ploeh.dk/2014/03/10/solid-the-next-step-is-functional). Still DI is relevant for some cases and then use [Pure DI](http://blog.ploeh.dk/2014/06/10/pure-di/).
- Use `const` by default, `let` if you have to rebind a variable.
- Use `() =>` lambda expression for all predicates and anonymous functions.
- Always use React propTypes for props passed to component, and if props are immutables or primitives, use PureRenderMixin. Simple rule for ultimate performance.
- Never mock browser inside server code, it can confuse isomorphic libraries.
- Always use settostring helper for actions.
- Even though we can use `import {canUseDOM} from 'react/lib/ExecutionEnvironment'` to detect browser/server, don't use it since it's runtime value. Use webpack DefinePlugin to set process.env.IS_BROWSER rather, because compilation removes dead code then.
- [aeflash.com/2015-02/react-tips-and-best-practices.html](http://aeflash.com/2015-02/react-tips-and-best-practices.html)
- Why React `this.state` isn't used? Because whole app state belongs to app one global immutable app state. So we can log it easily, user can navigate out page with half fulfilled form without losing its state, and more.
- You can still use Closure Tools, [gist](https://gist.github.com/steida/afbc595a1e2f27e925d9)

## Notes

- Este.js dev stack should work on OSX, Linux, and even Windows. Feel free to report any issue.
- As a rule of thumb, Este.js supports all evergreen browsers plus last two pieces of IE. In theory, It should not be hard to support IE8 as hell.

## Credit

<img alt="Este.js" src="https://cloud.githubusercontent.com/assets/66249/6515278/de638916-c388-11e4-8754-184f5b11e770.jpeg" width="200">

made by Daniel Steigerwald, [twitter.com/steida](https://twitter.com/steida)
