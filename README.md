# Namaste React Akshay Saini Assignment
**-What is 'NPM'?**
  *   **Short:** Node Package Manager. A command-line tool and online registry for JavaScript software packages (libraries/modules).
  *   **Analogy:** An app store for code. You can "install" code libraries written by others into your project.
  *   **JS Example (Command Line):** `npm install react` (installs the React library)
  *   **Best Example:** Managing all the external code your project depends on, like React, Lodash, date-fns.

**-What is 'Parcel/Webpack'? Why do we need it?**
  *   **Short:** They are **module bundlers**. They take all your project's JavaScript files, CSS, images, etc., and combine/optimize them into a few files (often one JS and one CSS) that browsers can understand efficiently.
  *   **Why:** Modern web apps are split into many small files (modules) for organization. Browsers don't efficiently handle hundreds of small files. Bundlers also perform optimizations like minification (making files smaller) and transpilation (converting new JS to older JS).
  *   **Analogy:** A chef (bundler) takes many raw ingredients (your code files, images, CSS) from your pantry and expertly cooks and plates them into a single, delicious, and easily digestible meal (the bundled output file) for your guest (the browser).
  *   **JS Example (Conceptual - not direct code):** You write `import MyButton from './Button.js';`. The bundler finds `Button.js`, includes its code, and makes `MyButton` available.
  *   **Best Example:** Building a production-ready React/Vue/Angular application from many component files, SCSS files, and image assets.

**-What is parcel-cache**
  *   **Short:** A directory (`.parcel-cache`) where Parcel stores intermediate build results.
  *   **Why:** To speed up subsequent builds. Parcel doesn't have to re-process everything from scratch if files haven't changed.
  *   **Analogy:** A chef's prep station. If they chopped onions yesterday and have some left over (and they're still good), they'll use those instead of chopping new ones, saving time.
  *   **Best Example:** During development, when you save a file, Parcel rebuilds much faster because it reuses cached information for unchanged parts of your project.

**-What is npx' ?**
  *   **Short:** Node Package eXecutor. A tool that comes with NPM to execute Node.js packages either from the local `node_modules/.bin` directory or by temporarily downloading and running them from the NPM registry.
  *   **Analogy:** Renting a specific tool for a one-time job instead of buying it and keeping it in your garage. Or, asking your local project's "foreman" to run a tool it already has.
  *   **JS Example (Command Line):** `npx create-react-app my-app` (downloads and runs `create-react-app` without installing it globally).
  *   **Best Example:** Running CLI tools like `create-react-app`, `tailwindcss init`, or local project scripts without global installation or complex path configurations.

**-What is difference between dependencies vs devDependencies'**
  *   **Short:**
      *   `dependencies`: Packages required for your application to run in production (e.g., React, Lodash).
      *   `devDependencies`: Packages only needed during development and testing (e.g., Jest for testing, ESLint for linting, Webpack/Parcel itself).
  *   **Analogy:**
      *   `dependencies`: The engine, wheels, and seats of a car – essential for it to drive and function.
      *   `devDependencies`: The tools in the mechanic's workshop (wrenches, diagnostic machines) – needed to build and maintain the car, but not part of the car itself when it's on the road.
  *   **JS Example (`package.json`):**
      ```json
      {
        "dependencies": {
          "react": "^18.0.0"
        },
        "devDependencies": {
          "jest": "^29.0.0",
          "parcel": "^2.8.0"
        }
      }
      ```
  *   **Best Example:** `react` and `react-dom` are `dependencies`. `eslint`, `prettier`, `jest`, and `webpack` are `devDependencies`.

**-What is Tree Shaking?**
  *   **Short:** A dead code elimination process used by bundlers like Webpack and Parcel. It removes unused code from your final bundle.
  *   **Analogy:** Packing for a trip. You lay out all your clothes (your codebase and libraries), but tree shaking only puts the clothes you'll actually wear (the code that's used) into your suitcase (the final bundle), leaving the rest behind.
  *   **Best Example:** If you import a utility library like Lodash but only use one function (`_.debounce`), tree shaking ensures only `_.debounce` (and its internal dependencies) are included in the final build, not the entire Lodash library.

**-What is Hot Module Replacement?**
  *   **Short:** A feature of bundlers (like Webpack/Parcel) that allows modules to be updated in a running application *without* a full page reload, often while preserving application state.
  *   **Analogy:** Changing a single Lego brick in a large Lego model without having to take the whole model apart and rebuild it. The rest of the model stays intact.
  *   **Best Example:** Editing a CSS file and seeing the style changes instantly in the browser without losing the current state of your React components (e.g., form input values, open modals).

**-List down your favourite 5 superpowers of Parcel and describe any 3 of them in your own words.**
  1.  **Zero Configuration:**
  2.  **Blazing Fast Builds:** (especially with caching)
  3.  **Out-of-the-box Asset Handling:** (JS, CSS, HTML, images, etc.)
  4.  **Hot Module Replacement (HMR):**
  5.  **Automatic Code Splitting:**

  *   **Descriptions:**
      1.  **Zero Configuration:** You can point Parcel at your HTML file, and it figures out almost everything else (JS, CSS, image imports) without needing a complex config file. It's like a smart assistant that just *knows* how to assemble your project.
      2.  **Out-of-the-box Asset Handling:** Parcel understands common web assets like CSS, SCSS, images, and even file types like Rust or ReasonML by default. It's like a universal adapter that can connect many different types of plugs.
      3.  **Hot Module Replacement (HMR):** When you change a piece of your code (like a React component or a CSS rule), Parcel can inject that change directly into the running app in your browser without a full refresh. This is like a pit crew changing a tire on a race car while it's still on the track, making your development feedback loop incredibly fast.

**-What is' gitignore? What should we add and not add into it?**
  *   **Short:** A file named `.gitignore` that tells Git which untracked files or directories to ignore. Git won't track them or let you commit them.
  *   **Analogy:** A "Do Not Disturb" list for your project's version control. You tell Git, "Hey, don't pay attention to these specific files or folders."
  *   **What to add (ignore):**
      *   `node_modules/` (can be regenerated from `package.json`)
      *   Build output folders (e.g., `dist/`, `build/`)
      *   Cache folders (e.g., `.parcel-cache/`, `.webpack-cache/`)
      *   Environment files with secrets (e.g., `.env`)
      *   OS-generated files (e.g., `.DS_Store` on macOS, `Thumbs.db` on Windows)
      *   Log files, editor-specific config files.
  *   **What NOT to add (i.e., what to track):**
      *   Your source code (e.g., `.js`, `.jsx`, `.html`, `.css`, `.scss` files you wrote)
      *   `package.json` and `package-lock.json` (or `yarn.lock`)
      *   Project configuration files (e.g., `babel.config.js`, `tailwind.config.js`)
      *   The `.gitignore` file itself!
  *   **Best Example:** Always add `node_modules/` to `.gitignore`.

