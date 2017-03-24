#  User Field Type

This Field Type validates and stores information about a user.

| Name   | Internal name | Expected input |
|--------|---------------|----------------|
| `User` | `ezuser`      | ignored        |

## PHP API Field Type

### Value Object

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
<td><p><code>hasStoredLogin</code></p></td>
<td><code>boolean</code></td>
<td>Denotes if user has stored login.</td>
<td><code>true</code></td>
</tr>
<tr class="even">
<td><p><code>contentId</code></p></td>
<td><code>int|string</code></td>
<td>Id of the Content corresponding to the user.</td>
<td><code>42</code></td>
</tr>
<tr class="odd">
<td><p><code>login</code></p></td>
<td><code>string</code></td>
<td>Username.</td>
<td><code>john</code></td>
</tr>
<tr class="even">
<td><p><code>email</code></p></td>
<td><code>string</code></td>
<td>Users' email address.</td>
<td><code>john@smith.com</code></td>
</tr>
<tr class="odd">
<td><p><code>passwordHash</code></p></td>
<td><code>string</code></td>
<td>Hash of the user's password.</td>
<td><code>1234567890abcdef</code></td>
</tr>
<tr class="even">
<td><p><code>passwordHashType</code></p></td>
<td><code>mixed</code></td>
<td>Algorithm user for generating password hash as a <code>PASSWORD_HASH_* </code>constant defined in <span><code>eZ\Publish\Core\Repository\Values\User\User</code> class</span>.</td>
<td><pre><code>User::PASSWORD_HASH_MD5_USER</code></pre></td>
</tr>
<tr class="odd">
<td><p><code>maxLogin</code></p></td>
<td><code>int</code></td>
<td>Maximal number of concurrent logins.</td>
<td><code>1000</code></td>
</tr>
</tbody>
</table>

##### Available password hash types

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Constant</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><code>eZ\Publish\Core\Repository\Values\User\User::PASSWORD_HASH_MD5_PASSWORD</code></p></td>
<td>MD5 hash of the password, not recommended.</td>
</tr>
<tr class="even">
<td><p><code>eZ\Publish\Core\Repository\Values\User\User::PASSWORD_HASH_MD5_USER</code></p></td>
<td><span>MD5 hash of the password and username.</span></td>
</tr>
<tr class="odd">
<td><p><code>eZ\Publish\Core\Repository\Values\User\User::PASSWORD_HASH_MD5_SITE</code></p></td>
<td><span>MD5 hash of the password, username and site name.</span></td>
</tr>
<tr class="even">
<td><p><code>eZ\Publish\Core\Repository\Values\User\User::PASSWORD_HASH_PLAINTEXT</code></p></td>
<td><p>Passwords are stored in plaintext, should not be used for real sites.</p></td>
</tr>
</tbody>
</table>

 
