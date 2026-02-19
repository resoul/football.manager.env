# Football Manager

This is local stack for developers. Check out instructions below to getting started.

## Prerequires

To work with this repository you should install docker and node.js
Checkout instructions how to install it on your operating system.
```
Docker: https://docs.docker.com/engine/install/
Node.js: https://nodejs.org/en/download/
```
## Setup local environment

Create a directory for projects, for example `$HOME/projects/manager`

Go to this directory and clone this repository

Go to directory

Run the following commands:

```
npm install
make services-init
make projects-init
make services-deploy
```

On the output you can see all projects domains.

Use command `make help` to get all available commands.

### Create a local proxy

Run the following commands:

```
sudo mkdir /opt/homebrew/etc/nginx/manager.d
sudo make dns
```
Type the directory location with trailing slash: `/opt/homebrew/etc/nginx/manager.d/`
than reload nginx: `sudo nginx -s reload`

Update your `/opt/homebrew/etc/nginx/nginx.conf` file, add line `include manager.d/*.conf;` to section http.

After that add next rows to your `/etc/hosts` file

```
127.0.0.1    dashboard.manager.localhost
127.0.0.1    api.manager.localhost
127.0.0.1    mail.manager.localhost
127.0.0.1    adminer.manager.localhost
```

If all done correctly, you should had access to all hosts above via your browser.


### Local passwords
```
http://api.manager.localhost
http://dashboard.manager.localhost
http://adminer.manager.localhost postgres/postgres
```
