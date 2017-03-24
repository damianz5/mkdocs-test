#  Float Field Type

This Field Type represents a float value.

| Name    | Internal name | Expected input |
|---------|---------------|----------------|
| `Float` | `ezfloat`     | `float`        |

## Description

This Field Type stores numeric values which will be provided as floats.

## PHP API Field Type 

### Input expectations

The Field Type expects a number as input. Both decimal and integer numbers are accepted.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Type</th>
<th>Example</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>float</code></td>
<td><p><code>194079.572</code></p></td>
</tr>
<tr class="even">
<td><code>int</code></td>
<td><code>144</code></td>
</tr>
</tbody>
</table>

### Value object

##### Properties

The Value class of this field type contains the following properties:

| Property | Type    | Description                                                        |
|----------|---------|--------------------------------------------------------------------|
| `$value` | `float` | This property will be used to store the value provided as a float. |

**Value object content example**

```
use eZ\Publish\Core\FieldType\Float\Type;

// Instantiates a Float Value object
$floatValue = new Type\Value();

$float->value = 284.773
```

##### Constructor

The `Float``\Value` constructor will initialize a new Value object with the value provided. It expects a numeric value with or without decimals.

**Constructor example**

```
use eZ\Publish\Core\FieldType\Float\Type;

// Instantiates a Float Value object
$floatValue = new Type\Value( 284.773 );
```

### Validation

This Field Type supports `FloatValueValidator`, defining maximal and minimal float value:

<table>
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
<td><code>minFloatValue</code></td>
<td><code>float</code></td>
<td><code>null</code><br />
</td>
<td>This setting defines the minimum value this FieldType will allow as input.</td>
</tr>
<tr class="even">
<td><code>maxFloatValue</code></td>
<td><code>float</code></td>
<td><code>null</code><br />
</td>
<td>This setting defines the maximum value this FieldType will allow as input.</td>
</tr>
</tbody>
</table>

**Validator configuration example in PHP**

```
use eZ\Publish\Core\FieldType\Float\Type;

$contentTypeService = $repository->getContentTypeService();
$floatFieldCreateStruct = $contentTypeService->newFieldDefinitionCreateStruct( "float", "ezfloat" );

// Accept only numbers between 0.1 and 203.99
$floatFieldCreateStruct->validatorConfiguration = array(
    "FileSizeValidator" => array(  
        "minFloatValue" => 0.1,
        "maxFloatValue" => 203.99
    )
);
```

### Settings

This Field Type does not support settings.
