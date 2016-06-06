## DataLoader

[src/index.js:43-183](https://github.com/nxus/data-loader/blob/79a319262520f3cc3d172a2bbee85cf802334a3a/src/index.js#L43-L183 "Source code on GitHub")

Import file contents as arrays of objects

### Installation

> npm install @nxus/data-loader --save

### Options

All responses accept an options argument, in addition to any parser-specific options
you can indicate:

-   `mapping`: object of {field: newField} name mappings
-   `identityFields`: for importing to models, array of fields to be used for createOrUpdate query

### Events

You can modify the records during import with the following specific events:

-   `records.type`: e.g. `app.get('data-loader').after('records.csv', (results) => {})`
-   `record.type`: e.g. `app.get('data-loader).after('record.csv', (one) => {})`
-   `models.identity`: e.g. `app.get('data-loader').after('models.user', (results) => {})`
-   `model.identity`: e.g. `app.get('data-loader).after('model.user', (user) => {})`

record_ events occur after parsing and name mapping
model_ events occur after record events and before models are created/updated.

## API

### 

[src/index.js:32-32](https://github.com/nxus/data-loader/blob/4bac4d0d930e8152bc7d27ab2c2f135a233f8c36/src/index.js#L32-L32 "Source code on GitHub")

Import file contents as arrays of objects

#### Installation

> npm install @nxus/data-loader --save

#### Options

All responses accept an options argument, in addition to any parser-specific options
you can indicate:

-   `mapping`: object of {field: newField} name mappings
-   `identityFields`: for importing to models, array of fields to be used for createOrUpdate query
-   `truncate`: for importing to models, true/false for deleting existing collection data before import. Ignored if `identityFields` is provided.
-   `strict`: defaults to true. Only import columns/data that matches the attribute names for the model. Set to false to import everything.

#### Events

You can modify the records during import with the following specific events:

-   `records.type`: e.g. `app.get('data-loader').after('records.csv', (results) => {})`
-   `record.type`: e.g. `app.get('data-loader).after('record.csv', (one) => {})`
-   `models.identity`: e.g. `app.get('data-loader').after('models.user', (results) => {})`
-   `model.identity`: e.g. `app.get('data-loader).after('model.user', (user) => {})`

record_ events occur after parsing and name mapping
model_ events occur after record events and before models are created/updated.

### API

* * *

### export

[src/JSONExporter.js:14-21](https://github.com/nxus/data-loader/blob/4bac4d0d930e8152bc7d27ab2c2f135a233f8c36/src/JSONExporter.js#L14-L21 "Source code on GitHub")

Stringify an array of results into JSON. Assumes top-level is array, unless
 opts.key is provided to wrap results in an object.

**Parameters**

-   `records` **[array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)** 
-   `options` **[object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** 
-   `opts`  

### export

[src/index.js:112-116](https://github.com/nxus/data-loader/blob/4bac4d0d930e8152bc7d27ab2c2f135a233f8c36/src/index.js#L112-L116 "Source code on GitHub")

Request formattted output based on type

**Parameters**

-   `type` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The type (e.g. 'html') of the output content
-   `records` **\[[object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)]** The records to export
-   `opts` **[object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Options for the exporter context

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)** String of formatted output

### exporter

[src/index.js:96-98](https://github.com/nxus/data-loader/blob/4bac4d0d930e8152bc7d27ab2c2f135a233f8c36/src/index.js#L96-L98 "Source code on GitHub")

Provide an exporter for a particular type (file extension)

**Parameters**

-   `type` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The type (e.g. 'html') this exporter creates
-   `handler` **[function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)** Function to receive (content, options) and return formatted output content

### import

[src/index.js:125-132](https://github.com/nxus/data-loader/blob/4bac4d0d930e8152bc7d27ab2c2f135a233f8c36/src/index.js#L125-L132 "Source code on GitHub")

Request parsed results based on type

**Parameters**

-   `type` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The type (e.g. 'html') of the content
-   `content` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The contents to parse
-   `opts` **[object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Options for the parser context

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)** Array of parsed result objects

### importFile

[src/index.js:140-149](https://github.com/nxus/data-loader/blob/4bac4d0d930e8152bc7d27ab2c2f135a233f8c36/src/index.js#L140-L149 "Source code on GitHub")

Request parsed results from a file path

**Parameters**

-   `filename` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The filename to read and parse
-   `opts` **[object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Options for the parser context

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)** Array of parsed result objects

### importFileToModel

[src/index.js:172-176](https://github.com/nxus/data-loader/blob/4bac4d0d930e8152bc7d27ab2c2f135a233f8c36/src/index.js#L172-L176 "Source code on GitHub")

Import file contents to a model

**Parameters**

-   `model` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The identity of the model to populate
-   `filename` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The filename to read and parse
-   `opts` **[object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Options for the parser context

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)** Array of instances

### importToModel

[src/index.js:159-163](https://github.com/nxus/data-loader/blob/4bac4d0d930e8152bc7d27ab2c2f135a233f8c36/src/index.js#L159-L163 "Source code on GitHub")

Import string contents to a model

**Parameters**

-   `model` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The identity of the model to populate
-   `type` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The type (e.g. 'html') of the content
-   `content` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The contents to parse
-   `opts` **[object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Options for the parser context

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)** Array of instances

### parser

[src/index.js:86-90](https://github.com/nxus/data-loader/blob/4bac4d0d930e8152bc7d27ab2c2f135a233f8c36/src/index.js#L86-L90 "Source code on GitHub")

Provide a parser for a particular type (file extension)

**Parameters**

-   `type` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The type (e.g. 'html') this renderer should handle
-   `handler` **[function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)** Function to receive (content, options) and return parsed array of result objects

### parse

[src/JSONParser.js:14-20](https://github.com/nxus/data-loader/blob/4bac4d0d930e8152bc7d27ab2c2f135a233f8c36/src/JSONParser.js#L14-L20 "Source code on GitHub")

Parse JSON into an array of results. Assumes top-level is array, unless
 opts.key is provided to pick a top-level key from parsed object as results.

**Parameters**

-   `contents` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** 
-   `options` **[object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** 
-   `opts`  