**-What is the difference between package.json' and package-lock.json***
  *   **Short:**
      *   `package.json`: Your project's manifest. Lists dependencies (often with version ranges like `^1.2.3`), scripts, project name, version, etc.
      *   `package-lock.json`: Records the *exact* versions of every package that was installed, including sub-dependencies. Ensures consistent installs across different machines/times.
  *   **Analogy:**
      *   `package.json`: Your shopping list ("I need milk, about 1 liter, any good brand"). It describes what you generally want.
      *   `package-lock.json`: The detailed store receipt after you've shopped ("BrandX Milk, 1.05L, purchased 2023-10-27, batch #XYZ"). It records exactly what you got.
  *   **Best Example:** `package.json` might say `"lodash": "^4.17.0"`. `package-lock.json` will specify the exact version, like `"lodash": "4.17.21"`, and also the exact versions of all of Lodash's own dependencies.

**-Why should I not modify 'package-lock.json'?**
  *   **Short:** It's auto-generated by NPM/Yarn to guarantee reproducible builds. Manual edits can break this guarantee and lead to "it works on my machine" problems.
  *   **Analogy:** You shouldn't scribble on the detailed store receipt. If you do, and then try to return an item or re-buy the exact same things, the store (NPM) might get confused or give you something different. Let the cashier (NPM) generate the receipt.
  *   **Best Example:** If you manually change a version in `package-lock.json`, a teammate running `npm install` might get a different set of sub-dependencies than you, potentially leading to bugs.

**-What is 'node_modules? Is it a good idea to push that on git?**
  *   **Short:** The directory where NPM downloads and stores all your project's dependencies (both `dependencies` and `devDependencies`).
  *   **Is it a good idea to push to Git?:** **NO.**
      *   It can be very large.
      *   It can be easily regenerated by running `npm install` using `package.json` and `package-lock.json`.
      *   It can contain platform-specific binaries that might not work on other developers' machines.
  *   **Analogy:** `node_modules` is like the actual physical books you borrowed from a library based on your `package.json` (list of books) and `package-lock.json` (specific editions). You don't mail all the physical books to your collaborator; you just mail them the list and specific edition numbers, and they get their own copies from their local library.
  *   **Best Example:** A project with even a few dependencies can have a `node_modules` folder that's hundreds of megabytes with thousands of files. Committing this bloats your repository.

**-What is the 'dist' folder?**
  *   **Short:** "Distribution" folder. This is the standard name for the directory where your bundler (Webpack, Parcel) outputs the final, optimized, and bundled files ready for deployment to a web server.
  *   **Analogy:** The packaged product ready for shipping. After the chef (bundler) has cooked the meal (processed your code), the `dist` folder is the take-out container with the finished meal, ready to be delivered to the customer (web server/browser).
  *   **Best Example:** After running `npm run build` (which often invokes Parcel or Webpack), you'll find `index.html`, `bundle.js`, `styles.css`, etc., in the `dist` folder. This is what you upload to your web host.

**-What is 'browserslist'**
  *   **Short:** A configuration used by tools like Babel (for JS transpiling) and Autoprefixer (for CSS vendor prefixes) to determine which browsers your project needs to support.
  *   **Analogy:** A list of languages you need a document translated into. Based on this list, the translator (Babel/Autoprefixer) will ensure the final document is understandable by speakers of those specific languages (target browsers).
  *   **JS Example (in `package.json`):**
      ```json
      "browserslist": [
        ">0.2%",
        "not dead",
        "not op_mini all"
      ]
      ```
  *   **Best Example:** If your `browserslist` includes `IE 11`, Babel will transpile modern JavaScript features (like arrow functions) into older syntax that IE 11 understands.

**-dif bundlers: vite, webpack, parcel**
  *   **Short:**
      *   **Webpack:** Highly configurable, mature, vast ecosystem. Can be complex to set up.
      *   **Parcel:** Focuses on zero-to-low configuration, very developer-friendly, fast.
      *   **Vite:** Extremely fast development server using native ES modules. Uses Rollup for production builds. Modern and gaining popularity.
  *   **Analogy:**
      *   **Webpack:** A professional chef's kitchen with every imaginable tool and appliance. Powerful, can make anything, but requires expertise to set up and use effectively.
      *   **Parcel:** A smart, all-in-one kitchen appliance. Easy to use, figures out most things for you, great for common meals.
      *   **Vite:** A high-tech food replicator for daily meals (development) that's incredibly fast, and then uses a very efficient professional packer (Rollup) for when you need to ship food long-distance (production).
  *   **Best Examples:**
      *   **Webpack:** Large, complex enterprise applications where fine-grained control over the build process is crucial.
      *   **Parcel:** Quick prototypes, smaller to medium projects, or when you want to get started quickly without config overhead.
      *   **Vite:** New React/Vue/Svelte projects where fast dev server startup and HMR are priorities.

**-caret and ~ - tilda (in package.json versions)**
  *   **Short:** Version range specifiers in `package.json`.
      *   `~` (Tilde): Allows patch updates. `~1.2.3` will accept `1.2.4`, `1.2.9`, but NOT `1.3.0`.
      *   `^` (Caret): Allows minor and patch updates, as long as the leftmost non-zero digit doesn't change. `^1.2.3` will accept `1.2.4`, `1.3.0`, `1.9.9`, but NOT `2.0.0`.
  *   **Analogy:**
      *   **Tilde (`~1.2.3`):** "Give me version 1.2, and any tiny bug fixes for it (like 1.2.4), but don't change the features (not 1.3.0)."
      *   **Caret (`^1.2.3`):** "Give me version 1, and any backward-compatible improvements or bug fixes (like 1.2.4 or 1.3.0), but not a major rewrite that might break things (not 2.0.0)."
  *   **Best Example:**
      *   `~` is safer if you are very sensitive to even minor API changes.
      *   `^` is more common, as it allows beneficial non-breaking updates while protecting against breaking changes (assuming semantic versioning is followed by the library).

**-Script types in html (MDN Docs)**
  *   **Short:** The `type` attribute on a `<script>` tag tells the browser how to interpret the script content.
  *   **Common Values:**
      *   `text/javascript` (or omitted): Default. Standard JavaScript.
      *   `module`: Treats the script as an ES module, allowing `import`/`export` syntax.
      *   `application/json`: Embeds JSON data. Not executable.
      *   `application/ld+json`: For structured JSON-LD data.
  *   **Analogy:** Labels on different types of instruction manuals for the browser. "This is a classic script," "This is a modern module script that can import other things," "This is just data, don't run it."
  *   **JS Example:**
      ```html
      <script src="classic.js"></script> <!-- type="text/javascript" is implied -->
      <script type="module" src="app.js"></script> <!-- Uses ES module system -->
      <script type="application/json" id="my-data">
        { "name": "Widget", "version": "1.0" }
      </script>
      ```
  *   **Best Example:** Using `type="module"` for modern JavaScript development to leverage `import` and `export`.

**-JSX**
  *   **Short:** JavaScript XML. A syntax extension for JavaScript, commonly used with React, that allows you to write HTML-like structures in your JavaScript code.
  *   **Analogy:** A special shorthand or blueprint language that looks like HTML but is actually used by JavaScript (specifically, tools like Babel) to create UI elements. It's like writing down cooking instructions in a familiar recipe format, which a chef (Babel) then translates into precise kitchen actions (`React.createElement` calls).
  *   **JS Example:**
      ```jsx
      const element = <h1>Hello, world!</h1>;
      const MyComponent = () => <div><p>This is a component.</p></div>;
      ```
  *   **Best Example:** Defining React components in a declarative and readable way.

