# Mongo to [D2](https://github.com/terrastruct/d2#related) (M2D2)

[D2](https://github.com/terrastruct/d2) Diagrams are very useful know exactly what schemas your database is following.
If you have a mongo database that you'd like to diagram, you can use this tool to generate a schema for it.

Here is an example of the output of this tool rendered in Terrastruct. 

![Example](./example.png)

## This Tool Supports
- Merging the same document referenced in other documents into the same table
- Recursively mapping Arrays and Documents
- Mapping only the user generated databases

## Installation

- Clone this repo
- `npm install`

## Usage

```sh
$ node index "mongodb://localhost:27017"
```

## Database Setup

Due to mongo having no actual relational data, we have to rely on the names of fields to get the correlation.
Thus a forign reference in Mongo should be of the form "_<collection_name>Id" or "<collection_name>Id" as a field in a document.
For example, if we have a collection named "templates" and a document links to its id 
then we expect the document to contain a field called "_templateId" or "templateId".

## Future

We will look in the future to move this tool to a npm distributed cli tool for better maintainability
and additional features.
