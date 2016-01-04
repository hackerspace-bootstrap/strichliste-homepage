+++
date = "2015-07-12T00:34:08+02:00"
draft = false
title = "Install strichliste"
[menu]
  [menu.main]
    parent = "Install"
+++

Installing strichliste is done in two steps.

### Backend

#### Prerequisites

The backend is a nodejs application. As such, you need to have `nodejs` installed.

    sudo apt-get install nodejs

#### Installing the Backend

1. Go to the Github project to download the [latest release](https://github.com/hackerspace-bootstrap/strichliste/releases).
2. Unpack the contents of the tarball to your target directory.
3. Run `npm install` to install the package depencies.
4. Create the SQLite database by running `make database`.
5. _(optional)_ Modify `configuration.js` to match your needs.
6. Start the backend by running `node server.js`. You can optionally specify
the path to your configuration file using the `--externalconfig` parameter.

The backend should now be running.

### Frontend

#### Installing the Frontend

The frontend is a set of static files to be served by a webserver such as
`nginx`. It accesses the backend using HTTP.

1. Go to the Github project to download the [latest release](https://github.com/hackerspace-bootstrap/strichliste-web).
2. Unpack the contents of the tarball to your target directory. 
4. Modify `src/script/lib/settings.js` to match your needs.
5. Run `make production` to install the package depencies.
6. Your build is not ready in the build/ directory where your webserver should point to.
7. Access the frontend from your favorite browser.

You should now be able to create your first transactions!
