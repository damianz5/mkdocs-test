#  Media Field Type

This Field Type represents and handles media (audio/video) binary file.

| Name    | Internal name | Expected input |
|---------|---------------|----------------|
| `Media` | `ezmedia`     | `mixed`        |

## Description

This Field Type represents and handles a media (audio/video) binary file.

It is capable of handling following types of files:

-   Apple QuickTime
-   Adobe Flash
-   Microsoft Windows Media
-   Real Media
-   Silverlight
-   HTML5 Video
-   HTML5 Audio

## PHP API Field Type 

### Input expectations

| Type                                    | Description                                                                             | Example                           |
|-----------------------------------------|-----------------------------------------------------------------------------------------|-----------------------------------|
| `string`                                | Path to the media file.                                                                 | `/Users/jane/butterflies.mp4`     |
| `eZ\Publish\Core\FieldType\Media\Value` | Media FieldType Value Object with path to the media file as the value of `id` property. | See `Value` object section below. |

### Value object

##### Properties

**`eZ\Publish\Core\FieldType\Media\Value`** offers the following properties.

Note that both **`Media`** and **`BinaryFile`** Value and Type inherit from the **`BinaryBase`** abstract Field Type and share common properties.

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
<td><code>id</code></td>
<td>string</td>
<td><p>Media file identifier. This ID depends on the <a href="https://doc.ez.no/display/DEVELOPER/Clustering#Clustering-Binaryfilesclustering">IO Handler</a> that is being used. With the native, default handlers (FileSystem and Legacy), the ID is the file path, relative to the binary file storage root dir (<code>var/&lt;vardir&gt;/storage/original</code> by default).</p></td>
<td>application/63cd472dd7819da7b75e8e2fee507c68.<span>mp4</span></td>
</tr>
<tr class="even">
<td><code>fileName</code></td>
<td>string</td>
<td>The human-readable file name, as exposed to the outside. Used when sending the file for download in order to name the file.</td>
<td>butterflies.mp4</td>
</tr>
<tr class="odd">
<td><code>fileSize</code></td>
<td>int</td>
<td>File size, in bytes.</td>
<td>1077923</td>
</tr>
<tr class="even">
<td><code>mimeType</code></td>
<td>string</td>
<td>The file's mime type.</td>
<td><p>video/mp4</p></td>
</tr>
<tr class="odd">
<td><code>uri</code></td>
<td>string</td>
<td><p>The binary file's HTTP uri. If the URI doesn't include a host or protocol, it applies to the request domain.</p>
<p><strong><strong>The URI is not publicly readable, and must NOT be used to link to the file for download.</strong></strong> Use <code>ez_render_field</code> to generate a valid link to the download controller.</p></td>
<td>/var/ezdemo_site/storage/original/application/63cd472dd7819da7b75e8e2fee507c68.<span>mp4</span></td>
</tr>
<tr class="even">
<td><code>hasController</code></td>
<td>boolean</td>
<td><p><span>Whether the media has a controller when being displayed.</span></p></td>
<td>true</td>
</tr>
<tr class="odd">
<td><code>autoplay</code></td>
<td>boolean</td>
<td><p><span>Whether the media should be automatically played.</span></p></td>
<td>true</td>
</tr>
<tr class="even">
<td><code>loop</code></td>
<td>boolean</td>
<td><p><span>Whether the media should be played in a loop.</span></p></td>
<td>false</td>
</tr>
<tr class="odd">
<td><code>height</code></td>
<td>int</td>
<td><p><span>Height of the media.</span></p></td>
<td>300</td>
</tr>
<tr class="even">
<td><code>width</code></td>
<td>int</td>
<td><p><span>Width of the media.</span></p></td>
<td>400</td>
</tr>
<tr class="odd">
<td><code>path</code></td>
<td>string</td>
<td><p><strong><span style="color: rgb(255,0,0);">deprecated</span><br />
</strong>Renamed to <code>id</code> starting from eZ Publish 5.2. Can still be used, but it is recommended not to use it anymore as it will be removed.</p></td>
<td> </td>
</tr>
</tbody>
</table>

