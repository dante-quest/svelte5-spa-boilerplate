<h3>What's this?</h3>
<p>
	It's a boilerplate template like any other. Compared to the default Svelte 5 kit template, a few modifications have been made.
</p>
<ul>
	<li>
		The compiled size of this boilerplate is about 310 KiB with all dependencies included. Most of
		that, about two third at 213 KiB, is from the CSS framework. The CSS part can be reduced by
		removing the color variables to 139 KiB and to 117 KiB by using the classless version.
	</li>
	<li>
		Compilation produces an SPA, using <strong>adapter-static</strong>. The output can be used as a
		fully client-side application, hosted by a webserver or for use by Electron, etc.
	</li>
	<li>
		<strong>PicoCSS</strong> (using <em>@yohns/picocss</em> fork), a minimalist CSS framework has been
		included by default. It offers an optional classless mode as well as light/dark themes and a number
		of color themes. Check the integration in <strong>+layout.svelte</strong>.
	</li>
	<li>
		<strong>Lucide</strong> (<em>@lucide/svelte</em>), an open source svelte icon component library
		with 1,100+ icons that can style SVG icons out of the box and doesn't use webfonts.
	</li>
	<li>
		A <em>very simple</em> navigation component using the &lt;button&gt; element, in order to hide
		the link hover tooltips that may be undesired when building app interfaces.
	</li>
</ul>

<h3>Using this template</h3>
<p>
	The following commands will create a local copy of this repo and make it ready for development:
</p>
<pre>
	mkdir your_new_project
	cd your_new_project
	git clone https://github.com/dante-quest/svelte5-spa-boilerplate
	npm install
</pre>

<h3>Further development</h3>
<p>
	The following commands will create a local copy of this repo and make it ready for development:
</p>
<pre>
	# start the dev server
	npm run dev

	# start the dev server and open the project in your default browser
	npm run dev -- --open

	# build the project as a SPA
	npm run build
</pre>

<h3>Building the SPA</h3>
<p>
	Using the default command <strong>npm run build</strong> will create the SPA in the <strong>
	./build	</strong> folder with <strong>index.html</strong> as the entry-point.
</p>
<p>
	Optionally activate prerendering in <strong>+layout.ts</strong> and change the fallback from
	<strong>index.html</strong> to something else like <strong>200.html</strong> in <strong>
	svelte.config.js</strong> if you require increased performance through pre-rendered pages.
</p>