**-React.createElement vs JSX**
  *   **Short:**
      *   `React.createElement()`: The actual JavaScript function React uses under the hood to create React elements (objects describing your UI).
      *   JSX: Syntactic sugar that gets transpiled (converted) by tools like Babel into `React.createElement()` calls.
  *   **Analogy:**
      *   JSX: Writing a letter in friendly, conversational English.
      *   `React.createElement()`: The formal, precise language a machine (React) understands, with every instruction explicitly detailed. Babel is the translator.
  *   **JS Example:**
      *   JSX: `const element = <h1 className="greeting">Hello</h1>;`
      *   Equivalent `React.createElement()`:
        ```javascript
        const element = React.createElement(
          'h1',
          { className: 'greeting' },
          'Hello'
        );
        ```
  *   **Best Example:** JSX is almost always preferred for its readability and similarity to HTML when writing React components.

**-Benefits of JSX**
  *   **Readability:** Looks very similar to HTML, making it easier to visualize the UI structure.
  *   **Familiarity:** Easier for developers with HTML/XML experience to pick up.
  *   **Error Checking:** Transpilers like Babel can catch errors like unclosed tags or misspelled HTML attributes (like `class` instead of `className`) at compile time.
  *   **Expressions:** Allows embedding JavaScript expressions directly within the markup using curly braces `{}`.

