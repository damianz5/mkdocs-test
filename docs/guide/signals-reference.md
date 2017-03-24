#  Signals Reference

This page references **all available signals** that you can listen to, triggered by ("Public") Repository API in eZ Platform.

For more information, check the [SignalSlot ](#SignalsReference-Signalslots)section and the [Listening to Core events](Listening-to-Core-events_31429796.html) recipe.

All signals are relative to `eZ\Publish\Core\SignalSlot\Signal` namespace.

Transactions

Signals are sent after transactions are executed, making signals transaction safe.

 

### ContentService

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Signal type</th>
<th>Properties</th>
<th>Triggered by</th>
<th>When</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>ContentService\AddRelationSignal</code></td>
<td><ul>
<li><code>srcContentId</code> (source contentId, aka referrer)</li>
<li><code>srcVersionNo</code></li>
<li><code>dstContentId</code> (destination contentId, aka target)</li>
</ul></td>
<td><p><code>ContentService::addRelation()</code></p></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>ContentService\AddTranslationInfoSignal</code></td>
<td>N/A</td>
<td><code>ContentService::addTranslationInfo()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>ContentService\CopyContentSignal</code></td>
<td><ul>
<li><code>srcContentId</code> (original content ID)</li>
<li><code>srcVersionNo</code></li>
<li><code>dstContentId</code> (contentId of the copy)</li>
<li><code>dstVersionNo</code></li>
<li><code>dstParentLocationId</code> (locationId where the content has been copied)</li>
</ul></td>
<td><code>ContentService::copyContent()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>ContentService\CreateContentDraftSignal</code></td>
<td><ul>
<li><code>contentId</code></li>
<li><code>versionNo</code></li>
<li><code>userId</code> (Id of user used to create the draft, or null - current user)</li>
</ul></td>
<td><code>ContentService::createContentDraft()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>ContentService\CreateContentSignal</code></td>
<td><ul>
<li><code>contentId</code></li>
<li><code>versionNo</code></li>
</ul></td>
<td><code>ContentService::createContent()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>ContentService\DeleteContentSignal</code></td>
<td><ul>
<li><code>contentId</code></li>
</ul></td>
<td><code>ContentService::deleteContent()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>ContentService\DeleteRelationSignal</code></td>
<td><ul>
<li><code>srcContentId</code></li>
<li><code>srcVersionNo</code></li>
<li><code>dstContentId</code></li>
</ul></td>
<td><code>ContentService::deleteRelation()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>ContentService\DeleteVersionSignal</code></td>
<td><ul>
<li><code>contentId</code></li>
<li><code>versionNo</code></li>
</ul></td>
<td><code>ContentService::deleteVersion()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>ContentService\PublishVersionSignal</code></td>
<td><ul>
<li><code>contentId</code></li>
<li><code>versionNo</code></li>
</ul></td>
<td><code>ContentService:: publishVersion()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>ContentService\TranslateVersionSignal</code></td>
<td><ul>
<li><code>contentId</code></li>
<li><code>versionNo</code></li>
<li><code>userId</code></li>
</ul></td>
<td><code>ContentService::translationVersion()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>ContentService\UpdateContentMetadataSignal</code></td>
<td><ul>
<li><code>contentId</code></li>
</ul></td>
<td><code>ContentService::updateContentMetadata()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>ContentService\UpdateContentSignal</code></td>
<td><ul>
<li><code>contentId</code></li>
<li><code>versionNo</code></li>
</ul></td>
<td><code>ContentService::updateContent()</code></td>
<td>After</td>
</tr>
</tbody>
</table>

### ContentTypeService

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Signal type</th>
<th>Properties</th>
<th>Triggered by</th>
<th>When</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>ContentTypeService\AddFieldDefinitionSignal</code></td>
<td><ul>
<li><span>contentTypeDraftId</span></li>
</ul></td>
<td><p><code>ContentTypeService::addFieldDefinition()</code></p></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>ContentTypeService\AssignContentTypeGroupSignal</code></td>
<td><ul>
<li><code>contentTypeId</code></li>
<li><code>contentTypeGroupId</code></li>
</ul></td>
<td><code>ContentTypeService::assignContentTypeGroup()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>ContentTypeService\CopyContentTypeSignal</code></td>
<td><ul>
<li><code>contentTypeId</code></li>
<li><code>userId</code></li>
</ul></td>
<td><code>ContentTypeService::copyContentType()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>ContentTypeService\CreateContentTypeDraftSignal</code></td>
<td><ul>
<li><code>contentTypeId</code></li>
</ul></td>
<td><code>ContentTypeService::createContentTypeDraft()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>ContentTypeService\CreateContentTypeGroupSignal</code></td>
<td><ul>
<li><code>groupId</code></li>
</ul></td>
<td><code>ContentTypeService::createContentTypeGroup()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>ContentTypeService\CreateContentTypeSignal</code></td>
<td><ul>
<li><code>contentTypeId</code></li>
</ul></td>
<td><code>ContentTypeService::createContentType()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>ContentTypeService\DeleteContentTypeGroupSignal</code></td>
<td><ul>
<li><code>contentTypeGroupId</code></li>
</ul></td>
<td><code>ContentTypeService::deleteContentTypeGroup()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>ContentTypeService\DeleteContentTypeSignal</code></td>
<td><ul>
<li><code>contentTypeId</code></li>
</ul></td>
<td><code>ContentTypeService::deleteContentType()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>ContentTypeService\PublishContentTypeDraftSignal</code></td>
<td><ul>
<li><code>contentTypeDraftId</code></li>
</ul></td>
<td><code>ContentTypeService::publishContentTypeDraft()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>ContentTypeService\RemoveFieldDefinitionSignal</code></td>
<td><ul>
<li><code>contentTypeDraftId</code></li>
<li><code>fieldDefinitionId</code></li>
</ul></td>
<td><code>ContentTypeService::removeFieldDefinition()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>ContentTypeService\UnassignContentTypeGroupSignal</code></td>
<td><ul>
<li><code>contentTypeId</code></li>
<li><code>contentTypeGroupId</code></li>
</ul></td>
<td><code>ContentTypeService::unassignContentTypeGroup()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>ContentTypeService\UpdateContentTypeDraftSignal</code></td>
<td><ul>
<li><code>contentTypeDraftId</code></li>
</ul></td>
<td><code>ContentTypeService::updateContentTypeDraft()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>ContentTypeService\UpdateContentTypeGroupSignal</code></td>
<td><ul>
<li><code>contentTypeGroupId</code></li>
</ul></td>
<td><code>ContentTypeService::updateContentTypeGroup()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>ContentTypeService\UpdateFieldDefinitionSignal</code></td>
<td><ul>
<li><code>contentTypeDraftId</code></li>
<li><code>fieldDefinitionId</code></li>
</ul></td>
<td><code>ContentTypeService::updateFieldDefinition()</code></td>
<td>After</td>
</tr>
</tbody>
</table>

### LanguageService

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Signal type</th>
<th>Properties</th>
<th>Triggered by</th>
<th>When</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>LanguageService\CreateLanguageSignal</code></td>
<td><ul>
<li><code>languageId</code></li>
</ul></td>
<td><code>LanguageService::createLanguage()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>LanguageService\DeleteLanguageSignal</code></td>
<td><ul>
<li><code>languageId</code></li>
</ul></td>
<td><code>LanguageService::deleteLanguage()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>LanguageService\DisableLanguageSignal</code></td>
<td><ul>
<li><code>languageId</code></li>
</ul></td>
<td><code>LanguageService::disableLanguage()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>LanguageService\EnableLanguageSignal</code></td>
<td><ul>
<li><code>languageId</code></li>
</ul></td>
<td><code>LanguageService::enableLanguage()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>LanguageService\UpdateLanguageNameSignal</code></td>
<td><ul>
<li><code>languageId</code></li>
<li><code>newName</code></li>
</ul></td>
<td><code>LanguageService::updateLanguageName()</code></td>
<td><p>After</p></td>
</tr>
</tbody>
</table>

### LocationService

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Signal type</th>
<th>Properties</th>
<th>Triggered by</th>
<th>When</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>LocationService\CopySubtreeSignal</code></td>
<td><ul>
<li><code>subtreeId</code> (top locationId of the subtree to be copied)</li>
<li><code>targetParentLocationId</code></li>
</ul></td>
<td><p><code>LocationService::copySubtree()</code></p></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>LocationService\CreateLocationSignal</code></td>
<td><ul>
<li><code>contentId</code></li>
<li><code>locationId</code></li>
</ul></td>
<td><code>LocationService::createLocation()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>LocationService\DeleteLocationSignal</code></td>
<td><ul>
<li><code>contentId</code></li>
<li><code>locationId</code></li>
</ul></td>
<td><code>LocationService::deleteLocation()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>LocationService\HideLocationSignal</code></td>
<td><ul>
<li><code>contentId</code></li>
<li><code>locationId</code></li>
</ul></td>
<td><code>LocationService::hideLocation()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>LocationService\UnhideLocationSignal</code></td>
<td><ul>
<li><code>contentId</code></li>
<li><code>locationId</code></li>
</ul></td>
<td><code>LocationService::unhideLocation()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>LocationService\MoveSubtreeSignal</code></td>
<td><ul>
<li><code>subtreeId</code></li>
<li><code>newParentLocationId</code></li>
</ul></td>
<td><code>LocationService::moveSubtree()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>LocationService\SwapLocationSignal</code></td>
<td><ul>
<li><code>content1Id</code></li>
<li><code>location1Id</code></li>
<li><code>content2Id</code></li>
<li><code>location2Id</code><code></code></li>
</ul></td>
<td><code>LocationService::swapLocation()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>LocationService\UpdateLocationSignal</code></td>
<td><ul>
<li><code>contentId</code></li>
<li><code>locationId</code></li>
</ul></td>
<td><code>LocationService::updateLocation()</code></td>
<td>After</td>
</tr>
</tbody>
</table>

### ObjectStateService

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Signal type</th>
<th>Properties</th>
<th>Triggered by</th>
<th>When</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>ObjectStateService\CreateObjectStateGroupSignal</code></td>
<td><ul>
<li><code>objectStateGroupId</code></li>
</ul></td>
<td><code>ObjectStateService::createObjectStateGroup()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>ObjectStateService\CreateObjectStateSignal</code></td>
<td><ul>
<li><code>objectStateGroupId</code></li>
<li><code>objectStateId</code></li>
</ul></td>
<td><code>ObjectStateService::createObjectState()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>ObjectStateService\DeleteObjectStateGroupSignal</code></td>
<td><ul>
<li><code>objectStateGroupId</code></li>
</ul></td>
<td><code>ObjectStateService::deleteObjectStateGroup()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>ObjectStateService\DeleteObjectStateSignal</code></td>
<td><ul>
<li><code>objectStateId</code></li>
</ul></td>
<td><code>ObjectStateService::deleteObjectState()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>ObjectStateService\SetContentStateSignal</code></td>
<td><ul>
<li><code>contentId</code></li>
<li><code>objectStateGroupId</code></li>
<li><code>objectStateId</code></li>
</ul></td>
<td><code>ObjectStateService::setContentState()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>ObjectStateService\SetPriorityOfObjectStateSignal</code></td>
<td><ul>
<li><code>objectStateId</code></li>
<li><code>priority</code></li>
</ul></td>
<td><code>ObjectStateService::setPriorityOfObjectState()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>ObjectStateService\UpdateObjectStateGroupSignal</code></td>
<td><ul>
<li><code>objectStateGroupId</code></li>
</ul></td>
<td><code>ObjectStateService::updateObjectStateGroup()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>ObjectStateService\UpdateObjectStateSignal</code></td>
<td><ul>
<li><code>objectStateId</code></li>
</ul></td>
<td><code>ObjectStateService::updateObjectState()</code></td>
<td>After</td>
</tr>
</tbody>
</table>

### RoleService

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Signal type</th>
<th>Properties</th>
<th>Triggered by</th>
<th>When</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>RoleService\AddPolicySignal</code></td>
<td><ul>
<li><code>roleId</code></li>
<li><code>policyId</code></li>
</ul></td>
<td><code>RoleService::addPolicy()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>RoleService\AssignRoleToUserGroupSignal</code></td>
<td><ul>
<li><code>roleId</code></li>
<li><code>userGroupId</code></li>
<li><code>roleLimitation</code></li>
</ul></td>
<td><code>RoleService::assignRoleToUserGroup()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>RoleService\AssignRoleToUserSignal</code></td>
<td><ul>
<li><code>roleId</code></li>
<li><code>userId</code></li>
<li><code>roleLimitation</code></li>
</ul></td>
<td><code>RoleService::assignRoleToUser()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>RoleService\CreateRoleSignal</code></td>
<td><ul>
<li><code>roleId</code></li>
</ul></td>
<td><code>RoleService::createRole()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>RoleService\DeleteRoleSignal</code></td>
<td><ul>
<li><code>roleId</code></li>
</ul></td>
<td><code>RoleService::deleteRole()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>RoleService\RemovePolicySignal</code></td>
<td><ul>
<li><code>roleId</code></li>
<li><code>policyId</code></li>
</ul></td>
<td><code>RoleService::removePolicy()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>RoleService\UnassignRoleFromUserGroupSignal</code></td>
<td><ul>
<li><code>roleId</code></li>
<li><code>userGroupId</code></li>
</ul></td>
<td><code>RoleService::unassignRoleFromUserGroup()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>RoleService\UnassignRoleFromUserSignal</code></td>
<td><ul>
<li><code>roleId</code></li>
<li><code>userId</code></li>
</ul></td>
<td><code>RoleService::unassignRoleFromUser()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>RoleService\UpdatePolicySignal</code></td>
<td><ul>
<li><code>policyId</code></li>
</ul></td>
<td><code>RoleService::updatePolicy()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>RoleService\UpdateRoleSignal</code></td>
<td><ul>
<li><code>roleId</code></li>
</ul></td>
<td><code>RoleService::updateRole()</code></td>
<td>After</td>
</tr>
</tbody>
</table>

### SectionService

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Signal type</th>
<th>Properties</th>
<th>Triggered by</th>
<th>When</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>SectionService\AssignSectionSignal</code></td>
<td><ul>
<li><code>contentId</code></li>
<li><code>sectionId</code></li>
</ul></td>
<td><code>SectionService::assignSection()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>SectionService\CreateSectionSignal</code></td>
<td><ul>
<li><code>sectionId</code></li>
</ul></td>
<td><code>SectionService::createSection()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>SectionService\DeleteSectionSignal</code></td>
<td><ul>
<li><code>sectionId</code></li>
</ul></td>
<td><code>SectionService::deleteSection()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>SectionService\UpdateSectionSignal</code></td>
<td><ul>
<li><code>sectionId</code></li>
</ul></td>
<td><code>SectionService::updateSection()</code></td>
<td>After</td>
</tr>
</tbody>
</table>

### TrashService

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Signal type</th>
<th>Properties</th>
<th>Triggered by</th>
<th>When</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>TrashService\DeleteTrashItemSignal</code></td>
<td><ul>
<li><code>trashItemId</code></li>
</ul></td>
<td><code>TrashService::deleteTrashItem()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>TrashService\EmptyTrashSignal</code></td>
<td>N/A</td>
<td><code>TrashService::emptyTrash()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>TrashService\RecoverSignal</code></td>
<td><ul>
<li><code>trashItemId</code></li>
<li><code>newParentLocationId</code></li>
<li><code>newLocationId</code></li>
</ul></td>
<td><code>TrashService::recover()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>TrashService\TrashSignal</code></td>
<td><ul>
<li><code>locationId</code></li>
</ul></td>
<td><code>TrashService::trash()</code></td>
<td>After</td>
</tr>
</tbody>
</table>

### URLAliasService

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Signal type</th>
<th>Properties</th>
<th>Triggered by</th>
<th>When</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>URLAliasService\CreateGlobalUrlAliasSignal</code></td>
<td><ul>
<li><code>urlAliasId</code></li>
</ul></td>
<td><code>URLAliasService::createGlobalUrlAlias()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>URLAliasService\CreateUrlAliasSignal</code></td>
<td><ul>
<li><code>urlAliasId</code></li>
</ul></td>
<td><code>URLAliasService::createUrlAlias()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>URLAliasService\RemoveAliasesSignal</code></td>
<td><ul>
<li><code>aliasList</code></li>
</ul></td>
<td><code>URLAliasService::removeAliases()</code></td>
<td>After</td>
</tr>
</tbody>
</table>

### URLWildcardService

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Signal type</th>
<th>Properties</th>
<th>Triggered by</th>
<th>When</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>URLWildcardService\CreateSignal</code></td>
<td><ul>
<li><code>urlWildcardId</code></li>
</ul></td>
<td><code>URLWildcardService::create()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>URLWildcardService\RemoveSignal</code></td>
<td><ul>
<li><code>urlWildcardId</code></li>
</ul></td>
<td><code>URLWildcardService::remove()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>URLWildcardService\TranslateSignal</code></td>
<td><ul>
<li><code>url</code></li>
</ul></td>
<td><code>URLWildcardService::translate()</code></td>
<td>After</td>
</tr>
</tbody>
</table>

### UserService

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Signal type</th>
<th>Properties</th>
<th>Triggered by</th>
<th>When</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><code>UserService\AssignUserToUserGroupSignal</code></td>
<td><ul>
<li><code>userId</code></li>
<li><code>userGroupId</code></li>
</ul></td>
<td><code>UserService::assignUserToUserGroup()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>UserService\CreateUserGroupSignal</code></td>
<td><ul>
<li><code>userGroupId</code></li>
</ul></td>
<td><code>UserService::createUserGroup()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>UserService\CreateUserSignal</code></td>
<td><ul>
<li><code>userId</code></li>
</ul></td>
<td><code>UserService::createUser()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>UserService\DeleteUserGroupSignal</code></td>
<td><ul>
<li><code>userGroupId</code></li>
</ul></td>
<td><code>UserService::deleteUserGroup()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>UserService\DeleteUserSignal</code></td>
<td><ul>
<li><code>userId</code></li>
</ul></td>
<td><code>UserService::deleteUser()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>UserService\MoveUserGroupSignal</code></td>
<td><ul>
<li><code>userGroupId</code></li>
<li><code>newParentId</code></li>
</ul></td>
<td><code>UserService::moveUserGroup()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>UserService\UnAssignUserFromUserGroupSignal</code></td>
<td><ul>
<li><code>userId</code></li>
<li><code>userGroupId</code></li>
</ul></td>
<td><code>UserService::unAssignUserFromUserGroup()</code></td>
<td>After</td>
</tr>
<tr class="even">
<td><code>UserService\UpdateUserGroupSignal</code></td>
<td><ul>
<li><code>userGroupId</code></li>
</ul></td>
<td><code>UserService::updateUserGroup()</code></td>
<td>After</td>
</tr>
<tr class="odd">
<td><code>UserService\UpdateUserSignal</code></td>
<td><ul>
<li><code>userId</code></li>
</ul></td>
<td><code>UserService::updateUser()</code></td>
<td>After</td>
</tr>
</tbody>
</table>
