#  Web Server

# Configuration files

You can find configuration files in the `doc/` directory of the software, for the following web server engines:

-   [Apache](https://github.com/ezsystems/ezplatform/tree/master/doc/apache2)
-   [Nginx](https://github.com/ezsystems/ezplatform/tree/master/doc/nginx)

and also configuration files for

-   [Varnish](https://github.com/ezsystems/ezplatform/blob/master/doc/varnish/varnish.md)

# Generate vhost config script

In addition to that, you have a Bash script for generating a virtual host configuration based on template, containing variables among the once define below.
For help text, execute: `./bin/vhost.sh -h`

## Help

 

```
./bin/vhost.sh [-h|--help]
```

 

## Usage

```
$> ./bin/vhost.sh --basedir=/var/www/ezplatform \\

  --template-file=doc/apache2/vhost.template \\

  | sudo tee /etc/apache2/sites-enabled/my-site > /dev/null
```

Default values will be fetched from the environment variables `$env_list`, but might be overridden using the arguments listed below.

## Arguments

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Option</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>--basedir=&lt;path&gt;</p></td>
<td>Root path to where the eZ installation is placed, used for &lt;path&gt;/web</td>
</tr>
<tr class="even">
<td><p>--template-file=&lt;file.template&gt;</p></td>
<td><p>The file to use as template for the generated output file</p></td>
</tr>
<tr class="odd">
<td>--host-name=localhost</td>
<td>Primary host name, default &quot;localhost&quot;</td>
</tr>
<tr class="even">
<td><p>--host-alias=*.localhost</p></td>
<td>Space separated list of host aliases, default &quot;*.localhost&quot;</td>
</tr>
<tr class="odd">
<td><p>--ip=*|127.0.0.1</p></td>
<td>IP address web server should accept traffic on.</td>
</tr>
<tr class="even">
<td><p>--port=80]</p></td>
<td>Port number web server should listen to</td>
</tr>
<tr class="odd">
<td><p>--sf-env=prod|dev|..</p></td>
<td>Symfony environment used for the virtual host, default is &quot;prod&quot;</td>
</tr>
<tr class="even">
<td><p>--sf-debug=0|1</p></td>
<td>Set if Symfony debug should be on, by default on if env is &quot;dev&quot;</td>
</tr>
<tr class="odd">
<td><p>--sf-trusted-proxies=127.0.0.1,....</p></td>
<td>Comma separated trusted proxies (e.g. Varnish), that we can get client IP from</td>
</tr>
<tr class="even">
<td><p>--sf-http-cache=0|1</p></td>
<td>To disable Symfony HTTP cache Proxy for using a different reverse proxy
<p>By default disabled when env is &quot;dev&quot;, enabled otherwise.</p></td>
</tr>
<tr class="odd">
<td>--sf-http-cache-class=&lt;class-file.php&gt;</td>
<td>To specify a different class than the default one, to use as the Symfony proxy</td>
</tr>
<tr class="even">
<td>--sf-classloader-file=&lt;class-file.php&gt;</td>
<td>To specify a different class than the default one, to use for PHP auto loading</td>
</tr>
<tr class="odd">
<td><p>--body-size-limit=&lt;int&gt;</p></td>
<td>Limit in megabytes for max size of request body, 0 value disables limit</td>
</tr>
<tr class="even">
<td>--request-timeout=&lt;int&gt;</td>
<td>Limit in seconds before timeout of request, 0 value disables timeout limit</td>
</tr>
</tbody>
</table>
