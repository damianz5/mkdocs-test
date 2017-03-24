#  XmlText Field Type

The XmlText Field Type isn't officially supported by eZ Platform. It can be installed by requiring ezsystems/ezplatform-xmltext-fieldtype. PlatformUI does not support wysiwyg editing of this type of Field.

This Field Type validates and stores formatted text using the eZ Publish legacy format, ezxml. 

| Name      | Internal name | Expected input |
|-----------|---------------|----------------|
| `XmlText` | `ezxmltext`   | `mixed`        |

## Input expectations

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type</th>
<th>Description</th>
<th>Example</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>string</code></td>
<td>XML document in the Field Type internal format as a string.</td>
<td><p>See the example below.</p></td>
</tr>
<tr class="even">
<td><pre><code>eZ\Publish\Core\FieldType\XmlText\Input</code></pre></td>
<td>An instance of the class implementing Field Type abstract <strong><code>Input</code></strong> class.</td>
<td><span>See the example below.</span></td>
</tr>
<tr class="odd">
<td><pre><code>eZ\Publish\Core\FieldType\XmlText\Value</code></pre></td>
<td><span>An instance of the Field Type <strong><code>Value</code></strong> object.</span></td>
<td><span>See the example below.</span></td>
</tr>
</tbody>
</table>

### Example of the Field Type's internal format

```
<?xml version="1.0" encoding="utf-8"?>
<section
    xmlns:custom="http://ez.no/namespaces/ezpublish3/custom/"
    xmlns:image="http://ez.no/namespaces/ezpublish3/image/"
    xmlns:xhtml="http://ez.no/namespaces/ezpublish3/xhtml/">
    <paragraph>This is a paragraph.</paragraph>
</section>
```

### For XHTML Input

The eZ XML output uses &lt;strong&gt; and &lt;em&gt; by default, respecting the semantic XHTML notation.

Learn more about &lt;strong&gt;, &lt;b&gt;, &lt;em&gt;, &lt;i&gt;

-   [Read the share.ez.no forum about our choice of semantic tags with eZ XML](http://share.ez.no/forums/ez-publish-5-platform/strong-vs-b-and-em-vs-i)
-   Learn more [about the semantic tags vs the presentational tags.](http://html5doctor.com/i-b-em-strong-element/)

## Input object API

`Input` object is intended as a vector for different input formats. It should accept input value in a foreign format and convert it to the Field Type's internal format.

It should implement abstract **`eZ\Publish\Core\FieldType\XmlText\Input`** class, which defines only one method:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Method</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre><code>getInternalRepresentation</code></pre></td>
<td>The method should return the input value in the internal format.</td>
</tr>
</tbody>
</table>

At the moment there is only one implementation of the **`Input`** class, **`eZ\Publish\Core\FieldType\XmlText\Input\EzXml`**, which accepts input value in the internal format, and therefore only performs validation of the input value.

**Example of using the Input object**

```
...
 
use eZ\Publish\Core\FieldType\XmlText\Input\EzXml as EzXmlInput;

...

$contentService = $repository->getContentService();
$contentTypeService = $repository->getContentTypeService();
 
$contentType = $contentTypeService->loadContentTypeByIdentifier( "article" );
$contentCreateStruct = $contentService->newContentCreateStruct( $contentType, "eng-GB" );

$inputString = <<<EZXML
<?xml version="1.0" encoding="utf-8"?>
<section
    xmlns:custom="http://ez.no/namespaces/ezpublish3/custom/"
    xmlns:image="http://ez.no/namespaces/ezpublish3/image/"
    xmlns:xhtml="http://ez.no/namespaces/ezpublish3/xhtml/">
    <paragraph>This is a paragraph.</paragraph>
</section>
EZXML;
 
$ezxmlInput = new EzXmlInput( $inputString );

$contentCreateStruct->setField( "description", $ezxmlInput );
 
...
```

## Value object API

**`eZ\Publish\Core\FieldType\XmlText\Value`** offers following properties:

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Property</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>xml</code></td>
<td><pre><code>DOMDocument</code></pre></td>
<td>Internal format value as an instance of <span style="line-height: 1.4285715;"><code>DOMDocument</code>.</span></td>
</tr>
</tbody>
</table>

## Validation

Validation of the internal format is performed in the **`eZ\Publish\Core\FieldType\XmlText\Input\EzXml`** class.

## Settings

Following settings are available:

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Type</th>
<th>Default value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><code>numRows</code></p></td>
<td><code>int</code></td>
<td><code>10</code></td>
<td>Defines the number of rows for the online editor in the administration interface.</td>
</tr>
<tr class="even">
<td><p><code>tagPreset</code></p></td>
<td><code>mixed</code></td>
<td><code>Type::TAG_PRESET_DEFAULT</code></td>
<td><p><span>Preset of tags for the online editor in the administration interface.</span></p></td>
</tr>
</tbody>
</table>

### Tag presets

Following tag presets are available as constants in the **`eZ\Publish\Core\FieldType\XmlText`** class:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Constant</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre><code>TAG_PRESET_DEFAULT</code></pre></td>
<td>Default tag preset.</td>
</tr>
<tr class="even">
<td><pre><code>TAG_PRESET_SIMPLE_FORMATTING</code></pre></td>
<td><p><span>Preset of tags for online editor intended for simple formatting options.</span></p></td>
</tr>
</tbody>
</table>

**Example of using settings in PHP**

```
...
 
use eZ\Publish\Core\FieldType\XmlText\Type;

...

$contentTypeService = $repository->getContentTypeService();
$xmltextFieldCreateStruct = $contentTypeService->newFieldDefinitionCreateStruct( "description", "ezxmltext" );

$xmltextFieldCreateStruct->fieldSettings = array(
    "numRows" => 25,
    "tagPreset" => Type::TAG_PRESET_SIMPLE_FORMATTING
);
 
...
```

 
