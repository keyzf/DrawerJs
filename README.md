# DrawerJS

DrawerJS is a HTML5 widget that allows drawing and writing on HTML5 canvas element. Supports mobile devices. 

Here you will find more informations about features, examples, and you can test it live: [DrawerJs](https://www.DrawerJs.com)
Here you will find a detailed documentation about the usage and its configuration: [DrawerJs - Docs](https://www.drawerjs.com/documentation)

# Documentation:

[Distribution versions](#plugin-versions)

[Configuration options](#configuration)

[Development environment setup](#development-how-to)

[Source code files and build system overview](./ARCHITECTURE-DIRECTORIES.md)

[Source code architecture overview](./ARCHITECTURE.md)

## Plugin versions

This plugin distributes in two versions:

### Redactor editor plugin

Could be embedded to page as follows:

    <link rel="stylesheet" href="dist/drawerJs.css"/>

    <script src="dist/drawerJs.redactor.js"></script>

    <!-- or minified version: -->

    <script src="dist/drawerJs.redactor.min.js"></script>

For information about how to build everything to the `dist` folder please see [Development how-to](#development-how-to)

Then `drawer` name could be provided to redactor's config into the `plugins` section:

    $('.redactor').redactor({
        buttons: [
            'bold',
            'html',
            'image'
        ],
        plugins: [
            'video',
            'drawer', // << here we specify that redactor should load this plugin
            'opensave',
            'contexttoolbar'
        ],
        drawer: {
            // drawer config section here
            activeColor: '#19A6FD' // default drawing color
        }
    });

For working example please see `demo` folder.

For more information about drawer config section please see [Configuration](#configuration)

### Standalone version

Could be embedded to page as follows:

    <link rel="stylesheet" href="dist/drawerJs.css"/>

    <script src="dist/drawerJs.standalone.js"></script>

    <!-- or minified version: -->

    <script src="dist/drawerJs.standalone.min.js"></script>

For information about how to build everything to the `dist` folder please see [Development how-to](#development-how-to)

Then drawer could be appended to any html container like this:

    var canvas = new DrawerJs.Drawer(null, {
        // drawer config section here
        activeColor: '#19A6FD' // default drawing color
    }, 600, 600); // height and width of drawer will be 600x600

    $('#some_id').append(canvas.getHtml());
    canvas.onInsert();

Where `#some_id` is any DOM element id.

For working example please see `examples/standalone` folder.

For more information about drawer config section please see [Configuration](#configuration)

## Configuration

When you finish with [setting up development environment](#development-how-to)
you will have dist folder with everything built up.
Look there for `docs` folder, find `index.html` and open it.

Then the link below will work.

Please look at [CanvasElement documentation](DrawerJs.CanvasElement.html) for options description.


##  Development how-to:

Requirements: node.js, npm, git

`npm install` to install all npm/bower dependencies.

`npm start` to compile everything to `dist` folder.

This will also watch for changes  in `src` directory and recompile everything.