### Hash format

The hash format mostly matches the value object. It has the following keys:

-   `id`
-   `path` (for backwards compatibility)
-   `fileName`
-   `fileSize`
-   `mimeType`
-   `uri`
-   `hasController`
-   `autoplay`
-   `loop`
-   `height`
-   `width`

### Validation

The Field Type supports `FileSizeValidator`, defining maximum size of media file in bytes:

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><div class="tablesorter-header-inner">
Name
</div></th>
<th><div class="tablesorter-header-inner">
Type
</div></th>
<th><div class="tablesorter-header-inner">
Default value
</div></th>
<th><div class="tablesorter-header-inner">
Description
</div></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>maxFileSize</code></td>
<td><code>int</code></td>
<td><span>false</span></td>
<td>Maximum size of the file in bytes.</td>
</tr>
</tbody>
</table>

**Example of using Media Field Type validator in PHP**

```
use eZ\Publish\Core\FieldType\Media\Type;

$contentTypeService = $repository->getContentTypeService();
$mediaFieldCreateStruct = $contentTypeService->newFieldDefinitionCreateStruct( "media", "ezmedia" );

// Setting maximum file size to 5 megabytes
$mediaFieldCreateStruct->validatorConfiguration = array(
    "FileSizeValidator" => array(
        "maxFileSize" => 5 * 1024 * 1024
    )
);
```

### Settings

The Field Type supports `mediaType` setting, defining how the media file should be handled in output.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><div class="tablesorter-header-inner">
Name
</div></th>
<th><div class="tablesorter-header-inner">
Type
</div></th>
<th><div class="tablesorter-header-inner">
Default value
</div></th>
<th><div class="tablesorter-header-inner">
Description
</div></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>mediaType</code></td>
<td><code>mixed</code></td>
<td><pre><code>Type::TYPE_HTML5_VIDEO</code></pre></td>
<td>Type of the media, accepts one of the predefined constants.</td>
</tr>
</tbody>
</table>

List of all available `mediaType` constants defined in **`eZ\Publish\Core\FieldType\Media\Type`** class:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><div class="tablesorter-header-inner">
Name
</div></th>
<th><div class="tablesorter-header-inner">
Description
</div></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre><code>TYPE_FLASH</code></pre></td>
<td>Adobe Flash</td>
</tr>
<tr class="even">
<td><pre><code>TYPE_QUICKTIME</code></pre></td>
<td>Apple QuickTime</td>
</tr>
<tr class="odd">
<td><pre><code>TYPE_REALPLAYER</code></pre></td>
<td>Real Media</td>
</tr>
<tr class="even">
<td><pre><code>TYPE_SILVERLIGHT</code></pre></td>
<td>Silverlight</td>
</tr>
<tr class="odd">
<td><pre><code>TYPE_WINDOWSMEDIA</code></pre></td>
<td><p>Microsoft Windows Media</p></td>
</tr>
<tr class="even">
<td><pre><code>TYPE_HTML5_VIDEO</code></pre></td>
<td>HTML5 Video</td>
</tr>
<tr class="odd">
<td><pre><code>TYPE_HTML5_AUDIO</code></pre></td>
<td><p>HTML5 Audio</p></td>
</tr>
</tbody>
</table>

**Example of using Media Field Type settings in PHP**

```
use eZ\Publish\Core\FieldType\Media\Type;
 
$contentTypeService = $repository->getContentTypeService();
$mediaFieldCreateStruct = $contentTypeService->newFieldDefinitionCreateStruct( "media", "ezmedia" );

// Setting Adobe Flash as the media type
$mediaFieldCreateStruct->fieldSettings = array(
    "mediaType" => Type::TYPE_FLASH,
);
```
