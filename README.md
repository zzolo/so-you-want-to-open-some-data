# So you want to open some data?

An attempt at an opinionated recommendation for how to release your data openly for those starting from scratch.  This is meant to describe what formats and methods are most helpful for open data, specifically in terms of how it can be used by computers (i.e. in applications and by technical people).  This assumes that open data is not necessarily meant for the general public.

This is meant for governments, government agencies, government departments, non-profits, and private companies, and any person that wants to make the data they collect most open.

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

#### GeoJSON

#### TopoJSON

#### SQL

#### ESRI Shapefile
 
## Not another open data format document

This is being put together as the following documents are inspiring but don't seem to get to a firm, concise recommendation: [Sunlight Open Data Guidelines](http://sunlightfoundation.com/opendataguidelines/#open-formats), [Open Data Handbook](http://opendatahandbook.org/en/appendices/file-formats.html), [Open Data is Civic Capital](http://razor.occams.info/pubdocs/opendataciviccapital.html#format)