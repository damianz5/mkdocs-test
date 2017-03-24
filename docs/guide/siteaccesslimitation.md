#  SiteAccessLimitation

A Limitation to specify in which siteaccesses a certain permission applies, used by `user/login`.

|                 |                                                                         |
|-----------------|-------------------------------------------------------------------------|
| Identifier      | `SiteAccess`                                                            |
| Value Class     | `eZ\Publish\API\Repository\Values\User\Limitation\SiteAccessLimitation` |
| Type Class      | `eZ\Publish\Core\Limitation\SiteAccessLimitationType`                   |
| Criterion used  | n/a                                                                     |
| Role Limitation | no                                                                      |

###### Possible values

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Value</td>
<td>UI value</td>
<td>Description</td>
</tr>
<tr class="even">
<td><code>&lt;siteaccess_hash&gt;</code></td>
<td><code>&lt;siteaccess_name&gt;</code></td>
<td><p>Hash is calculated in the following way in legacy in default 64bit mode: <code>sprintf( '%u', crc32( $siteAccessName ) )</code></p></td>
</tr>
</tbody>
</table>

###### Legacy compatibility notes

1.   `SiteAccess` Limitation is deprecated and is not used actively in Public API, but is allowed for being able to read / create Limitations for legacy.

 