**-Behind the Scenes of JSX**
  *   **Short:** JSX is not understood by browsers directly. A transpiler (usually Babel) processes your code, finds JSX syntax, and converts it into standard JavaScript calls to `React.createElement()`.
  *   **Analogy:** You write a recipe in shorthand (JSX). Babel (the chef's assistant) rewrites it into a very detailed, step-by-step instruction list (`React.createElement` calls) that the head chef (React) can follow perfectly.

**-Babel & parcel role in JSX**
  *   **Babel:** The primary transpiler that converts JSX syntax into `React.createElement()` calls. It also transpiles modern JavaScript (ES6+) into older JavaScript that more browsers can understand.
  *   **Parcel (or Webpack):** The module bundler. Parcel automatically uses Babel under the hood (often pre-configured) to handle JSX and modern JS transformations as part of its bundling process.
  *   **Analogy:**
      *   Babel: The specialized translator for JSX and modern JS features.
      *   Parcel: The project manager that hires Babel (the translator) to ensure all code is in the correct format before packaging it all up.

**-Components**
  *   **Short:** Reusable, self-contained pieces of UI. They can be thought of as custom HTML elements you define. Components can have their own logic and state.
  *   **Analogy:** Lego bricks. Each brick (component) is a distinct piece. You can use many of the same type of brick, or combine different types of bricks to build a complex structure (your application).
  *   **JS Example (Functional Component):**
      ```jsx
      function Welcome(props) {
        return <h1>Hello, {props.name}</h1>;
      }
      // Usage: <Welcome name="Sarah" />
      ```
  *   **Best Example:** Creating a `<Button>`, `<UserProfileCard>`, or `<NavigationBar>` component that can be reused throughout your application.

**-Functional Components**
  *   **Short:** The simpler way to define React components: JavaScript functions that accept `props` (properties) as an argument and return JSX to describe the UI.
  *   **Analogy:** A simple Lego brick defined by its shape and color (its function and the JSX it returns). It takes some input (props) and produces a piece of UI.
  *   **JS Example:**
      ```jsx
      const Greeting = (props) => {
        return <p>Hello, {props.user}!</p>;
      };
      // Renders: <Greeting user="Alex" />
      ```
  *   **Best Example:** Most components in modern React are written as functional components, especially with the advent of Hooks for state and lifecycle features.

**-Composing Components**
  *   **Short:** Building complex UIs by combining smaller, simpler components. Components can render other components.
  *   **Analogy:** Building a complex Lego castle by connecting many different types of Lego bricks together. A "wall" component might be made of many "brick" components.
  *   **JS Example:**
      ```jsx
      function App() {
        return (
          <div>
            <NavigationBar />
            <MainContent />
            <Footer />
          </div>
        );
      }
      ```
  *   **Best Example:** An `App` component rendering `Header`, `Sidebar`, and `ArticleList` components, where `ArticleList` itself renders multiple `ArticleItem` components.

**-Superpowers of JSX**
  1.  **Readability & Familiarity:** Looks like HTML, making UI structure intuitive.
  2.  **JavaScript Expressions:** Embed any JS expression within `{}` (e.g., `{user.name}`, `{2+2}`, `{isAdmin ? <AdminPanel/> : null}`).
  3.  **Component-Centric:** Designed for building UIs with components, promoting reusability.
  4.  **Safety:** Helps prevent injection attacks (XSS) by default (it escapes string content).
  5.  **Tooling Support:** Great editor support (syntax highlighting, autocompletion) and error checking via Babel.

**-Role of type attribute in script tag? What options can I use there?**
  *   **Short:** The `type` attribute tells the browser how to interpret the script's content.
  *   **Options:**
      *   `text/javascript`: (or omitted) The default for classic JavaScript.
      *   `module`: For ES6+ modules (allows `import`/`export`).
      *   `text/babel` (less common now): Used to indicate code that needs Babel transpilation in the browser (usually for online playgrounds, not production).
      *   `application/json`: For embedding JSON data directly in HTML.
      *   `application/ld+json`: For JSON-LD structured data (SEO).
      *   Other non-standard types can be used for custom templating engines, but the browser ignores them unless specific JS handles them.
  *   **Analogy:** Like a file extension for the browser. `.js` means "JavaScript," `.module.js` could mean "JavaScript Module."
  *   **Best Example:** Using `type="module"` for modern projects to enable JavaScript modules.
      ```html
      <script type="module" src="app.js"></script>
      ```

**-{TitleComponent} vs {<TitleComponent/>} vs {<TitleComponent></TitleComponent>} in JSX**
  *   **`{TitleComponent}`:** This attempts to render the *value* of the variable `TitleComponent`.
      *   If `TitleComponent` is a function/class *itself* (e.g., `const TitleComponent = () => <h1>Title</h1>;`), this will likely cause an error or render nothing useful in React, as React expects elements or primitive values here.
      *   If `TitleComponent` was a variable holding a string, number, or a pre-rendered React element, it would render that value. E.g., `const TitleComponent = "My Page Title"; <div>{TitleComponent}</div>` would render "My Page Title".
  *   **`<TitleComponent/>`:** This is the correct way to render a React component named `TitleComponent`. It's a self-closing tag, used when the component doesn't have any children.
  *   **`<TitleComponent></TitleComponent>`:** Also a correct way to render a React component. This form is used when `TitleComponent` needs to accept child elements between its opening and closing tags (accessible via `props.children`).

  *   **Analogy:**
      *   `{TitleComponent}`: Trying to display the blueprint paper itself instead of building from it. Or, displaying a variable's simple text content.
      *   `<TitleComponent/>`: Telling React, "Build and display an instance of the `TitleComponent` blueprint." (like a self-contained Lego piece).
      *   `<TitleComponent>...</TitleComponent>`: "Build `TitleComponent` and put these other Lego pieces (children) inside it."

  *   **JS Example:**
      ```jsx
      const TitleString = "My Awesome Title";
      const TitleComponent = () => <h1>My Component Title</h1>;
      const AnotherComponent = ({ children }) => <div>{children}</div>;

      function App() {
        return (
          <div>
            {/* Renders the string "My Awesome Title" */}
            <p>{TitleString}</p>

            {/* Correctly renders the TitleComponent */}
            <TitleComponent />

            {/* Correctly renders AnotherComponent with a child */}
            <AnotherComponent>
              <p>This is a child</p>
            </AnotherComponent>

            {/* This would likely error or render nothing useful in React */}
            {/* {TitleComponent}  <-- Not how you render a component by name */}
          </div>
        );
      }
      ```

**-What converts New Code to Older Code(For older version Browsers)?**
  *   **Short:** A **transpiler**, most commonly **Babel**.
  *   **Analogy:** A translator who takes a modern English novel (new JS code with ES6+ features) and rewrites it into older, more classical English (ES5 JS code) so that people who only understand classical English (older browsers) can read it.
  *   **Best Example:** Babel converting an arrow function `const add = (a, b) => a + b;` into a traditional function `var add = function(a, b) { return a + b; };` for compatibility with older browsers like IE11.

**-React-key Reconciliation**
  *   (Covered by "Why we need keys" and "Reconciliation")
  *   **Short:** Keys help React identify which items in a list have changed, been added, or removed. This allows React's reconciliation algorithm to efficiently update the UI. Without keys, React might have to re-render entire lists or make incorrect assumptions about element identity.

**-Is JSX HTML inside JS?**
  *   **Short:** No, not exactly. It *looks* like HTML and is designed to be familiar, but it's a **syntax extension for JavaScript**. It gets transformed into JavaScript function calls (`React.createElement`) by a transpiler (like Babel) before it's understood by the JavaScript engine.
  *   **Analogy:** It's like writing a recipe using cooking-specific shorthand (JSX) within a larger instruction manual (JavaScript). The shorthand needs to be expanded into full, explicit instructions (JavaScript function calls) before the chef (JavaScript engine) can understand it.

**-Diff between React Element & React Component**
  *   **React Element:** A plain JavaScript object that describes what you want to see on the screen. It's a lightweight description of a DOM node or another component. React elements are immutable.
      *   Example: `{ type: 'h1', props: { className: 'greeting', children: 'Hello' } }`
  *   **React Component:** A blueprint or template for creating React elements. It's a function or a class that optionally accepts input (props) and returns a React element (or another component).
      *   Example: `function Welcome(props) { return <h1>Hello, {props.name}</h1>; }`
  *   **Analogy:**
      *   **Component:** A cookie cutter (the blueprint/template).
      *   **Element:** The actual cookie (the description of what to create). You use the cookie cutter (Component) to make cookies (Elements).
  *   **Best Example:**
      ```jsx
      // Component (function)
      function Greeting(props) {
        return <p>Hello, {props.name}</p>; // Returns a React Element
      }

      // Element (object created by JSX, then by React.createElement)
      const greetingElement = <Greeting name="Alice" />; // This JSX describes an element
      // React internally: React.createElement(Greeting, { name: "Alice" })
      ```

**- Is JSX mandatory for React?**
  *   **Short:** No. You can write React applications entirely using `React.createElement()` calls.
  *   **Analogy:** You can write a book using only very formal, precise language (`React.createElement`), but it's often easier and more readable to use a more conversational style with some accepted shorthand (JSX).
  *   **Best Example:** While not mandatory, JSX is almost universally used because it makes code much more readable and maintainable. Writing complex UIs with `React.createElement` directly is verbose and error-prone.

**- Is ES6 mandatory for React?**
  *   **Short:** No, you could technically write React with ES5. However, modern React development heavily relies on ES6+ features (like classes for class components (though less common now), arrow functions, destructuring, `let`/`const`, modules).
  *   **Analogy:** You *could* build a modern car using only tools from the 1950s, but it would be much harder and less efficient than using modern tools and techniques (ES6+).
  *   **Best Example:** Using arrow functions for concise component definitions, destructuring props, and `import`/`export` for module management are standard ES6+ features in React.

**- How can I write comments in JSX?**
  *   **Short:** Inside curly braces, using JavaScript block comment syntax: `{/* This is a comment */}`.
  *   **Analogy:** Writing a little side note on your blueprint, enclosed in special markers so it's not mistaken for part of the building instructions.
  *   **JS Example:**
      ```jsx
      function MyComponent() {
        return (
          <div>
            {/* This heading is important */}
            <h1>Welcome</h1>
            <p>Some content here.</p> {/* Another comment */}
          </div>
        );
      }
      ```

**- What is < React. Fragment > </React.Fragment> and <></> ?**
  *   **Short:** They allow you to group multiple React elements without adding an extra, unnecessary wrapper DOM node (like a `<div>`). `<></>` is the shorthand syntax for `<React.Fragment>`.
  *   **Analogy:** An invisible container or a way to bundle multiple items together when you're giving them to someone, but you don't want to put them in an actual physical box that they'll see.
  *   **JS Example:**
      ```jsx
      // Before Fragments, you might need an extra div:
      // return (
      //   <div>
      //     <td>Hello</td>
      //     <td>World</td>
      //   </div>
      // );

      // With Fragment (long form):
      return (
        <React.Fragment>
          <td>Hello</td>
          <td>World</td>
        </React.Fragment>
      );

      // With Fragment (short syntax):
      return (
        <>
          <td>Hello</td>
          <td>World</td>
        </>
      );
      ```
  *   **Best Example:** Returning multiple elements from a component's render method, especially when HTML structure rules would be broken by an extra `div` (e.g., direct children of `<table>`, `<select>`).

**- What is Virtual DOM?**
  *   **Short:** An in-memory representation, or a "copy," of the actual browser DOM. React uses it to improve performance. When state changes, React updates the Virtual DOM first, calculates the minimal changes needed, and then efficiently updates only those parts of the real DOM.
  *   **Analogy:** A blueprint of a house. Before making actual, costly changes to the physical house (real DOM), you first mark all the changes on the blueprint (Virtual DOM). Then, you compare the old blueprint with the new one to find the most efficient way to apply only the necessary changes to the real house, saving time and effort.
  *   **Best Example:** When a list of 100 items updates and only one item changes, React's use of the Virtual DOM helps it identify and re-render only that single item in the real DOM, instead of re-rendering all 100.

**- What is Reconciliation in React?**
  *   **Short:** The process React uses to compare the previous Virtual DOM tree with the new Virtual DOM tree (after a state or prop update) to determine the minimum number of changes needed to update the actual browser DOM.
  *   **Analogy:** Playing a "spot the difference" game between two pictures (the old VDOM and the new VDOM). React figures out the fewest edits (add, remove, update) to make the first picture look like the second, and then applies those edits to the real display.
  *   **Best Example:** When state changes, React re-renders the component, generating a new VDOM tree. The reconciler then "diffs" this new tree against the previous one and tells React DOM precisely which parts of the actual DOM need to be updated.

**- What is React Fiber?**
  *   **Short:** A complete reimplementation of the React core algorithm (the reconciler). It was introduced in React 16 to enable more advanced features like incremental rendering, better scheduling of updates, error boundaries, and improved perceived performance.
  *   **Analogy:** Upgrading the engine and transmission of a car. The car (React) still drives, but the new internal mechanics (Fiber) allow it to handle tasks more smoothly, prioritize urgent tasks (like user input) over less urgent ones (like background updates), and recover better from internal issues. It makes the "driving experience" (UI rendering) smoother.
  *   **Best Example:** Fiber allows React to break rendering work into smaller chunks and pause/resume it. This prevents long rendering tasks from blocking the main thread, leading to a more responsive UI, especially for complex animations or data updates.

**- Why we need keys in React? When do we need keys in React?**
  *   **Why:** Keys help React identify which items in a list have changed, are added, or are removed. They give each element a stable identity across re-renders. This allows React to efficiently update and reorder list items without losing their state or unnecessarily re-creating DOM nodes.
  *   **When:** You need keys whenever you are rendering a list of elements (e.g., mapping an array to JSX elements).
  *   **Analogy:** Imagine students lining up. If you don't have name tags (keys) and one student leaves, you might assume everyone after them shifted, potentially misidentifying them. With name tags (keys), even if students reorder or someone leaves/joins, you can still correctly identify "Alice" because her name tag hasn't changed.
  *   **Best Example:**
      ```jsx
      function TodoList({ todos }) {
        return (
          <ul>
            {todos.map(todo => (
              // `todo.id` should be a unique and stable identifier
              <li key={todo.id}>{todo.text}</li>
            ))}
          </ul>
        );
      }
      ```

**- Can we use index as keys in React?**
  *   **Short:** Yes, you *can*, but it's generally **not recommended** if the order of list items can change, or if items can be inserted/deleted from the middle of the list. It's acceptable for static lists that never reorder.
  *   **Why it's risky:** If you use the array index as a key and an item is added to the beginning or middle of the list, or items are reordered, React will see the keys as having changed for many items (because their indices changed). This can lead to incorrect component state being preserved for the wrong item or inefficient re-renders.
  *   **Analogy:** Using the position in a line as a person's ID. If the first person leaves, the person who was second is now first, getting the "ID" of the person who left. This causes confusion if the ID was tied to specific data or state.
  *   **Best Example of when it's problematic:** A list of input fields where users can add, remove, or reorder items. If you use index as key, and you delete the first item, the second item now gets index 0. If that input had state (e.g., typed text), that state might incorrectly transfer to the new item at index 0.

**- What is props in React? Ways to [pass/use]**
  *   **Short:** "Props" (short for properties) are how components receive data from their parent components. They are read-only within the component that receives them.
  *   **Analogy:** Arguments passed to a JavaScript function. The parent component "calls" the child component and passes data (props) to customize its behavior or content. Or, settings on a Lego brick (e.g., `color="red"`, `size="small"`).
  *   **Ways to Pass/Use:**
      1.  **Passing from Parent:**
          ```jsx
          <MyComponent name="Alice" age={30} />
          ```
      2.  **Receiving in Functional Component:**
          ```jsx
          function MyComponent(props) { // props is an object: { name: "Alice", age: 30 }
            return <p>Hello, {props.name}. You are {props.age}.</p>;
          }
          // Or with destructuring:
          function MyComponent({ name, age }) {
            return <p>Hello, {name}. You are {age}.</p>;
          }
          ```
      3.  **Receiving in Class Component:**
          ```jsx
          class MyComponent extends React.Component {
            render() {
              // this.props is an object: { name: "Alice", age: 30 }
              return <p>Hello, {this.props.name}. You are {this.props.age}.</p>;
            }
          }
          ```
  *   **Best Example:** A `<UserProfile name="John Doe" avatarUrl="path/to/img.jpg" />` component where `name` and `avatarUrl` are props.

**- What is a Config Driven Ul ?**
  *   **Short:** A UI whose structure, content, and behavior are largely determined by a configuration object (often JSON) rather than being hardcoded in the component logic.
  *   **Analogy:** A music player where the playlist, song order, and even available controls (like "shuffle" button visibility) are loaded from a settings file, rather than being fixed in the player's code. Changing the settings file changes the player's UI and behavior without rewriting the player's core code.
  *   **Best Example:** Building a dynamic form generator where a JSON config specifies the fields, their types (text, dropdown, checkbox), validation rules, and layout. The React component then renders the form based on this JSON.
      ```javascript
      // config.json
      // {
      //   "fields": [
      //     { "name": "username", "type": "text", "label": "Username" },
      //     { "name": "role", "type": "select", "label": "Role", "options": ["Admin", "User"] }
      //   ]
      // }

      // FormComponent.jsx renders based on this config
      ```

**- What is the difference between Named Export, Default export and * as export?**
  *   **Short:**
      *   **Named Export:** Exports multiple values (variables, functions, classes) from a module. Must be imported using the exact same name (or aliased) within curly braces `{}`.
      *   **Default Export:** Exports a single primary value from a module. Can be imported with any name without curly braces. A module can have only one default export.
      *   `* as export` (actually `import * as name`): Imports all named exports from a module as properties of a single object.
  *   **Analogy:**
      *   **Named Export:** A shop's catalog listing individual items (e.g., "Blue T-Shirt", "Red Hat"). You pick specific items by name.
      *   **Default Export:** The shop's main flagship product. When you say "I want something from 'CoolShop'", you get this main product by default.
      *   `import * as name`: Getting the entire catalog from the shop and referring to items like `ShopCatalog.BlueTShirt`.
  *   **JS Example:**
      ```javascript
      // utils.js
      export const PI = 3.14; // Named export
      export function double(n) { return n * 2; } // Named export
      const GREETING = "Hello";
      export default GREETING; // Default export

      // app.js
      import MyGreeting, { PI, double as multiplyByTwo } from './utils.js';
      // MyGreeting is "Hello"
      // PI is 3.14
      // multiplyByTwo is the 'double' function

      import * as Utils from './utils.js';
      // Utils.PI is 3.14
      // Utils.double(2) is 4
      // Utils.default is "Hello"
      ```
  *   **Best Example:**
      *   Use **default export** for the primary thing a module provides (e.g., a React component).
      *   Use **named exports** for utility functions or constants that are secondary or multiple.

**- What is the importance of config.js file**
  *   **Short:** Centralizes application-wide configurations like API endpoints, feature flags, UI themes, or other constants.
  *   **Importance:**
      1.  **Maintainability:** Easy to find and change settings in one place.
      2.  **Environment Specificity:** Can easily load different configs for development, staging, production.
      3.  **Clarity:** Separates configuration from logic, making code cleaner.
  *   **Analogy:** The control panel or settings menu for your application. Instead of hardcoding the volume level in every part of a stereo system, you have one volume knob (config file).
  *   **Best Example:**
      ```javascript
      // config.js
      export const API_BASE_URL = process.env.NODE_ENV === 'production'
        ? 'https://api.example.com'
        : 'http://localhost:3001/api';
      export const FEATURE_NEW_DASHBOARD_ENABLED = true;
      export const THEME_COLOR = 'blue';
      ```
      Then import and use these in your app: `import { API_BASE_URL } from './config';`

**- What are React Hooks?**
  *   **Short:** Functions that let you "hook into" React state and lifecycle features from **functional components**. They allow you to use state, side effects, context, etc., without writing a class component.
  *   **Analogy:** Special tools that allow simple Lego bricks (functional components) to have advanced capabilities (like remembering things/state, or reacting to outside events/lifecycle) that previously only more complex Lego Technic pieces (class components) had.
  *   **JS Example:** `useState`, `useEffect`, `useContext`, `useReducer`.
      ```jsx
      import React, { useState, useEffect } from 'react';

      function MyComponent() {
        const [count, setCount] = useState(0); // useState Hook for state
        useEffect(() => { // useEffect Hook for side effects
          document.title = `You clicked ${count} times`;
        });
        return <button onClick={() => setCount(count + 1)}>Click me</button>;
      }
      ```
  *   **Best Example:** Using `useState` to manage local component state and `useEffect` to perform data fetching or subscriptions.

**- Why do we need a useState Hook?**
  *   **Short:** To add **state** (data that can change over time and affect rendering) to functional components. Before Hooks, only class components could have state.
  *   **Analogy:** Giving a simple, stateless Lego brick (functional component) a small internal memory or a tiny erasable whiteboard (`useState`) where it can keep track of something that might change, like how many times it's been pressed.
  *   **JS Example:**
      ```jsx
      import React, { useState } from 'react';

      function Counter() {
        // 'count' is the state variable, 'setCount' is the function to update it
        const [count, setCount] = useState(0); // Initial state is 0

        return (
          <div>
            <p>You clicked {count} times</p>
            <button onClick={() => setCount(count + 1)}>
              Increment
            </button>
          </div>
        );
      }
      ```
  *   **Best Example:** Managing form input values, toggle states (like a modal's visibility), or any piece of data that should trigger a re-render when it changes within a functional component.

**- What is a Microservice?**
  *   **Short:** An architectural style where a large application is built as a collection of small, independent, and loosely coupled services. Each service is self-contained, focuses on a specific business capability, and can be developed, deployed, and scaled independently.
  *   **Analogy:** A large restaurant that, instead of having one giant kitchen doing everything, has specialized stations: a grill station, a salad station, a dessert station, a drinks bar. Each station (microservice) operates independently with its own staff and equipment but works together to serve the customer's order.
  *   **Best Example:** An e-commerce platform could have separate microservices for User Accounts, Product Catalog, Shopping Cart, Order Processing, and Payments.

**- What is Monolith architecture?**
  *   **Short:** A traditional architectural style where an application is built as a single, unified unit. All its components, modules, and functionalities are tightly coupled and deployed together as one large piece of software.
  *   **Analogy:** An all-in-one kitchen appliance that can blend, toast, bake, and make coffee. Everything is in one unit. If one part breaks (e.g., the toaster element), the whole appliance might be affected or need to be replaced/repaired as a whole.
  *   **Best Example:** A web application where the user interface, business logic, and data access layer are all part of the same codebase and deployed as a single application on a server.

**- What is the difference between Monolith and Microservice?**
  *   **Short:**
      *   **Monolith:** Single, large codebase; all components deployed together. Simpler to develop initially, but harder to scale, maintain, and update specific parts independently.
      *   **Microservice:** Collection of small, independent services; each deployed separately. More complex initial setup and inter-service communication, but easier to scale, update, and maintain individual services. Different services can use different technologies.
  *   **Analogy:**
      *   **Monolith:** One big factory that builds an entire car from start to finish.
      *   **Microservices:** A network of specialized workshops. One workshop makes engines, another makes tires, another assembles the chassis. They all work together, but can be upgraded or expanded independently.
  *   **Key Differences:**
      *   **Deployment:** Monolith (all at once) vs. Microservices (independently).
      *   **Scalability:** Monolith (scale whole app) vs. Microservices (scale individual services).
      *   **Technology Stack:** Monolith (usually one stack) vs. Microservices (polyglot - different stacks possible).
      *   **Fault Isolation:** Monolith (one failure can affect all) vs. Microservices (failure in one service might not bring down others, if designed well).
      *   **Complexity:** Monolith (simpler initial dev, complex long-term) vs. Microservices (complex initial dev/ops, simpler individual services).

**- Why do we need a useEffect Hook?**
  *   **Short:** To perform **side effects** in functional components. Side effects are operations that interact with the "outside world" beyond just rendering UI, such as data fetching, setting up subscriptions, or manually changing the DOM.
  *   **Analogy:** Instructions for your component on what to do *after* it's been drawn on the screen (or when certain data changes). It's like saying, "Okay, component, now that you're visible, go fetch some data from the internet," or "When this 'user ID' prop changes, update the document's title."
  *   **JS Example:**
      ```jsx
      import React, { useState, useEffect } from 'react';

      function UserProfile({ userId }) {
        const [user, setUser] = useState(null);

        useEffect(() => {
          // Side effect: Fetch user data
          fetch(`/api/users/${userId}`)
            .then(res => res.json())
            .then(data => setUser(data));

          // Cleanup function (optional):
          return () => {
            // e.g., cancel subscription, clear timer
            console.log(`Cleaning up effect for userId: ${userId}`);
          };
        }, [userId]); // Dependency array: re-run effect if userId changes

        if (!user) return <p>Loading...</p>;
        return <h1>{user.name}</h1>;
      }
      ```
  *   **Best Example:** Fetching data from an API when a component mounts or when a prop like `userId` changes. Setting up and tearing down event listeners or timers.

**- What is Optional Chaining (`?.`)?**
  *   **Short:** A JavaScript operator (`?.`) that allows you to safely access deeply nested object properties without having to explicitly check if each property in the chain exists. If any part of the chain is `null` or `undefined`, the expression short-circuits and returns `undefined` instead of throwing an error.
  *   **Analogy:** Carefully trying to open a series of nested boxes. If you encounter an empty box (a `null` or `undefined` property) at any point, you stop trying to open further boxes inside it and just acknowledge "there's nothing further," instead of causing a mess (throwing an error).
  *   **JS Example:**
      ```javascript
      const user = {
        // address: {
        //   street: '123 Main St'
        // }
      };

      // Without optional chaining (could throw error if address is undefined)
      // const street = user.address.street; // TypeError if user.address is undefined

      // With optional chaining
      const street = user?.address?.street; // street will be undefined, no error
      const zip = user?.address?.zipCode ?? 'N/A'; // Using nullish coalescing for a default

      console.log(street); // undefined
      ```
  *   **Best Example:** Accessing properties from API responses where some data might be missing, e.g., `const cityName = response.data?.user?.location?.city;`.

**- What is Shimmer Ul?**
  *   **Short:** A type of loading indicator that displays a placeholder preview of the UI, often with a subtle animation (like a "shimmer" or pulsing effect) passing over it. It mimics the layout of the content that is about to load.
  *   **Analogy:** Seeing the vague shape and size of presents under the Christmas tree through a slightly translucent wrapping paper before they are unwrapped. It gives you an idea of what's coming and feels more engaging than a blank space or a simple spinner.
  *   **Best Example:** Facebook or LinkedIn's loading state, where grey boxes of various shapes appear where text and images will eventually load, often with a sweeping light animation.

**- What is the difference between JS expression and JS statement**
  *   **Short:**
      *   **Expression:** A piece of code that evaluates to (produces) a single value.
      *   **Statement:** A complete instruction or action to be performed. Statements often contain expressions.
  *   **Analogy:**
      *   **Expression:** A noun phrase or a clause that results in a "thing" (e.g., "the red ball", "5", "true", "what John said").
      *   **Statement:** A full sentence that performs an action or declares something (e.g., "Throw the red ball.", "Let x be 5.", "If it's raining, take an umbrella.").
  *   **JS Example:**
      ```javascript
      // Expressions:
      5                    // Evaluates to 5
      x + y                // Evaluates to the sum of x and y
      isActive             // Evaluates to true or false
      "hello"              // Evaluates to the string "hello"
      myFunction()         // Evaluates to the return value of myFunction

      // Statements:
      let x = 10;                       // Declaration statement
      if (x > 5) { console.log("Big"); } // Conditional statement
      for (let i = 0; i < 3; i++) { }     // Loop statement
      console.log("Hello");             // Expression statement (console.log() is an expression,
                                      // but the whole line is an action)
      ```
  *   **Best Example in React/JSX:** Inside `{}` in JSX, you can only put expressions, not statements.
      *   `<h1>{user.name}</h1>` (`user.name` is an expression)
      *   `<div>{isLoading ? <Spinner /> : <Data />}</div>` (ternary operator is an expression)
      *   You *cannot* do: `<h1>{let x = 5; x}</h1>` (`let x = 5;` is a statement).

**- What is Conditional Rendering, explain with a code example**
  *   **Short:** Displaying different UI elements or components based on certain conditions (e.g., user login status, data availability, state values).
  *   **Analogy:** Having different sets of clothes for different weather. If it's sunny (condition), you wear shorts (UI). If it's raining (condition), you wear a raincoat (different UI).
  *   **JS Example (React):**
      ```jsx
      import React, { useState } from 'react';

      function AuthButton() {
        const [isLoggedIn, setIsLoggedIn] = useState(false);

        if (isLoggedIn) {
          return <button onClick={() => setIsLoggedIn(false)}>Logout</button>;
        } else {
          return <button onClick={() => setIsLoggedIn(true)}>Login</button>;
        }
      }

      // Another common way using ternary operator:
      function Greeting({ user }) {
        return (
          <div>
            {user ? <h1>Welcome, {user.name}!</h1> : <p>Please log in.</p>}
          </div>
        );
      }

      // And with logical && for rendering something or nothing:
      function AdminPanel({ isAdmin }) {
        return (
          <div>
            {isAdmin && <button>Admin Settings</button>}
            <p>User Dashboard</p>
          </div>
        );
      }
      ```
  *   **Best Example:** Showing a "Login" button or a "User Profile" section based on whether a user is authenticated. Displaying a loading spinner while data is being fetched and the actual data once it arrives.

**- What is CORS?**
  *   **Short:** Cross-Origin Resource Sharing. A browser security mechanism that controls how web pages in one domain can request and access resources (e.g., APIs, fonts, images) from a server in a *different* domain.
  *   **Analogy:** Your house (your website's domain) has a security rule: you can only accept packages (data/resources) from your own address by default. If a package comes from a neighbor's address (a different domain), the mailman (browser) needs explicit permission (CORS headers) from that neighbor saying it's okay for your house to receive it. Without permission, the mailman won't deliver it.
  *   **Why it exists:** To prevent malicious websites from making unauthorized requests to other domains using a user's credentials.
  *   **Best Example:** Your frontend code at `mydomain.com` tries to fetch data from an API at `api.anotherdomain.com`. The browser makes a pre-flight `OPTIONS` request. If `api.anotherdomain.com`'s response includes headers like `Access-Control-Allow-Origin: mydomain.com`, the browser allows the actual data request. If not, it blocks it with a CORS error.

**- What is async and await?**
  *   **Short:** `async` and `await` are JavaScript keywords that provide syntactic sugar for working with Promises, making asynchronous code look and behave a bit more like synchronous code, which can make it easier to read and reason about.
      *   `async`: Placed before a function declaration, it makes the function implicitly return a Promise.
      *   `await`: Can only be used inside an `async` function. It pauses the execution of the `async` function until the Promise it's waiting for resolves or rejects.
  *   **Analogy:**
      *   `async` function: Like saying, "This task (function) might take some time and won't finish immediately. I promise to let you know when it's done."
      *   `await`: Like saying, "I need to wait here for *this specific part* of the task to finish before I can proceed with the next step in *my current plan*." While waiting, other JavaScript code outside this `async` function can still run.
  *   **JS Example:**
      ```javascript
      // Using Promises directly
      function fetchDataOld() {
        return fetch('https://api.example.com/data')
          .then(response => {
            if (!response.ok) {
              throw new Error('Network response was not ok');
            }
            return response.json();
          })
          .then(data => {
            console.log(data);
            return data;
          })
          .catch(error => {
            console.error('Fetch error:', error);
          });
      }

      // Using async/await
      async function fetchDataNew() {
        try {
          const response = await fetch('https://api.example.com/data'); // Pauses here until fetch resolves
          if (!response.ok) {
            throw new Error('Network response was not ok');
          }
          const data = await response.json(); // Pauses here until .json() resolves
          console.log(data);
          return data;
        } catch (error) {
          console.error('Fetch error:', error);
        }
      }

      fetchDataNew(); // This itself returns a Promise
      ```
  *   **Best Example:** Fetching data from an API, then processing the response, all in a clear, sequential-looking manner within an `async` function.

**- What is the use of 'const json = await data.json(); in getRestaurants()**
  *   **Short:**
      1.  `data`: This is typically a `Response` object received from a `fetch()` call (e.g., `const data = await fetch(...)`).
      2.  `.json()`: This is a method on the `Response` object. It reads the response stream to completion and parses the body text as JSON. This process is asynchronous, so `.json()` returns a Promise.
      3.  `await`: Pauses the execution of the `getRestaurants` (which must be an `async` function) until the Promise returned by `data.json()` resolves.
      4.  `const json = ...`: Once the Promise resolves, its result (the parsed JavaScript object from the JSON data) is assigned to the `json` variable.
  *   **Analogy:**
      *   `data` (Response object): A sealed letter (the HTTP response) that you've received.
      *   `data.json()`: The act of opening the letter and reading its contents, assuming the contents are written in JSON format. This takes a moment.
      *   `await`: You wait patiently while the letter is being opened and read.
      *   `const json = ...`: The actual message (parsed JSON data) from the letter is now in your hands (stored in the `json` variable).
  *   **Best Example (within a hypothetical `getRestaurants` function):**
      ```javascript
      async function getRestaurants() {
        try {
          const response = await fetch('https://api.example.com/restaurants'); // `response` is the Response object
          if (!response.ok) {
            throw new Error(`HTTP error! status: ${response.status}`);
          }
          // `response.json()` reads the body and parses it as JSON. This is async.
          // `await` waits for this parsing to complete.
          const jsonData = await response.json();
          // `jsonData` is now a JavaScript object/array representing the restaurants
          console.log(jsonData);
          return jsonData;
        } catch (error) {
          console.error("Could not fetch restaurants:", error);
        }
      }
      ```

**- What are various ways to add images into our App? Explain with code examples**
  1.  **Public Folder (Static Assets):**
      *   **How:** Place the image in a `public` (or `static`) folder that your server serves directly. Reference it with a relative path from the HTML.
      *   **Analogy:** Putting a picture frame directly on a publicly accessible wall in your house.
      *   **Code Example (assuming `public/images/logo.png`):**
          ```html
          <!-- In HTML -->
          <img src="/images/logo.png" alt="Company Logo" />
          ```
          ```jsx
          // In React (if image is in public folder)
          function Logo() {
            return <img src={process.env.PUBLIC_URL + '/images/logo.png'} alt="Company Logo" />;
            // Or if server serves from root: <img src="/images/logo.png" alt="Company Logo" />
          }
          ```
  2.  **Importing with a Bundler (Webpack/Parcel):**
      *   **How:** `import` the image like a JavaScript module. The bundler processes it, often optimizing it and giving you a path or data URL.
      *   **Analogy:** Asking your project manager (bundler) to handle the image. They might make copies, resize it, and give you a special ticket (path/data URL) to display it.
      *   **Code Example:**
          ```javascript
          // src/components/MyImage.js
          import React from 'react';
          import mySpecificImage from '../assets/my-image.jpg'; // Path relative to this JS file

          function MyImage() {
            return <img src={mySpecificImage} alt="A descriptive alt text" />;
          }
          export default MyImage;
          ```
  3.  **CSS `background-image`:**
      *   **How:** Use the CSS `background-image` property. Paths are relative to the CSS file or can be absolute.
      *   **Analogy:** Using wallpaper with a picture pattern on a wall.
      *   **Code Example:**
          ```css
          /* styles.css */
          .hero-section {
            background-image: url('../assets/background.jpg'); /* Relative to CSS file */
            /* or background-image: url('/images/public-background.png'); if in public */
            background-size: cover;
            height: 300px;
          }
          ```
          ```jsx
          // In React, applying the class
          function Hero() {
            return <div className="hero-section"></div>;
          }
          ```
  4.  **Absolute URLs (from CDN or external source):**
      *   **How:** Use the full URL of an image hosted elsewhere.
      *   **Analogy:** Displaying a poster that's stored in a public art gallery (CDN).
      *   **Code Example:**
          ```jsx
          function Avatar() {
            const avatarUrl = "https://cdn.example.com/user-avatars/user123.png";
            return <img src={avatarUrl} alt="User Avatar" />;
          }
          ```

**- What would happen if we do console.log(useState()?**
  *   **Short:** If called *inside* a React functional component (or a custom Hook), `console.log(useState())` would log an array containing two elements:
      1.  The current state value (which would be `undefined` if no initial value was passed to this specific `useState()` call and it's the first render).
      2.  A function to update that state (the "setter" function).
  *   **If called *outside* a React component context, it would throw an error** because Hooks can only be called inside the body of a function component or a custom Hook.
  *   **Analogy (inside component):** It's like asking the "state provider" in React, "What's the current value you're holding for me right now, and what's the remote control (setter function) to change it?"
  *   **JS Example (inside a component):**
      ```jsx
      import React, { useState } from 'react';

      function TestState() {
        const stateTuple = useState(); // No initial value, so state is undefined initially
        console.log(stateTuple);
        // Output would be similar to: [undefined, function dispatchSetState()]

        const [count, setCount] = useState(0);
        console.log(useState(0)); // This would be different for THIS call
        // Output could be: [0, function dispatchSetState()] if it's first render
        // Or [currentValue, function dispatchSetState()] on subsequent renders

        return <p>Check console</p>;
      }
      ```

**- How will useEffect behave if we don't add a dependency array?**
  *   **Short:** If you omit the dependency array in `useEffect`, the effect function will run **after every single render** of the component, including the initial render and all subsequent re-renders caused by any state or prop changes.
  *   **Analogy:** A chore that you *must* do every single time you enter a room (component renders), no matter why you entered or what changed in the room.
  *   **Behavior:**
      1.  Runs after the initial render.
      2.  Runs after any re-render of the component, regardless of what caused the re-render.
  *   **Caution:** This can easily lead to infinite loops if the effect itself causes a state update that triggers a re-render.
  *   **JS Example:**
      ```jsx
      import React, { useState, useEffect } from 'react';

      function MyComponent() {
        const [count, setCount] = useState(0);

        useEffect(() => {
          console.log('Effect ran!');
          // If you did setCount(c => c + 1) here, it would be an infinite loop!
        }); // No dependency array

        return (
          <div>
            <p>Count: {count}</p>
            <button onClick={() => setCount(count + 1)}>Increment</button>
          </div>
        );
      }
      ```
      In this example, "Effect ran!" will be logged on initial mount and every time the button is clicked (because `setCount` causes a re-render).

**- What is SPA?**
  *   **Short:** Single Page Application. A web application or website that interacts with the user by dynamically rewriting the current web page with new data from the web server, instead of the default method of a web browser loading entire new pages.
  *   **Analogy:** A magical book where, instead of turning to a completely new physical page for new content, the words and pictures on the *current page* magically change to show you the new chapter or section. The book cover (initial HTML shell) remains the same.
  *   **Key Characteristics:**
      *   Loads a single HTML shell.
      *   JavaScript manipulates the DOM to render different "views" or "pages."
      *   Navigation between views often handled by client-side routing.
      *   Data is typically fetched asynchronously (e.g., via AJAX/Fetch API).
  *   **Best Example:** Gmail, Google Maps, Facebook, Twitter web interfaces. When you click around, the URL might change, and content updates, but the browser doesn't do a full white-screen reload.

**- What is difference between Client Side Routing and Server Side Routing?**
  *   **Short:**
      *   **Server-Side Routing (SSR / Traditional):** When a user clicks a link, the browser sends a request to the server. The server processes the request and sends back a *completely new HTML page*. The browser then loads this new page, causing a full page refresh.
      *   **Client-Side Routing (CSR / SPA):** When a user clicks a link, JavaScript running in the browser intercepts the navigation. It typically updates the URL in the browser's address bar (using the History API), but *prevents a full page reload*. The JavaScript then dynamically changes the content on the current page (e.g., by rendering different React components) to show the new "view." Data for the new view might be fetched from an API.
  *   **Analogy:**
      *   **Server-Side Routing:** Ordering a different dish from a restaurant menu. The waiter goes to the kitchen (server) and brings you an entirely new, distinct plate (HTML page).
      *   **Client-Side Routing:** You have a magic plate. You tell the plate (JavaScript), "I want pasta now." The food on your *current plate* changes to pasta without the waiter bringing a brand new physical plate. The plate might quickly get new ingredients (API data) from the kitchen, but the plate itself isn't replaced.
  *   **Best Example:**
      *   **Server-Side:** Many traditional websites, blogs built with WordPress (by default).
      *   **Client-Side:** React apps using `react-router-dom`, Vue apps with `vue-router`, Angular apps.
