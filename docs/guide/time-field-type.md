#  Time Field Type

This Field Type represents time information.

| Name   | Internal name | Expected input type |
|--------|---------------|---------------------|
| `Time` | `eztime`      | `mixed`             |

## Description

This Field Type makes possible to store and retrieve time information.

Date information is **not stored**.

What is stored is the number of seconds, calculated from the beginning of the day in the given or the environment timezone.

## PHP API Field Type

### Input expectations

If input value is of type **`string`** or **`integer`**, it will be passed directly to the [PHP's built-in **`\DateTime`** class](http://www.php.net/manual/en/datetime.construct.php) constructor, therefore the same input format expectations apply.

It is also possible to directly pass an instance of **`\DateTime`**.

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
<td><code>string</code></td>
<td><code>&quot;2012-08-28 12:20 Europe/Berlin&quot;</code></td>
</tr>
<tr class="even">
<td><pre><code>integer</code></pre></td>
<td><pre><code>1346149200</code></pre></td>
</tr>
<tr class="odd">
<td><pre><code>\DateTime</code></pre></td>
<td><pre><code>new \DateTime()</code></pre></td>
</tr>
</tbody>
</table>

### Value object

##### Properties

The Value class of this field type contains the following properties:

| Property | Type           | Description                                                                       |
|----------|----------------|-----------------------------------------------------------------------------------|
| `$time`  | `integer|null` | Holds the time information as a number of seconds since the beginning of the day. |

##### Constructor

The constructor for this value object will initialize a new Value object with the value provided. It accepts an integer representing the number of seconds since the beginning of the day.

##### String representation

String representation of the date value will generate the date string in the format "H:i:s" as accepted by [PHP's built-in **`date()`** function](http://www.php.net/manual/en/function.date.php).

Example:

> `"12:14:56"`

### Hash format

Value in hash format is an integer representing a number of seconds since the beginning of the day.

Example:

> `36000`

### Validation

This Field Type does not perform validation of the input value.

### Settings

The field definition of this Field Type can be configured with several options:

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
<td><pre><code>useSeconds</code></pre></td>
<td><code>boolean</code></td>
<td><code>false</code></td>
<td>Used to control displaying of seconds in the output.</td>
</tr>
<tr class="even">
<td><pre><code>defaultType</code></pre></td>
<td><pre><code>Type::DEFAULT_EMPTY
Type::DEFAULT_CURRENT_TIME</code></pre></td>
<td><pre><code>Type::DEFAULT_EMPTY</code></pre></td>
<td>The constant used here defines default input value when using administration interface.</td>
</tr>
</tbody>
</table>

**Time Field Type example settings**

```
use eZ\Publish\Core\FieldType\Time\Type;

$settings = array(
    "defaultType" => DateAndTime::DEFAULT_EMPTY
);
```

## Template rendering

The template called by [the **ez\_render\_field()** Twig function](Content-Rendering_31429679.html) while rendering a Date field has access to the following parameters:

| Parameter | Type     | Default | Description                                                                                                                       |
|-----------|----------|---------|-----------------------------------------------------------------------------------------------------------------------------------|
| `locale`  | `string` |         | Internal parameter set by the system based on current request locale or if not set calculated based on the language of the field. |

Example:

```
{{ ez_render_field(content, 'time') }}
```

 
