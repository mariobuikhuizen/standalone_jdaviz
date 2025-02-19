# standalone_jdaviz

This repository is an example standalone web embed of [Jdaviz](https://github.com/spacetelescope/jdaviz) using the JS script version of [Voila Embed](https://github.com/mariobuikhuizen/voila-embed).  It is primarily designed to explore CSS conflicts during the embed process.  See https://github.com/spacetelescope/jdaviz/issues/463 for the initial discussion.

## Example Pages
This repo contains the following example pages
- index_simple.html - a simple embed of Jdaviz in a page predominantly controlled by Vue+Vuetify
- index_jwst.html - an embed of Jdaviz into a page with some extra layout and content for JWST, predominantly controlled by Vue-Vuetify, with some custom css.
- index_zmast.html - an embed of Jdaviz into a page with some extra layout and content for Z.MAST, with a mix of CSS and JS, e.g. Bootstrap, Jquery, Datatables, custom css, etc.

## Run Front-End Server
To set up the front-end, in a terminal window, do the following:

- cd into the `example` subdirectory
- copy one of the example index files to index.html, e.g. `cp index_simple.html index.html`
- run `npx serve` to spin up a local dev site
- Navigate to `http://localhost:5000` or wherever `npx` locally deployed the front-end.
## Run Voila Server
To set up the back-end Voila server, in a new terminal window, do the following:

- Navigate to this top-level directory, i.e. the directory where the `jdaviz_test.ipynb` resides
- install the [Voila Embed](https://github.com/mariobuikhuizen/voila-embed) package
- start the voila server with `voila --no-browser --template=embed --enable_nbextensions=True --Voila.tornado_settings="{'allow_origin': 'http://localhost:5000'}" --port=8000`.  This will start Voila running locally on port 8000.
- Reload the front-end web page
