# So you want to open some data?

An attempt at an opinionated recommendation for how to release your data openly for those starting from scratch.  This is meant to describe what formats and methods are most helpful for open data, specifically in terms of how it can be used by computers (i.e. in applications and by technical people).  This assumes that open data is not necessarily meant for the general public.

This is meant for governments, government agencies, government departments, non-profits, and private companies, and any person that wants to make the data they collect more open and accessible.

There is much more to opening up data then what is in this document.

## Data Formats

### General principles

General principles to follow.  The following parts are what should go into policy.

#### Open formats

An open format is a data format that usually has a published specification, or is otherwise commonly understood.

#### Non-proprietary

Non-properietary means that no one person or organization has sole ownership of the data format, or that the specification is not openly available to the public, or the data cannot be manipulated without a specific application.

#### Common or "industry standard"

Data formats should be used by more than just you or your organization.  Creating a new data format to release your is not usually a good idea unless you are working with other entities that have similar data.

### General formats

The following are specific formats that can be used in general for data, but may not be the best for a specific dataset.

#### JSON ([Javascript Object Notation](http://en.wikipedia.org/wiki/JSON))

JSON is readable and writeable by almost all the major programming languages, usually without any external libraries.  It allows for hierarchical structure as well as having the most common datatypes.

#### CSV ([Comma Separated Values](http://en.wikipedia.org/wiki/Comma-separated_values))

Though there is a standard for CSV, the characters used for separation do not always adhere to the standard.  Given its simplicity, CSV is very easy to read by programming languages and applications.

#### XML ([Extensible Markup Language](http://en.wikipedia.org/wiki/XML))

XML is meant to be both human and machine readable and meant to be able model any data strcture.  Though this is powerful, it often means that documentation is needed to fully understand the data.  XML is often hard to parse with programming languages given its free form structure.  XML is not preferred unless you spend the extra time to ensure that it is well-formed and follows the specification.

### Specific formats

Given the dataset, specific formats may be a preferred format.

#### [GeoJSON](http://en.wikipedia.org/wiki/GeoJSON)

GeoJSON is a specification of JSON aimed at representing geographical data.

#### [TopoJSON](http://en.wikipedia.org/wiki/TopoJSON)

TopoJSON is a more compact version of GeoJSON.

#### SQL ([Structured Query Language](http://en.wikipedia.org/wiki/SQL))

SQL is the language of many relational databases, including MySQL, PostgreSQL, SQLite, SQL Server, and more.  There is a common set of the language that most of these databases support, but all of the databases have their own features.  This means that data in SQL format can be very flexible if care is taken to ensure it in the common format.

#### ESRI [Shapefile](http://en.wikipedia.org/wiki/Shapefile)

This is for geographic data.  This is an exception to the non-proprietary suggestion.  Shapefiles are very commonly used for geographical information and given it's compression, it is helpful for large amounts of data.

### Media (documents, images, audio, video)

Some datasets are large collection of media such as a group of documents or images.  The best way to handle these datasets is to create a dataset that holds the metadata for each piece of media and provides a reference to the media file or URL.

#### Open media formats

The following are open formats for media that are the most commonly used:

* Audio: [Ogg](http://en.wikipedia.org/wiki/Ogg)
* Video: [Matroska MKV](http://en.wikipedia.org/wiki/Matroska)
* Image: [PNG](http://en.wikipedia.org/wiki/Portable_Network_Graphics), [SVG](http://en.wikipedia.org/wiki/Scalable_Vector_Graphics)
* Documents: [OpenDocument](http://en.wikipedia.org/wiki/OpenDocument), [Plain text](http://en.wikipedia.org/wiki/Plain_text)

### Archiving and compression

It often makes sense to compress a dataset or a set of datasets to save space and bandwidth.  Unfortunately there is not a common compression format that is easily supported on multiple platforms.  This means that providing multiple formats is probably the best solution.

* [.zip](http://en.wikipedia.org/wiki/ZIP_(file_format)) are widely supported but not entirely open.
* [.gz](http://en.wikipedia.org/wiki/Gzip) or [.tar](http://en.wikipedia.org/wiki/Tar_(file_format)) are open but not supported without external software on systems like Microsoft Windows.

### Formats not to use

The following are formats that you should not use.

#### PDF ([Portable Document Format](http://en.wikipedia.org/wiki/Portable_Document_Format))

The PDF format is meant to be a common document format, specifically so that documents look the same across different platforms.  It is not a data format.  It is also proprietary.

#### HTML ([Hypertext Markup Language](http://en.wikipedia.org/wiki/HTML))

HTML is meant to provide formating and meaning to text.  It is not a data format.

#### [Microsoft Excel](http://en.wikipedia.org/wiki/Microsoft_Excel)

Excel files are proprietary and not data formats.  Excel files are specific to the Excel application, are hard to parse, and have much more information embedded in them than just data.  Microsoft Excel makes it easy to export to CSV.

#### [Microsoft Word](http://en.wikipedia.org/wiki/Microsoft_Word)

Word is proprietary and a document format.  It cannot be easily parsed.

#### A web interface

An interface, for instance a form to search a data set, is not a data format.

## Access to data

Data should not be behind any sort of login process or agreement process.  A computer should be able to easily access the data through a URL.

### Mechanics

The two main mechanisms for obtaining data are from direct downloads or an API (Application Programming Interface).  Both these mechanisms are important; an API can provide the ability to get specific parts of the datasets when needed, while complete dataset downloads are very helpful when doing analysis.

#### Direct (bulk) downloads

Direct downloads mean that specific sets of data can be downloaded all at once.  This is really helpful for analysis and working with the data offline.  Overall, this mechanism is more important than an API, as direct downloads will provide all the data and the ability to analyze.  Do make sure that prermance and linkability are followed (see below).

#### APIs

Overall, an API approach will be more resource intensive for you to implement.  A general rule of thumb is that as the size of dataset grows or the frequency of which it is updated grows, the more likely an API will be needed.

* APIs should follow the [REST](http://en.wikipedia.org/wiki/Representational_state_transfer) specification as close as possible.
* APIs must be documented well regardless of how they are implemented.  Examples are also very helpful.  See [Github's API documentation](http://developer.github.com/v3/) for a good example.
* Use HTTP Headers to communicate metadata.

### Permanence

It takes significant resources to ensure data is available now and into the future, but if you're goal is to be the authority on the data it is important to keep your data resources up.  This means that a simple solution to host your data may be the best fit.

### Linkability

A consistent, permament, predicatable, and readable URL to data resources is extremely important both for reference sake but for applications that directly pull data in directly.

## Licensing

Licensing means to put some legal terms on the data for how it can or cannot be used.  You should use a license that is as permissive as possible, such as [CCO](http://creativecommons.org/publicdomain/zero/1.0/).  If you really have the need to require attribution and [copyleft](http://en.wikipedia.org/wiki/Copyleft), then look at the [ODBL](http://opendatacommons.org/licenses/odbl/summary/).  Depending on your local laws, your data may already be licensed.  Also note that these existing licenses provide information on warranty.
 
## Not another open data format document

This is being put together as the following documents are inspiring but don't seem to get to a firm, concise recommendation: [Sunlight Open Data Guidelines](http://sunlightfoundation.com/opendataguidelines/#open-formats), [Open Data Handbook](http://opendatahandbook.org/en/appendices/file-formats.html), [Open Data is Civic Capital](http://razor.occams.info/pubdocs/opendataciviccapital.html#format)
