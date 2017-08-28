## Zoo [![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/caonUlisses/zoo/issues) [![Maintenance](https://img.shields.io/maintenance/yes/2017.svg)]() [![Gemnasium](https://img.shields.io/gemnasium/mathiasbynens/he.svg)]() [![AUR](https://img.shields.io/aur/license/yaourt.svg)]()

![Zoo - An electric zoo for electric people](img/logo.png)

## An electric zoo for electric people

### What?

Zoo is a command line tool to help you set up development servers easily on GNU/Linux, with a few intuitive commands.

It assumes you are using the LEMP stack ([Linux](https://www.linuxfoundation.org/), [NGINX](https://nginx.org/en/), [MySQL](https://www.mysql.com/) and [PHP7](https://secure.php.net/manual/en/intro-whatis.php)).

It helps you with:

+ Easily creating a nginx site
+ Easily creating a nginx [laravel](https://laravel.com/) app
+ Easily starting, stopping and restarting your the EMP part of the LEMP stack

### How?

Just follow this tiny guide:

```bash
# Clone the repo
$ git clone https://github.com/caonUlisses/zoo.git zoo

# Enter the directory
$ cd zoo

# Run it!

$ sudo zoo lemp-start

```

You can also add the file to your $PATH or move it to your /bin/ to make it accessible everywhere!

```bash
# To move it to your /bin/ directory
# PROCEDE WITH CAUTION
$ sudo mv zoo /bin/zoo

```

### But what does it do?

The following commands are at your display:

```bash
# Well, this one starts emp
$ sudo zoo lemp-start

# Guess what? It stops emp
$ sudo zoo lemp-stop

# What? Yeah, it restarts the emp
$ sudo zoo lemp-restart

# This one shows the status of the services
# A plus sign means the service is running
# A minnus sign means the service is stopped
# If a question mark shows up, the status is unkown
$ sudo zoo lemp-status

```

The unix philosophy is to make it do one thing, but do it well. 'One thing' here is the (l)emp stack, so it also provides the above mentioned nginx specific commands:

```bash
$ sudo zoo new site site.app

```

> The animals from the Zoo need a superuser to help then escape their cages and conquer the world, so use sudo


This command will make a new file inside the `/etc/nginx/sites-available` called `site`, create a link to it inside the `/etc/nginx/sites-enabled` and add a line to your `/etc/hosts` file, at line number 4 with `site.app`. You'll be presented vi ready to edit the `/etc/nginx/sites-available/site`.
Make your changes, save and nginx will automatically restart.


There is another command, for Laravel specific apps. If you're using Laravel, make sure to run this command first:

> For Laravel, you'll need this:

```bash
# cd into the repo folder
$ sudo mv templates/laravel /etc/nginx/sites-available/laravel

```
This will create the file the animals need to create your Laravel servers.

After the file is set, you may run:


```bash
$ sudo zoo laravel site site.app

``` 

If you want to delete a config file from one of your sites, zoo also provides a command for that:

```bash
$ sudo zoo delete site

```

This command removes the files from both nginx folders.

> It won't remove the entry at your `hosts` file, so you can still use it later on


### But why bash?

The idea behind zoo is to make it easy to use, tweak and collaborate. Almost everybody working with PHP knows a little bit of bash.

### But why vi?

You can easily change vi with your editor of choice, by editing the `EDITOR` variable inside the `zoo` file.

### Is there a Mac release?

Not right now.

### How to contribute?

Fork it, tweak it, use it, update it.


