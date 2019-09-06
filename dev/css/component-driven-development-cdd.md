# Component Driven Development

{% embed url="https://dev.to/giteden/a-guide-to-component-driven-development-cdd-1fo1" %}

#### Let components drive the development of your applications.

[![](https://res.cloudinary.com/practicaldev/image/fetch/s--EXeep30D--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://cdn-images-1.medium.com/max/2000/1%2AHNrykRFyylLT_oTiiBDn1Q.gif)](https://bit.dev/)

.  
[Modularity](https://en.wikipedia.org/wiki/Modular_programming) has been a key principle in software development since the 1960s. It provides many advantages in software development, leveraging the separation of concerns for better reusability, composability, development etc.

In modern times, modularity takes on a new form in the design of software applications, through **components**. Modern UI libraries and frameworks such as [React](https://reactjs.org/), [Vue](https://vuejs.org/) and [Angular](https://angular.io/), and CDD-oriented tools like [Bit](https://bit.dev/) let us build our applications through modular components, providing the patterns and tools needed to develop each component in separation and compose them together.

A component is a well-defined and independent piece of our app’s UI. A chat window, a button, a slider are all components. Components can also be composed of smaller components and fragments. Each is a building block.

This approach gave birth to a new form of modularity named **CDD**, or **Component Driven Development**. By understanding CDD and how to leverage it, we can use components to drive the development of our apps, to benefit from the advantages brought to us in this newfound modularity.

looking forward [into a world of web-components](https://hackernoon.com/7-frontend-javascript-trends-and-tools-you-should-know-for-2020-fb1476e41083), CDD becomes a standardized method for developing the frontEnd of our applications.

### UI Component Driven Development

Simply put, component-driven development means designing your [software applications](https://en.wikipedia.org/wiki/Component-based_software_engineering) by building loosely-coupled independent components. Each component has an interface to communicate with the rest of the system, and multiple components are composed together into a modular application.

When building a React application, for example, this means building your components first as the base of your application, then moving up to compose larger parts of your UI such as entire pages and functionalities in your app.

The CDD approach correlates with principles such as [Atomic Design](http://bradfrost.com/blog/post/atomic-web-design/) \(see: [Atomic design in React: simplify a complex UI](https://blog.bitsrc.io/simplify-complex-ui-by-implementing-the-atomic-design-in-react-with-bit-f4ad116ec8db)\) and [micro-frontends](https://micro-frontends.org/).

CDD helps you separate the development into components. Each is designed independently from the rest of your app and is built to communicate with it. Designing each component as a standalone unit brings useful advantages.

[Addy Osmani](https://dev.to/giteden/undefined) lays out some key benefits for CDD in his [FIRST principles](https://addyosmani.com/first/):

* **Faster development**: Separating development into components lets you build modular parts with narrowly-focused APIs. This means it’s faster to build each component and learn when it’s good enough.
* **Simpler maintenance**: When you need to modify or update a part of your application, you can extend or update the component instead of having to refactor larger parts of your application. Think of it as performing surgery on a specific organ rather than on a whole system of the body.
* **Better reusability**: Through the separation of concerns components can be reused and extended to build multiple application instead of having to rewrite them over and over again \(see: [Sharing \(components\) is caring](https://blog.bitsrc.io/sharing-components-is-caring-f8235cf1a0c)\).
* **Better TDD**: When building modular components it becomes much easier to implement unit-tests to validate the focused functionality of each component. Larger systems can be more easily tested as it’s easier to understand and separate the responsibilities of every part of the system.
* **Shorter learning curves**: When a developer has to dive into a new project, it’s much easier to learn and understand the structure of a defined component than dive into an entire application.
* **Better modeling of the system**: When a system is composed out of modular components, it’s easier to grasp, understand and operate on.

### Tools for Component Driven Development

When components drive development, dedicated tools are needed for developing, testing, sharing and collaborating on components.

In particular, it is important to develop and test components in isolation, to make sure they work as standalone units to be used in your applications. It’s also important to provide reusability and shareability for the components, so you don’t have to re-invent the wheel every time you need a component.

Here are a few useful tools that can help with your CDD workflow. In the next section, we'll discuss recommended architectures for CDD implementation.

#### Component development and collaboartion: Bit

[Bit](https://bit.dev/) is [an open-source tool](https://github.com/teambit/bit) built essentially for component-driven development. It helps you develop, collaborate and build with components.

Bit can be used to virtually isolate components you’re developing in your application or library. Bit encapsulates components with all their files and dependencies, in a single CLI command, and lets you develop and test the virtual representation of the encapsulated components in isolation.

This means a component is written in your app suddenly becomes bundled, encapsulated and ready to be put to use \(and test\) outside your application.

Then, bit lets you pack the bundled and encapsulated components and [share them to the cloud](https://blog.bitsrc.io/meet-bits-atomic-component-cloud-521160de4f0c). There, your team can visually explore and discover all your shared components. With nearly 50K developers in the community, you can find thousands of open source components shared by other people too.

[![CDD: Build with components](https://res.cloudinary.com/practicaldev/image/fetch/s---X9dV56u--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://cdn-images-1.medium.com/max/2708/1%2A2ns2l6w5Jn8zrnWoDXRVng.png)](https://res.cloudinary.com/practicaldev/image/fetch/s---X9dV56u--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://cdn-images-1.medium.com/max/2708/1%2A2ns2l6w5Jn8zrnWoDXRVng.png)_CDD: Build with components_

[From the component cloud](http://https%3B//bit.dev), your team can install components in new applications, and even suggest updates right from the new projects consuming the components. Bit extends Git to track and sync changes to component’s source code in different projects, so you can gain control over changes and updates.

Since Bit defines each component’s entire dependency graph, when you update components you learn exactly which dependant component will be affected and might break when you make changes. This means a full-blown component-driven development experience, from development to testing, sharing and collaborating on components across apps and people.

[![Component Driven Development through the cloud](https://res.cloudinary.com/practicaldev/image/fetch/s--THtjOwOv--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://cdn-images-1.medium.com/max/2000/1%2AoUT51MUi1WjuYh4jv_gSdA.jpeg)](https://res.cloudinary.com/practicaldev/image/fetch/s--THtjOwOv--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://cdn-images-1.medium.com/max/2000/1%2AoUT51MUi1WjuYh4jv_gSdA.jpeg)_Component Driven Development through the cloud_

Another useful advantage is that tour team can do more than just explore all your components in one place: Developers can actually use the components they find right off the shelf, and even suggest updates.

Designers, product and everyone else gets on the same page while collaborating on the actual source code, in a visual playground view. The gap between design and development shortens, and everybody wins. Especially your users, which will expirience less inconsistency and confusing mistakes.

**Learn**:

* “[Meet Bit’s shared component cloud](https://medium.com/p/521160de4f0c/edit)”
* [“How to share React component between apps with Bit](https://blog.bitsrc.io/how-to-easily-share-react-components-between-projects-3dd42149c09)”
* “[Build a supermodular Todo App with React and Bit](https://blog.bitsrc.io/build-a-super-modular-todo-app-with-react-and-bit-components-aa06bbac4084)”.

#### UI component explorers: StoryBook and Styleguidist

Storybook and Styleguidist are environments for rapid UI development in React. Both are great tools for speeding the development of your components.

Here’s a short rundown.

[StoryBook](https://storybook.js.org/) — Interactive UI component dev & test: React, React Native, Vue, Angular  
\([https://github.com/storybooks/storybook](https://github.com/storybooks/storybook)\)

[Storybook](https://github.com/storybooks/storybook) is a rapid development environment for UI components.

It allows you to browse a component library, view the different states of each component, and interactively develop and test components.

[![](https://res.cloudinary.com/practicaldev/image/fetch/s--z0EPfJd9--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://cdn-images-1.medium.com/max/4312/1%2A8T0opytn0oYuEMpd8PRTsw.gif)](https://res.cloudinary.com/practicaldev/image/fetch/s--z0EPfJd9--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://cdn-images-1.medium.com/max/4312/1%2A8T0opytn0oYuEMpd8PRTsw.gif)

StoryBook helps you develop components in isolation from your app, which also encourages better reusability and testability for your components.

You can browse components from your library, play with their properties and get an instant impression with hot-reload on the web. You can find some popular examples [here](https://storybook.js.org/examples/).

Different plugins can help make your development process even faster, so you can shorten the cycle between code tweaking to visual output. StoryBook also supports [React Native](https://facebook.github.io/react-native/) and [Vue.js](https://vuejs.org/).

React [Styleguidist](https://github.com/styleguidist/react-styleguidist) is a component development environment with hot reloaded dev server and a living style guide that lists component propTypes and shows editable usage examples based on .md files.

[![](https://res.cloudinary.com/practicaldev/image/fetch/s--9Z5q4jcs--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://cdn-images-1.medium.com/max/2412/1%2A9V2nSEgH1VUbmXd5Dq-hnA.gif)](https://res.cloudinary.com/practicaldev/image/fetch/s--9Z5q4jcs--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://cdn-images-1.medium.com/max/2412/1%2A9V2nSEgH1VUbmXd5Dq-hnA.gif)

It supports ES6, Flow and TypeScript and works with Create React App out of the box. The auto-generated usage docs can help Styleguidist function as a visual documentation portal for your team’s different components.

* Also check out [\*\*React Live](https://github.com/FormidableLabs/react-live)\*\* by Formidable Labs.

**Differences between StoryBook and StyleGuidist**

With Storybook you write _stories_ in JavaScript files. With Styleguidist you write _examples_ in Markdown files. While Storybook shows one variation of a component at a time, Styleguidist can show multiple variations of different components. Storybook is great for showing a component’s states, and Styleguidist is useful for documentation and demos of different components.

### Architectures of Component Driven Development

CDD implies that you build your components first, as independently as possible from the rest of the app. This means you are not just building a set of components, you are also implementing a [UI component design system](https://blog.bitsrc.io/building-a-consistent-ui-design-system-4481fb37470f).

You can implement the components as part of the application itself \(i.e. in the same project\), or as a separate reposiotry \(i.e. a component library\). Tools like [Bit](https://bit.dev/) lets you isolate and encapsulate each component, so it can be developed, tested, reused and even updated anywhere- regardless of where it’s written.

When it comes to designing components first, you want to make them reusable to build you different apps. So, you should understand how you are going to make them reusable. Nothing worse than spending 6 months building [a library nobody ends up using](https://blog.bitsrc.io/do-we-really-use-reusable-components-959a252a0a98). Yes, it happens to many teams.

#### Why build a library?

So here’s the truth. Git repositories were not built for atomic components shared between projects. Neither were package managers. Both were built, well, for repositories. Components are not repositories.

[![](https://res.cloudinary.com/practicaldev/image/fetch/s--fos8GWVP--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://cdn-images-1.medium.com/max/2000/1%2AZ6sxp1OBjNRt9SEUvKljSw.jpeg)](https://res.cloudinary.com/practicaldev/image/fetch/s--fos8GWVP--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://cdn-images-1.medium.com/max/2000/1%2AZ6sxp1OBjNRt9SEUvKljSw.jpeg)

That’s why when we want to take a component in our app and use it in another app, we’d have to create a new reposiotry. To save overhead, most teams create one shared reposiotry to host 20–30 components.

If using Bit, you might not need a library. You can just share the components from the apps directly to your cloud, and install them in other projects. It’s kind of like the difference between a CD music album and Spotify. But, you can use Bit and StoryBook with a shared library too, so no worries.

When designing the library you should make a few key decisions. A few key principles will guide you through, and here’s the gist: you want to develop independent components. The rest is should be a lego-like composition. Otherwise, things will hit the wall the first time somebody needs something different than what you’ve defined in your library. Then, they won’t use it.

Let’s say you do build a library… here is some solid advice.

### 7 Keys to building a good CDD oriented UI library

[![](https://res.cloudinary.com/practicaldev/image/fetch/s--Ibln6HRc--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://cdn-images-1.medium.com/max/2000/1%2A-xfmjoUi0rWe52Gje-3QJw.jpeg)](https://res.cloudinary.com/practicaldev/image/fetch/s--Ibln6HRc--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://cdn-images-1.medium.com/max/2000/1%2A-xfmjoUi0rWe52Gje-3QJw.jpeg)

1. **Standards** — What are the dev standards in your library? Where are the components? Where are the tests? The styling? What’s your stack \(are you going to use TS for example\)? How are the components divided? is “Table” made of “Row” and “Cell”? Is “tabs” made of “tab” and etc…? You get it. It’s **very important** to involve designers in this process too, to make sure your library will be flexible enough to meet their future requirements too.
2. **Styling** - How will you [style the components](https://blog.bitsrc.io/5-ways-to-style-react-components-in-2019-30f1ccc2b5b)?\*\* \*\*Will you couple the CSS to every component? If so, what happens when a designer needs to change something only for a different app? Perhaps, use [CSS in JS libraries](https://blog.bitsrc.io/9-css-in-js-libraries-you-should-know-in-2018-25afb4025b9b) to better decouple them? If using [bit.dev](https://bit.dev/), you can separate the themes as independent components which can be composed with the logic components, so you can compose the right logic and style in every app. Maximum flexibility through modularity, nice right?
3. **Testing** - How will you [test components in your library](https://blog.bitsrc.io/7-react-testing-libraries-you-should-know-b20ca97422a4)? Jest and Enzyme? You better check thoroughly before choosing the right combo of framework+utility+tools, to make sure your testing isn’t getting in the way, and insteads provides valuable data to aid in your CDD. Unit tests are nice, but should test the functional API of components and not implementation details. Integration and end-to-end tests are just as important. Bit makes TDD a driving force in CDD. It lets you instantly bundle, encapsulate and test components in isolation outside of your app’s context, to validate their independence. When you update a component, you can also learn which dependant components might break as a result. In the cloud, component unit-test results are a key factor in discoverability.
4. **Build process** - Code needs to be compiled. How will you define a build process for your library? A release mechanism? Just copy-paste that of your app into the library \(might work though\)? Define build configurations for every component \(Lerna\) so it can be published? Use Bit to define a compiler applied to all \(or some\) individual components? If you complicate things too much, the development will become painful, modularity will be impaired and the learning curve for a PR will be annoying.
5. **Ownership** - Who owns the library? Larger organizations often have a frontEnd infra team and sometimes an architect. These are building a product called a shared library. Other frontEnd teams building apps in the organization are consumers. Then, it becomes very important to create discoverability for them \(Bit, StoryBook\), and even more so to let them suggest updates \(Bit\). Otherwise, consuming-developers won’t want to couple their app to the library and wait on a PR \(which may or may not come\) for every pull request. Don’t enforce, collaborate. If you won’t, people will just copy-paste code and nobody will know. And it's your fault. If you’re a smaller team, define a clear owner. Even if nobody is working on it full time, define 1–3 maintainers. The rest will PR, just like GitHub.
6. **Discoverability** - A library isn’t of much use of people can’t easily find components, learn how they work and put them to use in their code. If you share components to [bit.dev](https://bit.dev/), you [get discoverability out of the box](https://bit.dev/components) for your library: component search, visual previews, label tags, live playground, examples, API reference extracted from the code and test results. Then you get an all-in-one portal for searching, choosing and using components. If not \(or on top of it\), you can add a storybook docs portal and/or your own website to document components. [Codesandbox](https://codesandbox.io/) is also useful.
7. **Collaboration** - What happens when another developer \(maybe in another team or another county\) needs to change something on a component in your library? will they have to dive in for a PR to your repo, cross fingers and wait? For many, this is too much pain, and they might not adopt it even if you try forcing them too. Instead, allow any developer to develop and suggest updated to the components, to be reviewed by you \(and the designers\). Using Bit, the developers can do that right from their own projects without having to setup anything or wait on a PR. It’s better to know what people are doing and communicate than having them copy-pasting code and changing it in their apps without you even knowing,

**Remember** — a library is just another repo set to share some components between two repos. They don’t scale or age well, and suffer from additional overhead and tooling. It’s often better to just [share components directly between your applications through the cloud](https://blog.bitsrc.io/meet-bits-atomic-component-cloud-521160de4f0c).

### Benefits of CDD for dev teams

[![](https://res.cloudinary.com/practicaldev/image/fetch/s--LadA_QQR--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://cdn-images-1.medium.com/max/2000/1%2AqbDzKo9cg7oTnoERAodd6Q.png)](https://res.cloudinary.com/practicaldev/image/fetch/s--LadA_QQR--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://cdn-images-1.medium.com/max/2000/1%2AqbDzKo9cg7oTnoERAodd6Q.png)

When leveraging CDD development teams enjoy faster development times, more code reuse, better TDD and a unified consistent UI design system.

People can code with access to components already written, and collaborate on changes. New features or apps just means adjusting and tweaking your base components, and preventing mistakes later discovered in production.

Codesharing also means less code to maintain, so you can focus on building new things. When you build from the components up, you also get everyone aligned on the same page using the same building blocks, so your entire development workflows become standardized and yet remain flexible.

Some teams report up to 60% faster development through modular components based on a UI component design system implemented as React components. Some organization find they can delete ~30% of their codebase by adopting CDD. [Uber, Airbnb, Shopify](https://blog.bitsrc.io/building-a-consistent-ui-design-system-4481fb37470f) & more are moving to components.

### Conclusion

Personally, I don’t think it’s surprising that CDD5 is more effective. As [Brad Frost](https://dev.to/giteden/undefined) states in Atomic Design, modularity and composition are the basis for efficiency in physics, biology, economy and much more. In software, modularity breeds the same advantages: speed, reliability, simplicity, reusability, testability, extendability and composability. It’s better.

In the frontEnd of our applications, through CDD we also give [a consistent UI and expirience](https://blog.bitsrc.io/building-a-consistent-ui-design-system-4481fb37470f) for our users throughout our products and features. That makes them love what we build, and feel a bit happier. Everybody wins.

Thanks for reading! 🍻

