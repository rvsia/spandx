# spandex
Develop locally, proxy to prod, browser-sync, and process ESI tags.


## Quick-start

Here's a sample configuration file.  Save it as `sample.config.js`

    module.exports = {
        host: 'local.my-app.com',
        port: 1337,
        verbose: true,
        routes: {

            // Here are some routing examples to get started.

            // Route a URL path to a local directory.
            '/assets': '~/projects/my-app/assets',

            // Route a URL path to an app server.
            // This is most useful for testing local files (esp JS and CSS) against
            // a remote QA or production server.
            '/': { host: 'http://production.my-app.com' },

            // Route a URL path to an app server, and watch local files for changes.
            // This is most useful for putting a local development at a certain
            // path on your spandx server.  Includes browser-sync auto-reloading.
            '/': { host: 'http://localhost:8080/', watch: '~/projects/my-app' },

        },
    };

Then launch spandx!

    spandx -c sample.config.js
