#  PHP's built-in server

## Description

PHP, in 5.4 and later, comes with a [built-in webserver for development purposes](http://php.net/manual/en/features.commandline.webserver.php). This is very handy, as it allows you to **kickstart development quickly**, avoiding having to install and configure [Apache](https://github.com/ezsystems/ezplatform/tree/master/doc/apache2) / [Nginx](https://github.com/ezsystems/ezplatform/tree/master/doc/nginx). All you need here is PHP 5.4+ with command line binary.

## Usage

Symfony comes with a wrapper script for booting the built-in webserver: `server:run`. It's a nice shortcut as it will correctly set the web root depending on your configuration, and with eZ Platform it can be used as is.

Use this command for **local development purpose only**!
DO NOT use this on production servers, the use of `--env=prod` below is just showcasing that you can use the command both with Symfony's dev and prod environment depending on if you are debugging or just testing out your application locally.

##### Examples

The following example will start the webserver on <http://127.0.0.1:8000> on your machine, in Symfony dev environment for debug use:

**Debug example**

```
php app/console server:run
```

The following example will start the webserver on [http://localhost:8000](http://localhost:8000/) on your machine, in Symfony prod environment for demo/testing use:

**Testing/Demo example**

```
php app/console server:run --env=prod localhost:8000
```

 

##### **Help with the command**

As with any Symfony command, you may execute the command with a `-h` flag to get up-to-date help text for the command:

**Help info example**

```
php app/console server:run -h
```

 

 

#### Further reading:

<http://symfony.com/doc/current/cookbook/web_server/built_in.html>
