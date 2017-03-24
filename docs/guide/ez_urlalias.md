#  ez\_urlalias

#### Description

`ez_urlalias` is a not a real Twig helper, but a **special route name** for generating URLs for a Location from the given parameters.

#### Prototype and Arguments

**path(**  eZ\\Publish\\API\\Repository\\Values\\Content\\Location|string name\[, array parameters\]\[, bool absolute\]  **)**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Argument name</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>name</td>
<td><span class="sd">string | \eZ\Publish\API\Repository\Values\Content\Location<br />
</span></td>
<td><span class="sd">The name of the route or a Location instance</span></td>
</tr>
<tr class="even">
<td>parameters</td>
<td>array</td>
<td><p><span>An hash of parameters:</span></p>
<ul>
<li><code>                     locationId                   </code></li>
<li><span> <code>contentId</code> <span>(as of 5.4 / 2014.11) </span> </span></li>
</ul></td>
</tr>
<tr class="odd">
<td>absolute</td>
<td>boolean</td>
<td><span class="sd">Whether to generate an absolute URL</span></td>
</tr>
</tbody>
</table>

#### Working with Location

Linking to other Locations is fairly easy and is done with [native `path()` Twig helper](http://symfony.com/doc/2.3/book/templating.html#linking-to-pages) (or `url()` if you want to generate absolute URLs). You just have to pass it the Location object and `path()` will generate the URLAlias for you.

```
{# Assuming "location" variable is a valid eZ\Publish\API\Repository\Values\Content\Location object #}
<a href="{{ path( location ) }}">Some link to a location</a>
```

 

#### I don't have the Location object

##### Generating a link from a Location ID

```
<a href="{{ path( "ez_urlalias", {"locationId": 123} ) }}">Some link to a location, with its Id only</a>
```

 

##### Generating a link from a Content ID

```
<a href="{{ path( "ez_urlalias", {"contentId": 456} ) }}">Some link from a contentId</a>
```

 

**Important: Links generated from a Content ID will point to its main location.**

#### Error management

For Location alias setup 301 redirect to Location's current URL when:

1.  alias is history
2.  alias is custom with forward flag true
3.  requested URL is not case-sensitive equal with the one loaded

Under the hood

In the backend, `path()` uses the Router to generate links.

This makes it also easy to generate links from PHP, via the `router` service.
