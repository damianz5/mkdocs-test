#  NewSectionLimitation 

A Limitation to specify if the User has access to (assigning) a given Section (to Content).

In the `section/assign` Policy you can combine this with `SectionLimitation` to limit both from and to values.

|                 |                                                                         |
|-----------------|-------------------------------------------------------------------------|
| Identifier      | `NewSection`                                                            |
| Value Class     | `eZ\Publish\API\Repository\Values\User\Limitation\NewSectionLimitation` |
| Type Class      | `eZ\Publish\Core\Limitation\NewSectionLimitationType`                   |
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
<td><code>&lt;Session_id&gt;</code></td>
<td><code>&lt;Session_name&gt;</code></td>
<td><p>All valid section ids can be set as value(s)</p></td>
</tr>
</tbody>
</table>

 
