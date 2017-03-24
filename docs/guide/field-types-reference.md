#  Field Types reference

This page contains a reference of Field Types used in eZ Platform.

For the general Field Type documentation see [Field Type API and best practices](Field-Type-API-and-best-practices_31430767.html).

If you are looking for the documentation on how to implement a custom Field Type, see the [Creating a Tweet Field Type](Creating-a-Tweet-Field-Type_31429766.html) tutorial.

A Field Type is the smallest possible entity of storage. It determines how a specific type of information should be validated, stored, retrieved, formatted and so on. eZ Platform comes with a collection of fundamental types that can be used to build powerful and complex content structures. In addition, it is possible to extend the system by creating custom Field Types for special needs. Custom Field Types have to be programmed in PHP. However, the built-in Field Types are usually sufficient enough for typical scenarios. The following table gives an overview of the supported Field Types that come with eZ Platform.

### Built in Field Types

| FieldType                                              | Description                                                                         | Searchable in Legacy Storage engine               |
|--------------------------------------------------------|-------------------------------------------------------------------------------------|---------------------------------------------------|
| [Author](Author-Field-Type_31430499.html)              | Stores a list of authors, each consisting of author name and author email.          | No                                                |
| [BinaryFile](BinaryField-Field-Type_31430501.html)     | Stores a file.                                                                      | Yes                                               |
| [Checkbox](Checkbox-Field-Type_31430497.html)          | Stores a boolean value.                                                             | Yes                                               |
| [Country](Country-Field-Type_31430503.html)            | Stores country names as a string.                                                   | Yes                                               |
|  [DateAndTime](DateAndTime-Field-Type_31430505.html)   | Stores a full date including time information.                                      | Yes                                               |
|  [Date](Date-Field-Type_31430507.html)                 | Stores date information.                                                            | Yes                                               |
|  [EmailAddress](EmailAddress-Field-Type_31430509.html) | Validates and stores an email address.                                              | Yes                                               |
|  [Float](Float-Field-Type_31430511.html)               | Validates and stores a decimal value.                                               | No                                                |
|  [Image](Image-Field-Type_31430513.html)               | Validates and stores an image.                                                      | No                                                |
|  [Integer](Integer-Field-Type_31430515.html)           | Validates and stores an integer value.                                              | Yes                                               |
|  [ISBN](ISBN-Field-Type_31430517.html)                 | Handles International Standard Book Number (ISBN) in 10-digit or 13-digit format.   | Yes                                               |
|  [Keyword](Keyword-Field-Type_31430519.html)           | Stores keywords.                                                                    | No                                                |
| [Landing Page](31430521.html)                          | Stores a page with a layout consisting of multiple zones.                           | No                                                |
|  [MapLocation](MapLocation-Field-Type_31430523.html)   | Stores map coordinates.                                                             | Yes, with MapLocationDistance criterion           |
|  [Media](Media-Field-Type_31430525.html)               | Validates and stores a media file.                                                  | No                                                |
|  [Null](Null-Field-Type_31430527.html)                 | Used as fallback for missing Field Types and for testing purposes.                  | No                                                |
|  [Rating](Rating-Field-Type_31430531.html)             | Stores a rating.                                                                    | No                                                |
|  [Relation](Relation-Field-Type_31430533.html)         | Validates and stores a relation to a Content item.                                  | Yes, with both Field and FieldRelation criterions |
|  [RelationList](RelationList-Field-Type_31430535.html) | Validates and stores a list of relations to Content items.                          | Yes, with FieldRelation criterion                 |
| [RichText](RichText-Field-Type_31430537.html)          | Validates and stores structured rich text, and exposes it in several formats.       | Yes                                               |
|  [Selection](Selection-Field-Type_31430539.html)       | Validates and stores a single selection or multiple choices from a list of options. | Yes                                               |
|  [TextBlock](TextBlock-Field-Type_31430541.html)       | Validates and stores a larger block of text.                                        | No                                                |
|  [TextLine](TextLine-Field-Type_31430545.html)         | Validates and stores a single line of text.                                         | Yes                                               |
|  [Time](Time-Field-Type_31430543.html)                 | Stores time information.                                                            | Yes                                               |
|  [Url](Url-Field-Type_31430547.html)                   | Stores a URL / address.                                                             | No                                                |
|  [User](User-Field-Type_31430549.html)                 | Validates and stores information about a user.                                      | No                                                |
|  [XmlText](XmlText-Field-Type_31430551.html)           | Validates and stores multiple lines of formatted text.                              | Yes                                               |

### Field Types provided by Community

| FieldType                                                        | Description                                    | Searchable | Editing support in UI                                                                                                | Planned to be incl in the future |
|------------------------------------------------------------------|------------------------------------------------|------------|----------------------------------------------------------------------------------------------------------------------|----------------------------------|
| [Tags](https://github.com/netgen/TagsBundle)                     | Tags field and full fledge taxonomy management | Yes        | No *(See [crowdfunding](http://www.netgenlabs.com/Blog/Crowdfunding-Tags-Bundle-support-for-eZ-Platform-UI)* *page)* | Yes                              |
| [Price](https://github.com/ezcommunity/EzPriceBundle)            | Price field for product catalog use            | Yes        | No                                                                                                                   | Yes                              |
| [Matrix](https://github.com/ezcommunity/EzMatrixFieldTypeBundle) | Matrix field for matrix data                   | Yes        | No                                                                                                                   | Yes                              |

### Known missing Field Types

The following Field Types are configured using [Null Field Type](Null-Field-Type_31430527.html) to avoid exceptions if they exists in your database, but their functionality is currently not known to be implemented out of the box or by the community:

 [![](https://jira.ez.no/images/icons/issuetypes/story.png)EZP-20112](https://jira.ez.no/browse/EZP-20112?src=confmacro) - Some Shop FieldTypes are not supported by Public API Backlog

 [![](https://jira.ez.no/images/icons/issuetypes/story.png)EZP-20115](https://jira.ez.no/browse/EZP-20115?src=confmacro) - eZ Identifier FieldType not supported by Public API Backlog

 [![](https://jira.ez.no/images/icons/issuetypes/story.png)EZP-20118](https://jira.ez.no/browse/EZP-20118?src=confmacro) - eZ Password Expiry FieldType not supported by Public API Backlog

*Missing something? For field types provided by community, like for instance `ezselection2`, unless otherwise mentioned it can be considered missing for the time being. If something should be listed here, add a comment.* 

### Generate new Field Type

Besides links in the top of this topic in regards to creating own field type, from partner Smile there is now a [Field Type Generator Bundle](https://github.com/Smile-SA/EzFieldTypeGeneratorBundle) helping you get started creating skeleton for eZ Platform field type, including templates for editorial interface. 

 

#### Related topics:

-   [Content items, Content Types and Fields](31430275.html)

#### In this topic:

-   [Built in Field Types](#FieldTypesreference-BuiltinFieldTypes)
-   [Field Types provided by Community](#FieldTypesreference-FieldTypesprovidedbyCommunity)
-   [Known missing Field Types](#FieldTypesreference-KnownmissingFieldTypes)
-   [Generate new Field Type](#FieldTypesreference-GeneratenewFieldType)
