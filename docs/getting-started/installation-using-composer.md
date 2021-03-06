#  Installation Using Composer

## Get Composer

If you don't have it already, install Composer, the command-line package manager for PHP. You'll have to have a copy of Git installed on your machine. The following command uses PHP to download and run the Composer installer, and should be entered on your terminal and executed by pressing Return or Enter:

```
php -r "readfile('https://getcomposer.org/installer');" | php
```

For further information about Composer usage see [Using Composer](Using-Composer_31431588.html) .

## eZ Platform Installation

The commands below assume you have Composer installed globally, a copy of git on your system, and your **MySQL/MariaDB server *already set up* with a database**. Once you've got all the required PHP extensions installed, you can get eZ Platform up and running with the following commands:

```
composer create-project --no-dev --keep-vcs ezsystems/ezplatform ezplatform
cd ezplatform

php app/console ezplatform:install clean
```

For more information about the availables options with Composer commands, see[the Composer documentation](https://getcomposer.org/doc/03-cli.md).

 

### Installing another distribution

eZ Platform exists in several distributions, listed in [Step 1: Installation](31429538.html), some with their own installer as shown in the example below. To install The Enterprise Edition you need an eZ Enterprise subscription and have to [set up Composer for that](Using-Composer_31431588.html).

**eZ Platform Enterprise Edition**

```
composer create-project --no-dev --keep-vcs ezsystems/ezstudio
cd ezstudio

# Options are listed on php app/console ezplatform:install -h
php app/console ezplatform:install studio-clean
```

### Installing another version

The instructions above show how to install the latest stable version, however with Composer you can specify the version and stability as well if you want to install something else. Using `composer create-project -h` you can see how you can specify another version:

> create-project \[options\] \[--\] \[&lt;package&gt;\] \[&lt;directory&gt;\] \[&lt;version&gt;\]
>
>  
>
> Arguments:
>
>   &lt;package&gt;                            Package name to be installed
>
>   &lt;directory&gt;                            Directory where the files should be created
>
>   &lt;version&gt;                              Version, will default to latest

Versions [can be expressed in many ways in Composer,](https://getcomposer.org/doc/articles/versions.md) but the ones we recommend are:

-   Exact git tag: `v1.3.1`
-   Tilde for locking down the minor version: `~1.3.0`
    -   Equals: 1.3.\* 
-   Caret for allowing all versions within a major: `^1.3.0`
    -   Equals: 1.\* &lt;= 1.3.0

What was described above concerns stable releases, however [Composer lets you specify stability in many ways](https://getcomposer.org/doc/articles/versions.md#stability), mainly:

-   Exact git tag: `v1.4.0-beta1`
-   Stability flag on a given version: `1.4.0@beta`
    -   Equals: versions of 1.4.0 in stability order of: beta, rc, stable
    -   This can also be combined with tilde and caret to match ranges of unstable releases
-   Stability flag while omitting version: '`@alpha` equals latest available alpha release

Example:

```
composer create-project --no-dev --keep-vcs ezsystems/ezplatform-demo ezplatform @beta
cd ezplatform

php app/console ezplatform:install demo
```

#### Related:

-   [Installation Guide for OS X](Installation-Guide-for-OS-X_31431738.html)
-   [Installation Guide for Unix-Based Systems](Installation-Guide-for-Unix-Based-Systems_31431755.html)
