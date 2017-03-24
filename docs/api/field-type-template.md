#  Field Type template

Created by Dominika Kurek, last modified on Apr 22, 2016

# Defining your Field Type template

In order to be used by [`ez_render_field()` Twig helper](https://doc.ez.no/display/TECHDOC/ez_render_field), you need to define a **template containing a block** dedicated to the Field display.

This block consists on a piece of template receiving specific variables you can use to make the display vary.

You will find examples with built-in Field Types in [EzPublishCoreBundle/Resources/views/content\_fields.html.twig](https://github.com/ezsystems/ezpublish-kernel/blob/master/eZ/Bundle/EzPublishCoreBundle/Resources/views/content_fields.html.twig)

**Template for a FieldType with "myfieldtype" identifier**

```
{% block myfieldtype_field %}
{# Your code here #}
{% endblock %}
```

By convention, your block **must** be named `<fieldTypeIdentifier>_field`.

## Exposed variables

<table>
<thead>
<tr class="header">
<th>Name</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>field</code></td>
<td><code>eZ\Publish\API\Repository\Values\Content\Field</code></td>
<td>The field to display</td>
</tr>
<tr class="even">
<td><code>contentInfo</code></td>
<td><code>eZ\Publish\API\Repository\Values\Content\ContentInfo</code></td>
<td>The ContentInfo to which the field belongs to</td>
</tr>
<tr class="odd">
<td><code>versionInfo</code></td>
<td><code>eZ\Publish\API\Repository\Values\Content\VersionInfo</code></td>
<td>The VersionInfo to which the field belongs to</td>
</tr>
<tr class="even">
<td><code>fieldSettings</code></td>
<td><code>mixed</code></td>
<td>Settings of the field (depends on the FieldType)</td>
</tr>
<tr class="odd">
<td><code>parameters</code></td>
<td><code>hash</code></td>
<td>Options passed to <code>ez_render_field()</code> under the <code>parameters</code> key</td>
</tr>
<tr class="even">
<td><code>attr</code></td>
<td><code>hash</code></td>
<td>The attributes to add the generate the HTML markup.<br />
Contains at least a <strong><code>class</code></strong> entry, containing <code>&lt;fieldtypeidentifier&gt;-field</code></td>
</tr>
</tbody>
</table>

## Reusing blocks

To ease Field Type template development, you can take advantage of all defined blocks by using the [block() function](http://twig.sensiolabs.org/doc/functions/block.html).

You can for example take advantage of `simple_block_field`, `simple_inline_field` or `field_attributes` blocks provided in [content\_fields.html.twig](https://github.com/ezsystems/ezpublish-kernel/blob/master/eZ/Bundle/EzPublishCoreBundle/Resources/views/content_fields.html.twig#L413).

Warning

To be able to reuse built-in blocks, **your template must inherit from `EzPublishCoreBundle::content_fields.html.twig`**.

## Registering your template

 

To make your template available, you must register it to the system.

**app/config/ezplatform.yml**

```
ezpublish:
    system:
        my_siteaccess:
            field_templates:
                - 
                    template: "AcmeTestBundle:fields:my_field_template.html.twig"
                    # Priority is optional (default is 0). The higher it is, the higher your template gets in the list.
                    priority: 10
```

You can define these rules in a dedicated file instead of `app/config/ezplatform.yml`. Read the [cookbook recipe to learn more about it](Importing-settings-from-a-bundle_31429803.html).
