#  ParentOwnerLimitation

A Limitation to specify that only the Users who owns all parent Locations of a Content item gets a certain access right, used for `content/create` permission.

|                 |                                                                          |
|-----------------|--------------------------------------------------------------------------|
| Identifier      | `ParentOwner`                                                            |
| Value Class     | `eZ\Publish\API\Repository\Values\User\Limitation\ParentOwnerLimitation` |
| Type Class      | `eZ\Publish\Core\Limitation\ParentOwnerLimitationType`                   |
| Criterion used  | n/a                                                                      |
| Role Limitation | no                                                                       |

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
<td><p>Only the User who is the owner of all parent Locations gets access</p></td>
</tr>
<tr class="odd">
<td>2</td>
<td>&quot;session&quot;</td>
<td><p>Same as &quot;self&quot;</p></td>
</tr>
</tbody>
</table>

###### Legacy compatibility notes

1.  "session" is deprecated and works exactly like "self" in Public API since it has no knowledge of user Sessions
2.  User is no longer auto assumed to be owner of himself and get access create children of own user content object when `Owner` limitation is used in Public API

Workaround for the ParentOwner Limitation on Users (when a User is the parent of the content being created)

To make sure the User gets access to themselves when using (Parent)OwnerLimitation across 4.x and 5.x, the solution is to change the User to be the owner of their own Content item.

This is accomplished using a privileged user to do the following API calls:

```
$user = $userService->loadUser( $userId );
$contentMetadataUpdateStruct = $contentService->newContentMetadataUpdateStruct();
$contentMetadataUpdateStruct->ownerId = $user->id;
$contentService->updateContentMetadata( $user->getVersionInfo()->getContentInfo(), $contentMetadataUpdateStruct );
```
