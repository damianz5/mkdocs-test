#  eZ Platform 15.03 Release notes

## eZ Platform "Alpha2" available for testing

##### 13th May 2015

![Preview of Platform UI Alpha2 during editing an image](attachments/31429950/31429945.png "Preview of Platform UI during editing an image")

#### Quick links

-   [Install](https://github.com/ezsystems/ezplatform/blob/master/INSTALL.md)
-   [Requirements](https://doc.ez.no/display/TMPA/Requirements+5.4) *(currently same as eZ Publish Platform 5.4)*
-   Upgrading: *As this is a alpha release, there is no upgrade instructions yet, this is planned for Beta during the Summer.*

-   Download: See [share.ez.no/downloads](http://share.ez.no/downloads/downloads/ez-platform-15.03-alpha), or see *Install* for how to install via composer.

The second alpha release of eZ Platform,15.03, builds upon the [15.01](eZ-Platform-15.01-Release-notes_31429941.html) March release adding additional support for editing- and browsing-capabilities. It also contains several underlying improvements and fixes developed for [5.3.5](https://doc.ez.no/display/TMPA/5.3.5+Release+Notes) and [5.4.2](https://doc.ez.no/display/TMPA/5.4.2+Release+Notes), that has also been released recently.

*Next release is planned to be released beginning of June, and will preview several additional features currently not exposed yet.*

## Highlights

Besides lots of smaller improvements and fixes found bellow, and mentioned above for the 5.x sub release, the main visual changes are: 

### Platform UI Bundle with Universal Discovery Widget

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="attachments/31429950/31429943.png" class="confluence-embedded-image confluence-thumbnail" width="300" /></span></td>
<td><p>One important feature in eZ Publish, and also now eZ Platform, is being able to browse for content you want to select. In eZ Platform we call this Universal Discovery Widget, and in this release you can see more or less the completion of first part of this with possibility to select by browsing the tree (location structure): <span class="jira-issue resolved"> <a href="https://jira.ez.no/browse/EZP-23893?src=confmacro" class="jira-issue-key"><img src="https://jira.ez.no/images/icons/issuetypes/epic.png" class="icon" />EZP-23893</a> - <span class="summary">UDW : Basic tree</span> <span class="aui-lozenge aui-lozenge-subtle aui-lozenge-success jira-macro-single-issue-export-pdf">Closed</span> </span></p>
<p>This is used for Relation, Relation List and Section assignment selection so far, and before July release we hope to complete this part with inclusion of <span class="jira-issue"> <a href="https://jira.ez.no/browse/EZP-24067?src=confmacro" class="jira-issue-key"><img src="https://jira.ez.no/images/icons/issuetypes/epic.png" class="icon" />EZP-24067</a> - <span class="summary">Sub items widget</span> <span class="aui-lozenge aui-lozenge-subtle aui-lozenge-current jira-macro-single-issue-export-pdf">QA</span> </span></p>
<p>Future tentatively planned ways to browse for content includes:</p>
<p></p>
<div id="refresh-module-539459587">
<p></p>
<div id="jira-issues-539459587" style="width: 100%;  overflow: auto;">
<table>
<tbody>
<tr class="odd">
<td><span class="jim-table-header-content">Summary</span></td>
<td><span class="jim-table-header-content">Updated</span></td>
<td><span class="jim-table-header-content">P</span></td>
<td><span class="jim-table-header-content">Status</span></td>
</tr>
<tr class="even">
<td><a href="https://jira.ez.no/browse/EZP-24284?src=confmacro">UDW - Search</a></td>
<td>Jun 30, 2016</td>
<td><img src="https://jira.ez.no/images/icons/priorities/critical.png" alt="Critical" class="icon" /></td>
<td><span class="aui-lozenge aui-lozenge-subtle aui-lozenge-complete"> Open </span></td>
</tr>
<tr class="odd">
<td><a href="https://jira.ez.no/browse/EZP-24285?src=confmacro">UDW - recent content</a></td>
<td>Jun 30, 2016</td>
<td><img src="https://jira.ez.no/images/icons/priorities/major.png" alt="High" class="icon" /></td>
<td><span class="aui-lozenge aui-lozenge-subtle aui-lozenge-complete"> Open </span></td>
</tr>
<tr class="even">
<td><a href="https://jira.ez.no/browse/EZP-24286?src=confmacro">UDW : Bookmark</a></td>
<td>Jun 30, 2016</td>
<td><img src="https://jira.ez.no/images/icons/priorities/minor.png" alt="Medium" class="icon" /></td>
<td><span class="aui-lozenge aui-lozenge-subtle aui-lozenge-complete"> Open </span></td>
</tr>
<tr class="odd">
<td><a href="https://jira.ez.no/browse/EZP-24287?src=confmacro">UDW : ID</a></td>
<td>Jun 30, 2016</td>
<td><img src="https://jira.ez.no/images/icons/priorities/trivial.png" alt="Low" class="icon" /></td>
<td><span class="aui-lozenge aui-lozenge-subtle aui-lozenge-complete"> Open </span></td>
</tr>
</tbody>
</table>
</div>
<div class="refresh-issues-bottom">
<span id="total-issues-count-539459587"> <a href="https://jira.ez.no/secure/IssueNavigator.jspa?reset=true&amp;jqlQuery=key+in+%28EZP-24284%2C+EZP-24285%2C+EZP-24286%2C+EZP-24287%29++order+by+priority+&amp;src=confmacro" title="View all matching issues in JIRA.">4 issues</a> </span>
</div>
</div></td>
</tr>
</tbody>
</table>

### Demo Bundle with privacy cookie banner

|                                        |                                                                                                                                                                                                                                                                                     |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ![](attachments/31429950/31429944.png) | Available in this release is a new [PrivacyCookieBundle](https://github.com/ezsystems/EzSystemsPrivacyCookieBundle), providing easy access to setup warning and remembering user input for Privacy banners needed to comply with EU directive commonly referred to as "Cookie law". |

### Other notable changes

-    [![](https://jira.ez.no/images/icons/issuetypes/improvement.png)EZP-24015](https://jira.ez.no/browse/EZP-24015?src=confmacro) - Improve Language Switcher flags and logic Closed
-    [![](https://jira.ez.no/images/icons/issuetypes/story.png)EZP-23730](https://jira.ez.no/browse/EZP-23730?src=confmacro) - As an editor, I want to see the content of the media fields Closed
-    [![](https://jira.ez.no/images/icons/issuetypes/story.png)EZP-23816](https://jira.ez.no/browse/EZP-23816?src=confmacro) - As an editor, I want to be able to fill the Relation field Closed
-    [![](https://jira.ez.no/images/icons/issuetypes/improvement.png)EZP-24213](https://jira.ez.no/browse/EZP-24213?src=confmacro) - FullText stopWordThreshold should be percentage of content count Closed

 

## Changelog

*Changes* (Stories, Improvements and bug fixes) can be found in our issue tracker:  [47 issues](https://jira.ez.no/secure/IssueNavigator.jspa?reset=true&jqlQuery=fixVersion%3D%222015.03%22+AND+project+%3D+EZP+AND+issuetype+in+%28Story%2C+Improvement%2C+Bug%29+order+by+issuetype++&src=confmacro)  *(some are still pending additional documentation changes)*

### Known issues & upcoming features

-   List of issues specifically affecting this release:  [19 issues](https://jira.ez.no/secure/IssueNavigator.jspa?reset=true&jqlQuery=project+%3D+EZP+AND+issuetype+in+%28bug%29+AND+affectedVersion+%3D+2015.03+ORDER+BY+priority+++&src=confmacro)
-   General "Known issues" in *Platform stack* compared to* Legacy*:  [8 issues](https://jira.ez.no/secure/IssueNavigator.jspa?reset=true&jqlQuery=project+%3D+EZP+AND+affectedVersion+%3D%22Known+Issues+5.x+Stack%22+AND+resolution+%3D+Unresolved+ORDER+BY+priority+&src=confmacro)
-   Epics tentatively\* planned for first stable release:  [7 issues](https://jira.ez.no/secure/IssueNavigator.jspa?reset=true&jqlQuery=project+%3D+EZP+AND+issuetype+%3D+Epic+AND+fixVersion%3DPollux+AND+resolution+%3D+Unresolved+ORDER+BY+priority+&src=confmacro)
-   Epics tentatively\* planned for first LTS release:  [0 issue](https://jira.ez.no/secure/IssueNavigator.jspa?reset=true&jqlQuery=project+%3D+EZP+AND+issuetype+%3D+Epic+AND+fixVersion%3D%22Mauna+Kea%22+AND+resolution+%3D+Unresolved+ORDER+BY+priority++&src=confmacro)

*'\* Some of these features will not be in the stable releases, the once we first and foremost will aim for having in the release are those mentioned on the [Roadmap](http://ez.no/Blog/What-to-Expect-from-eZ-Studio-and-eZ-Platform).*

## Attachments:

![](images/icons/bullet_blue.gif) [Screen Shot 2015-05-12 at 19.16.38 .png](attachments/31429950/31429943.png) (image/png)
![](images/icons/bullet_blue.gif) [PrivacyCookieBundle.png](attachments/31429950/31429944.png) (image/png)
![](images/icons/bullet_blue.gif) [Screen Shot 2015-05-12 at 11.46.48 .png](attachments/31429950/31429945.png) (image/png)
![](images/icons/bullet_blue.gif) [iStock\_000032478246XLarge - banner doc.jpg](attachments/31429950/31429946.jpg) (image/jpeg)
![](images/icons/bullet_blue.gif) [Ventoux-Square.jpg](attachments/31429950/31429947.jpg) (image/jpeg)
![](images/icons/bullet_blue.gif) [Getting-Started-with-eZ-Publish-Platform.jpg](attachments/31429950/31429948.jpg) (image/jpeg)
![](images/icons/bullet_blue.gif) [Platform screenshoot alpha1.gif](attachments/31429950/31429949.gif) (image/gif)
