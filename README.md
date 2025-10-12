### What's this?

It's a boilerplate template like any other. Compared to the default Svelte 5 kit template, a few modifications have been made.

- The compiled size of this boilerplate is about 310 KiB with all dependencies included. Most of that, about two third at 213 KiB, is from the CSS framework. The CSS part can be reduced by removing the color variables to 139 KiB and to 117 KiB by using the classless version.
- Compilation produces an SPA, using **adapter-static**. The output can be used as a fully client-side application, hosted by a webserver or for use by Electron, etc.
- **PicoCSS** (using *@yohns/picocss* fork), a minimalist CSS framework has been included by default. It offers an optional classless mode as well as light/dark themes and a number of color themes. Check the integration in **+layout.svelte**.
- **Lucide** (*@lucide/svelte*), an open source svelte icon component library with 1,100+ icons that can style SVG icons out of the box and doesn't use webfonts.
- A *very simple* navigation component using the `<button>` element, in order to hide the link hover tooltips that may be undesired when building app interfaces.


### Using this template

The following commands will create a local copy of this repo and make it ready for development:

```sh
# clone repository into current directory
# note: this only works if the directory is empty!
git clone https://github.com/dante-quest/svelte5-spa-boilerplate.git .
npm install

# clone repository into target directory
git clone https://github.com/dante-quest/svelte5-spa-boilerplate.git your_project_name
cd your_project_name
npm install

# optionally, rename the default directory name:
git clone https://github.com/dante-quest/svelte5-spa-boilerplate.git
mv svelte5-spa-boilerplate your_project_name
cd your_project_name
npm install
```


### Further development

The following commands are essential for the development phase:

```sh
# start the dev server
npm run dev

# start the dev server and open the project in your default browser
npm run dev -- --open

# build the project as a SPA
npm run build
```


### Building the SPA

The command **npm run build** will create the SPA in the **./build** folder with **index.html** as the entry-point.

You can optionally activate prerendering if you desire or require increased performance. You can do this by adding **export const prerender = true;** in **+layout.ts** and other **.ts** files. This step also requires you to change the fallback from **index.html** to something else like **200.html** in **svelte.config.js**.