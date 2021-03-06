#  SubtreeLimitation 

A Limitation to specify if the User has access to Content within a specific subtree, in case of `content/create` the parent subtree is evaluated.

|                 |                                                                      |
|-----------------|----------------------------------------------------------------------|
| Identifier      | `Subtree`                                                            |
| Value Class     | `eZ\Publish\API\Repository\Values\User\Limitation\SubtreeLimitation` |
| Type Class      | `eZ\Publish\Core\Limitation\SubtreeLimitationType`                   |
| Criterion used  | `eZ\Publish\API\Repository\Values\Content\Query\Criterion\Subtree`   |
| Role Limitation | yes                                                                  |

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
<td><code>&lt;Location_pathString&gt;</code></td>
<td><code>&lt;Location_name&gt;</code></td>
<td><p>All valid location <code>pathStrings</code> can be set as value(s)</p></td>
</tr>
</tbody>
</table>

 
