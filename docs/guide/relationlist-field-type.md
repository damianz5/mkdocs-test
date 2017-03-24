#  RelationList Field Type

This Field Type represents one or multiple relations to content.

| Name           | Internal name          | Expected input |
|----------------|------------------------|----------------|
| `RelationList` | `ezobjectrelationlist` | `mixed`        |

## Description

This Field Type makes possible to store and retrieve values of relation to content.

## PHP API Field Type 

### Input expectations

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><div class="tablesorter-header-inner">
Type
</div></th>
<th><div class="tablesorter-header-inner">
Description
</div></th>
<th><div class="tablesorter-header-inner">
Example
</div></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>int|string</code></td>
<td>Id of the related Content item</td>
<td><code>42</code></td>
</tr>
<tr class="even">
<td><code>array</code></td>
<td>An array of related Content IDs</td>
<td><code>array( 24, 42 )</code></td>
</tr>
<tr class="odd">
<td><pre><code>eZ\Publish\API\Repository\Values\Content\ContentInfo</code></pre></td>
<td><p>ContentInfo instance of the related Content</p></td>
<td> </td>
</tr>
<tr class="even">
<td><code>eZ\Publish\Core\FieldType\RelationList\Value</code></td>
<td>RelationList Field Type Value Object</td>
<td>See Value Object documentation section below.</td>
</tr>
</tbody>
</table>

### Value Object

##### Properties

`eZ\Publish\Core\FieldType\RelationList\Value` contains following properties.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Property</th>
<th>Type</th>
<th>Description</th>
<th>Example</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><code>destinationContentIds</code></p></td>
<td><code>array</code></td>
<td>An array of related Content ids</td>
<td><code>array( 24, 42 )</code></td>
</tr>
</tbody>
</table>

**Value object content example**

```
$relationList->destinationContentId = array(
    $contentInfo1->id,
    $contentInfo2->id,
    170
);
```

##### Constructor

The `RelationList``\Value` constructor will initialize a new Value object with the value provided. It expects a mixed array as value.

**Constructor example**

```
// Instantiates a RelationList Value object
$relationListValue = new RelationList\Value(
    array(
        $contentInfo1->id,
        $contentInfo2->id,
        170     
    )
);
```

### Validation

This Field Type validates if the `selectionMethod` specified is 0 (`self::SELECTION_BROWSE)` or 1 (`self::SELECTION_DROPDOWN)`. A validation error is thrown if the value does not match.

Also validates if the `selectionDefaultLocation` specified is `null`, `string` or `integer`. If the type validation fails a validation error is thrown.

And validates if the value specified in `selectionContentTypes` is an array. If not, a validation error in given.

### Settings

The field definition of this Field Type can be configured with following options:

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
<td><p><code>selectionMethod</code></p></td>
<td><code>mixed</code></td>
<td><pre><code>SELECTION_BROWSE</code></pre></td>
<td>Method of selection in the administration interface</td>
</tr>
<tr class="even">
<td><p><code>selectionDefaultLocation</code></p></td>
<td><code>string|integer</code></td>
<td><code>null</code></td>
<td>Id of the default Location for the selection when using administration interface</td>
</tr>
<tr class="odd">
<td><p><code>selectionContentTypes</code></p></td>
<td><code>array</code></td>
<td><code>array()</code></td>
<td>An array of ContentType ids that are allowed for related Content</td>
</tr>
</tbody>
</table>

Following selection methods are available:

| Name                | Description                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------------------|
| SELECTION\_BROWSE   | Selection will use browse mode                                                                                |
| SELECTION\_DROPDOWN | Selection control will use dropdown control containing the Content list in the default Location for selection |

NOTE: Dropdown not implemented in Platform UI yet, only browse is used currently.

**Example of using settings in PHP**

```
use eZ\Publish\Core\FieldType\RelationList\Type;

$settings = array(
    "selectionMethod" => Type::SELECTION_BROWSE,
    "selectionDefaultLocation" => null,
    "selectionContentTypes" => array()
 );
```

 
