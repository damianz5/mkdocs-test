#  ParentUserGroupLimitation 

A Limitation to specify that only Users with at least one common *direct* User group with the owner of the parent Location of a Content item get a certain access right, used by `content/create` permission.

|                 |                                                                              |
|-----------------|------------------------------------------------------------------------------|
| Identifier      | `ParentGroup`                                                                |
| Value Class     | `eZ\Publish\API\Repository\Values\User\Limitation\ParentUserGroupLimitation` |
| Type Class      | `eZ\Publish\Core\Limitation\ParentUserGroupLimitationType`                   |
| Criterion used  | n/a                                                                          |
| Role Limitation | no                                                                           |

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
<td>1</td>
<td>&quot;self&quot;</td>
<td><p>Only a User who has at least one common <em>direct</em> user group with owner of the parent Location gets access</p></td>
</tr>
</tbody>
</table>

 

 
