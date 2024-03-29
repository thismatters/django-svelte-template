# This Svelte 3 template is no longer current. Please see the [instructions for setting up a Svelte 4 deployment](https://github.com/thismatters/django-svelte/tree/main/demo_project/svelte) appropriate for use along `django-svelte`.

---

# django-svelte-template

This template has a few modifications applied to the vanilla Svelte template:
* Rollup configured to export multiple app bundles,
  * Default export is still based upon `App.svelte`, but `main.js` has been renamed `main-App.js` and has been modified to target an element created in the html template by django-svelte (e.g. `app-target` and `app-props`; the name `app` is keying off of the component name: `App.js`)
  * To export additional component js/css bundles add the name of the component (e.g. "MyComponent") to the Array at the bottom of `rollup.config.js`, create the component with that name ("MyComponent.svelte"), create a `main-MyComponent.js` by copying `main-App.js` and replace all instances of "app" with "mycomponent" (observing appropriate casing "App" -> "MyComponent"). You may need to restart the Node.js instance for your changes to take effect. See [django-svelte-demo](https://github.com/thismatters/django-svelte-demo) for an example of this in action.

---


# svelte app

This is a project template for [Svelte](https://svelte.dev) apps. It lives at https://github.com/sveltejs/template.

To create a new project based on this template using [degit](https://github.com/Rich-Harris/degit):

```bash
npx degit sveltejs/template svelte-app
cd svelte-app
```

*Note that you will need to have [Node.js](https://nodejs.org) installed.*


## Get started

Install the dependencies...

```bash
cd svelte-app
npm install
```

...then start [Rollup](https://rollupjs.org):

```bash
npm run dev
```

Navigate to [localhost:5000](http://localhost:5000). You should see your app running. Edit a component file in `src`, save it, and reload the page to see your changes.

By default, the server will only respond to requests from localhost. To allow connections from other computers, edit the `sirv` commands in package.json to include the option `--host 0.0.0.0`.

If you're using [Visual Studio Code](https://code.visualstudio.com/) we recommend installing the official extension [Svelte for VS Code](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode). If you are using other editors you may need to install a plugin in order to get syntax highlighting and intellisense.

## Building and running in production mode

To create an optimised version of the app:

```bash
npm run build
```

You can run the newly built app with `npm run start`. This uses [sirv](https://github.com/lukeed/sirv), which is included in your package.json's `dependencies` so that the app will work when you deploy to platforms like [Heroku](https://heroku.com).


## Single-page app mode

By default, sirv will only respond to requests that match files in `public`. This is to maximise compatibility with static fileservers, allowing you to deploy your app anywhere.

If you're building a single-page app (SPA) with multiple routes, sirv needs to be able to respond to requests for *any* path. You can make it so by editing the `"start"` command in package.json:

```js
"start": "sirv public --single"
```

## Using TypeScript

This template comes with a script to set up a TypeScript development environment, you can run it immediately after cloning the template with:

```bash
node scripts/setupTypeScript.js
```

Or remove the script via:

```bash
rm scripts/setupTypeScript.js
```

## Deploying to the web

### With [Vercel](https://vercel.com)

Install `vercel` if you haven't already:

```bash
npm install -g vercel
```

Then, from within your project folder:

```bash
cd public
vercel deploy --name my-project
```

### With [surge](https://surge.sh/)

Install `surge` if you haven't already:

```bash
npm install -g surge
```

Then, from within your project folder:

```bash
npm run build
surge public my-project.surge.sh
```
