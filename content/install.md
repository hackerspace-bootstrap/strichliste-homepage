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
4. Create the SQLite database by running `make database`. (You might need the package `sqlite3` or the equivalent on your distro.)
5. _(optional)_ Modify `configuration.js` to match your needs.
6. Start the backend by running `node server.js`. You can optionally specify
the path to your configuration file using the `--externalconfig` parameter.

The backend should now be running on `http://localhost:8080` (default).

#### Reverse-Proxy in front of API (optional)

You can proxy the requests to your strichliste server through your favorite webserver, using the default HTTP port 80. 

For NGINX:
```
location /api/ {
   proxy_pass http://localhost:8080/;
}
```

For Apache:
```
ProxyPass /api/ http://localhost:8080/
ProxyPassReverse /api/ http://localhost:8080/
```

### Frontend

#### Installing the Frontend

The frontend is a set of static files to be served by a webserver such as
`nginx`. It accesses the backend using HTTP.

1. Go to the Github to download the [latest release](https://github.com/hackerspace-bootstrap/strichliste-web/releases).
2. Unpack the contents of the tarball to a directory of your choice. (e.g. /var/www/strichliste)
3. Configure your webserver to point to this directory.
4. Modify your settings in `js/settings.js`. Use `http://<servername>:8080` or `http://<servername>/api` if you are using a reverse proxy.
5. Access the frontend from your favorite browser.

You should now be able to create your first transactions!
