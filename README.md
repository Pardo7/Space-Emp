# mleap

Wattos SpaceShip Emporium is built using Googles Polymer.JS framework and Webcomponents.

Wattos SpaceShip Emporium, along with the polymer-cli toolchain, demonstrates use of the "PRPL pattern" This pattern allows fast first delivery and interaction with the content at the initial route requested by the user, along with fast subsequent navigation by pre-caching the remaining components required by the app and progressively loading them on-demand as the user navigates through the app.

The PRPL pattern, in a nutshell:

* **Push** components required for the initial route
* **Render** initial route ASAP
* **Pre-cache** components for remaining routes
* **Lazy-load** and progressively upgrade next routes on-demand

Polymer and WebComponents, in a nutshell:

* Polymer is a lightweight library that helps you take full advantage of Web Components.
* With Web Components, you can create reusable custom elements that interoperate seamlessly with the browser’s built-in elements, or break your app up into right-sized components, making your code cleaner, less expensive to maintain and **blazing fast**!
* Polymer sprinkles a bit of sugar over the standard Web Components APIs, making it easier for you to get great results.

### Setup
### Installing dependencies

1) If you haven't already done so, [install Node](https://nodejs.org/en/) (version 4.4.0 and above).

You can install the Mac OS-X or Windows installer based on your Operating System. On Mac OS-X to sideline the frustrating `sudo` and `file.lock` issues for running npn with -g option, please refer to [Fixing npm permissions](https://docs.npmjs.com/getting-started/fixing-npm-permissions).

2) After you have Node installed install [Bower](https://bower.io/) and the [Polymer Cli](https://github.com/Polymer/polymer-cli) by typing the following in the terminal:

```bash
npm install -g bower polymer-cli
```

_(if you used the default Node installer rather than nvm, you will likely need to run the above command as `sudo`)_

```bash
sudo npm install -g bower polymer-cli
```


You're now ready to browse super awesome spaceships and wage an intergalactic war!

## Running Wattos SpaceShip Emporium

1) Clone [Watto's Spaceship Emporium]() repo:

```bash
git clone https://github.com/Pardo7/mleap.git
```

2) Use NPM & Bower to install Wattos Spaceship Emporium dependencies:

```bash
cd mleap
npm install && bower install
```

This will create the `/node_modules` and `public/bower_components` folders.

3) Start your local Wattos Spaceship Emporium development server:

```bash
polymer serve
```
You'll see some output in the terminal resembling the sample output below:

```bash
Files in this directory are available under the following URLs
      applications: http://127.0.0.1:8000
```

4) Open the application url referenced in your terminal output in your browser, and you'll see Wattos Spaceship Emporium manifest before your very eyes!


# Taking Watto's To Production
### Build

This command performs HTML, CSS, and JS minification on the application dependencies, and generates a service-worker.js file with code to pre-cache the dependencies based on the entrypoint and fragments specified in polymer.json. The minified files are output to the build/unbundled folder, and are suitable for serving from a HTTP/2+Push compatible server.

In addition the command also creates a fallback build/bundled folder, generated using fragment bundling, suitable for serving from non H2/push-compatible servers or to clients that do not support H2/Push.

```bash
polymer build
```

### Preview the build
This command serves the minified version of the app at http://localhost:8080 in an unbundled state, as it would be served by a push-compatible server:

```bash
polymer serve build/unbundled
```

This command serves the minified version of the app at http://localhost:8080 generated using fragment bundling:

```bash
polymer serve build/bundled
```
