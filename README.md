# ENUMS [WWW](https://github.com/totemstan/enums)  [COE](https://sc.appdev.proj.coe/acmesds/enums)  [SBU](https://gitlab.west.nga.ic.gov/acmesds/enums)

Provides methods to clock, fetch, enumerate, stream, fetch and get data.  Also makes connections
to required services: mysql, neo4j, txmail, rxmail.

## Installation

Simply clone **ENUMS** from one of its repos:

	git clone https://github.com/totemstan/enums
	git clone https://sc.appdev.proj.coe/acmesds/enums
	git clone https://gitlab.west.nga.ic.gov/acmesds/enums

## Manage 

	npm test [ ? || E1 || ...]	# Run unit test
	npm run redoc						# Update and distribute documentation

## Usage

From your module:

	const { Copy, Each, Extend, Stream, Fetch, ... } = require("./enums");  	// extract required methods
	
## Program Reference
<details>
<summary>
<i>Open / Close</i>
</summary>
## Modules

<dl>
<dt><a href="#module_ENUMS">ENUMS</a></dt>
<dd><p>Provides methods to clock, fetch, enumerate, regulate, stream, fetch and get data.  This module 
documented in accordance with <a href="https://jsdoc.app/">jsdoc</a>.</p>
<h3 id="env-dependencies">Env Dependencies</h3>
<pre><code>FETCH_PASS = password for local fetching cert
URL_LEXNEX = URL to lexis-nexis service w user/password credentials
URL_MYSQL = URL to mysql service w user/password credentials
URL_NEO4J = URL to neo4j service w user/password credentials
URL_TXMAIL = URL to smtp email service w user/password credentials
URL_RXMAIL = URL to imap email service w user/password credentials
URL_RSSFEED = URL to rss service w user/password credentials
URL_LEXNEX = URL to lexis-nexis service w user/password credentials
</code></pre>
</dd>
<dt><a href="#ENUMS.module_Array">Array</a></dt>
<dd></dd>
<dt><a href="#ENUMS.module_String">String</a></dt>
<dd></dd>
<dt><a href="#ENUMS.module_Clock">Clock</a></dt>
<dd><p>Create a clock object with specified trace switch, every interval, on-off times, and 
start date.  See the clock tick method for more information.</p>
</dd>
</dl>

<a name="module_ENUMS"></a>

## ENUMS
Provides methods to clock, fetch, enumerate, regulate, stream, fetch and get data.  This module 
documented in accordance with [jsdoc](https://jsdoc.app/).

### Env Dependencies

	FETCH_PASS = password for local fetching cert
	URL_LEXNEX = URL to lexis-nexis service w user/password credentials
	URL_MYSQL = URL to mysql service w user/password credentials
	URL_NEO4J = URL to neo4j service w user/password credentials
	URL_TXMAIL = URL to smtp email service w user/password credentials
	URL_RXMAIL = URL to imap email service w user/password credentials
	URL_RSSFEED = URL to rss service w user/password credentials
	URL_LEXNEX = URL to lexis-nexis service w user/password credentials

**Requires**: <code>module:os</code>, <code>module:cluster</code>, <code>module:fs</code>, <code>module:http</code>, <code>module:https</code>, <code>module:vm</code>, <code>module:cp</code>, <code>module:crypto</code>, <code>module:stream</code>, <code>module:mysql</code>, <code>module:neo4j-driver</code>, <code>module:nodemailer</code>, <code>module:nodemailer-smtp-transport</code>, <code>module:neo4j-driver</code>  
**Author**: [ACMESDS](https://totemstan.github.io)  

* [ENUMS](#module_ENUMS)
    * [.mysqlOpts](#module_ENUMS.mysqlOpts)
    * [.neo4jOpts](#module_ENUMS.neo4jOpts)
    * [.rxmailOpts](#module_ENUMS.rxmailOpts)
    * [.txmailOpts](#module_ENUMS.txmailOpts)
    * [.escapeId](#module_ENUMS.escapeId)
    * [.escape](#module_ENUMS.escape)
    * [.Log](#module_ENUMS.Log)
    * [.sites](#module_ENUMS.sites)
    * [.maxFiles](#module_ENUMS.maxFiles)
    * [.maxRetry](#module_ENUMS.maxRetry)
    * [.certs](#module_ENUMS.certs)
    * [.Debug()](#module_ENUMS.Debug)
    * [.Trace()](#module_ENUMS.Trace)
    * [.config(opts)](#module_ENUMS.config)
    * [.typeOf()](#module_ENUMS.typeOf)
    * [.getList()](#module_ENUMS.getList)
    * [.Copy(src, tar, deep)](#module_ENUMS.Copy) ⇒ <code>Object</code>
    * [.Each(A, cb)](#module_ENUMS.Each)
    * [.Stream(src, cb()](#module_ENUMS.Stream)
    * [.Regulate(opts, taskcb(recs,ctx,res), feedcb(err,step))](#module_ENUMS.Regulate) ⇒ <code>Clock</code>
    * [.Fetch(ref, cb, [cb])](#module_ENUMS.Fetch)

<a name="module_ENUMS.mysqlOpts"></a>

### ENUMS.mysqlOpts
**Kind**: static property of [<code>ENUMS</code>](#module_ENUMS)  
<a name="module_ENUMS.neo4jOpts"></a>

### ENUMS.neo4jOpts
**Kind**: static property of [<code>ENUMS</code>](#module_ENUMS)  
<a name="module_ENUMS.rxmailOpts"></a>

### ENUMS.rxmailOpts
**Kind**: static property of [<code>ENUMS</code>](#module_ENUMS)  
<a name="module_ENUMS.txmailOpts"></a>

### ENUMS.txmailOpts
**Kind**: static property of [<code>ENUMS</code>](#module_ENUMS)  
<a name="module_ENUMS.escapeId"></a>

### ENUMS.escapeId
**Kind**: static property of [<code>ENUMS</code>](#module_ENUMS)  
<a name="module_ENUMS.escape"></a>

### ENUMS.escape
**Kind**: static property of [<code>ENUMS</code>](#module_ENUMS)  
<a name="module_ENUMS.Log"></a>

### ENUMS.Log
**Kind**: static property of [<code>ENUMS</code>](#module_ENUMS)  
<a name="module_ENUMS.sites"></a>

### ENUMS.sites
Fetch quick SITEREFs

	https://www.programmableweb.com/search/military

	ACLED
	https://www.programmableweb.com/api/acled-rest-api-v25
	ACCT teliy40602@plexfirm.com / ACLEDsnivel1
	API https://developer.acleddata.com/rehd/cms/views/acled_api/documents/API-User-Guide.pdf
	SITE https://developer.acleddata.com/
	The Armed Conflict Location & Event Data Project (ACLED) is a real-time data and and crisis analysis and mapping project on political violence and protest across the world. ACLED's mission is to produce dis-aggregated, locally informed data and analysis globally in real time. An ACLED REST API enables users to retrieve data about actors, actor type, country, region and get data in JSON, XML, CSV or text. Filter data by date, area, pagination, etc.

	Animetrics FIMS
	https://www.programmableweb.com/api/animetrics-fims-cloud-rest-api
	http://animetrics.com/fims-cloud
	Aimed at the law enforcement, security and military intelligence industries, Animetrics' FaceR Identity Management Solution (FIMS) allows organizations to bring mobile security and video surveillance facial-biometrics applications into the field for use in real time. FIMS Cloud is used to centralize and access a user's cloud based photographic stores using facial recognition. FIMS Cloud organizes, searches and centralizes access to photographic stores using 1:many web service based verification engine. Access to the service is provided via a RESTful API. Public documentation is not available.

	Navlost WXT Weather Tesseract
	https://www.programmableweb.com/api/navlost-wxt-weather-tesseract
	The WXT Weather Service provides atmospheric weather information through a REST architecture, HTTP requests, and JSON formats. It integrates METAR/TAF information, sun, and moon calculations, targeting aviation and energy applications. Advanced features include: -Upper atmosphere information (e.g., research, aviation, rocketry, military) -Automated, push-type notification of arbitrary weather-related events (alert service) -Calculation of arbitrary results derived from weather forecast information via a server-side scripting language. The default response type is application/json, although other formats may be supported. At the present time, there is partial support for comma-separated value (CSV) responses.
	https://wxt.navlost.eu/api/v1/
	https://wxt.navlost.eu/doc/api/

**Kind**: static property of [<code>ENUMS</code>](#module_ENUMS)  
<a name="module_ENUMS.maxFiles"></a>

### ENUMS.maxFiles
Max files to Fetch when indexing a folder

**Kind**: static property of [<code>ENUMS</code>](#module_ENUMS)  
<a name="module_ENUMS.maxRetry"></a>

### ENUMS.maxRetry
Fetch wget/curl maxRetry

**Kind**: static property of [<code>ENUMS</code>](#module_ENUMS)  
<a name="module_ENUMS.certs"></a>

### ENUMS.certs
Legacy Fetching certs

**Kind**: static property of [<code>ENUMS</code>](#module_ENUMS)  
<a name="module_ENUMS.Debug"></a>

### ENUMS.Debug()
**Kind**: static method of [<code>ENUMS</code>](#module_ENUMS)  
<a name="module_ENUMS.Trace"></a>

### ENUMS.Trace()
Trace log message and args.

**Kind**: static method of [<code>ENUMS</code>](#module_ENUMS)  
<a name="module_ENUMS.config"></a>

### ENUMS.config(opts)
Configure enums

**Kind**: static method of [<code>ENUMS</code>](#module_ENUMS)  

| Param | Type | Description |
| --- | --- | --- |
| opts | <code>Object</code> | options |

<a name="module_ENUMS.typeOf"></a>

### ENUMS.typeOf()
Test an object x:

	isString(x), isDate(x), isFunction(x), isArray(x), isObject(x)
	isEmpty(x), isNumber(x), isKeyed(x), isBoolean(x), isBuffer(x)
	isError(x)

**Kind**: static method of [<code>ENUMS</code>](#module_ENUMS)  
<a name="module_ENUMS.getList"></a>

### ENUMS.getList()
**Kind**: static method of [<code>ENUMS</code>](#module_ENUMS)  
<a name="module_ENUMS.Copy"></a>

### ENUMS.Copy(src, tar, deep) ⇒ <code>Object</code>
Copy source hash src to target hash tar.  If the copy is shallow (deep = false), a 
Copy({...}, {}) is equivalent to new Object({...}).  In a deep copy,
(e.g. deep = "."), src keys are treated as keys into the target thusly:

	{	
		A: value,			// sets target[A] = value

		"A.B.C": value, 	// sets target[A][B][C] = value

		"A.B.C.": {			// appends X,Y to target[A][B][C]
			X:value, Y:value, ...
		},	

		OBJECT: [ 			// prototype OBJECT (Array,String,Date,Object) = method X,Y, ...
			function X() {}, 
			function Y() {}, 
		... ]

	}

**Kind**: static method of [<code>ENUMS</code>](#module_ENUMS)  
**Returns**: <code>Object</code> - target hash  

| Param | Type | Description |
| --- | --- | --- |
| src | <code>Object</code> | source hash |
| tar | <code>Object</code> | target hash |
| deep | <code>String</code> | copy key |

<a name="module_ENUMS.Each"></a>

### ENUMS.Each(A, cb)
Enumerate Object A over its keys with callback cb(key,val).

**Kind**: static method of [<code>ENUMS</code>](#module_ENUMS)  

| Param | Type | Description |
| --- | --- | --- |
| A | <code>Object</code> | source object |
| cb | <code>function</code> | callback (key,val) |

<a name="module_ENUMS.Stream"></a>

### ENUMS.Stream(src, cb()
Stream a src array, object or file using:

	Stream(src, opts, (rec,key,res) => {
		if ( res ) // still streaming 
			res( msg || undefined )  // pass undefined to bypass msg stacking

		else 
			// streaming done so key contains msg stack
	})

**Kind**: static method of [<code>ENUMS</code>](#module_ENUMS)  

| Param | Type | Description |
| --- | --- | --- |
| src | <code>Object</code> \| <code>Array</code> \| <code>String</code> | source object or array |
| cb( | <code>function</code> | rec || null, key, res ) Callback |

**Example**  
```js
Serialize a list:

	function fetcher( rec, info => { 
	});

	[ rec, ...].serialize( fetcher, (rec, fails) => {
		if ( rec ) 
			// rec = record being serialized
		else
			// done. fails = number of failed fetches
	}
```
**Example**  
```js
Serialize a string:

	function fetcher( rec, ex => {
		// regexp arguments rec.arg0, rec.arg1, rec.arg2, ...
		// rec.ID = record number being processed
		return "replaced string";
	});

	"string to search".serialize( fetcher, regex, "placeholder key", str => { 
		// str = final string with all replacements made
	});
```
<a name="module_ENUMS.Regulate"></a>

### ENUMS.Regulate(opts, taskcb(recs,ctx,res), feedcb(err,step)) ⇒ <code>Clock</code>
Regulate a task defined by options `opts`

	every 	= N [sec||min||hr||...]
	start	= DATE  
	end		= DATE  
	on		= NUM  
	off		= NUM  			
	util	= NUM  

	batch	= INT  
	watch	= NUM  
	limit	= INT  

with callbacks to

	taskcb( recs, ctx, res ) 
	to process `recs`-batch in `ctx`-context with `res` saver
	
	feedcb( step ) 
	to feed `recs`-batch to the queue via `step(recs)` 

When a `feedcb` is provided, the mandatory `taskcb` is placed into a 
stream workflow that terminates when the `recs`-batch goes null.  This 
`taskcb` *must* call its `res([save])` callback to advance the task; 
the supplied `ctx`-context is loaded from (and saved into) its 
json store every time the task is stepped.

If no `feedcb` is provided, the `taskcb` is periodically executed with 
a null `recs`-batch and the callback to `res([save])` is *optional*.

The regulated task is monitored/managed by the supplied options

	task 	= notebook being regulated (default "notask")
	name	= usecase being regulated (default "nocase")
	watch	= QoS task watchdog timer [s]; 0 disabled (default 60)

A nonzero QoS sets a tasking watchdog timer to manage the task.  A credit
deficient client is signalled by calling `feedcb(null)`.

To establish the task as a proposal, set Sign0 = 1 in the taskDB: in so 
doing, if Sign1 , ... are not signed-off (eg not approved by a task oversight
commitee) before the proposal's start time, the task will be killed.

The following DBs are used:

	openv.profiles client credit/billing information
	openv.queues tasking/billing information
	openv.<task> holds the task context and snapshot state

**Kind**: static method of [<code>ENUMS</code>](#module_ENUMS)  
**Returns**: <code>Clock</code> - Clock built for regulation options  

| Param | Type | Description |
| --- | --- | --- |
| opts | <code>Object</code> | Task regulation options hash |
| taskcb(recs,ctx,res) | <code>function</code> | Process record batch recs in context ctx then respond using res |
| feedcb(err,step) | <code>function</code> | Feed a record batch recs using step(recs) |

<a name="module_ENUMS.Fetch"></a>

### ENUMS.Fetch(ref, cb, [cb])
GET (PUT || POST || DELETE) information from (to) a `ref` url

	PROTOCOL://HOST/FILE ? QUERY & FLAGS
	SITEREF

given a `cb` callback function (or a `data` Array || Object || null).

The `ref` url specifies a PROTOCOL

	http(s) 	=	http (https) protocol
	curl(s) 	=	curl (curls uses certs/fetch.pfx to authenticate)
	wget(s)		=	wget (wgets uses certs/fetch.pfx to authenticate)
	mask 		=	http access via rotated proxies
	file		=	file or folder
	notebook	=	selected notebook record
	lexnex 		=	Lexis-Nexis oauth access to documents

All "${key}" in `ref` are replaced by QUERY[key].  When a FILE is "/"-terminated, a 
folder index is returned.  Use the FLAGS

	_every 	= "sec||min||hr||..."
	_start	= DATE  
	_end	= DATE  
	_watch	= NUM  
	_limit	= INT  
	_on		= NUM  
	_off	= NUM  						
	_util	= NUM  
	_name	= "job name"
	_client = "job owner"

to regulate the fetch in a job queue with periodic callbacks to `cb`.  Use 
the FLAGS

	_batch	= NUM
	_limit	= NUM
	_keys	= [...]
	_comma	= "delim"
	_newline= "delim"

to read a csv-file and feed record batches to the `cb` callback.

**Kind**: static method of [<code>ENUMS</code>](#module_ENUMS)  

| Param | Type | Description |
| --- | --- | --- |
| ref | <code>String</code> | source URL |
| cb | <code>string</code> \| <code>array</code> \| <code>function</code> \| <code>null</code> | callback or data |
| [cb] | <code>function</code> | optional callback when first cb is data |

**Example**  
```js
Fetch( ref, text => {			// get request
})
```
**Example**  
```js
Fetch( ref, [ ... ], stat => { 	// post request with data hash list
})
```
**Example**  
```js
Fetch( ref, { ... }, stat => { 	// put request with data hash
})
```
**Example**  
```js
Fetch( ref, null, stat => {		// delete request 
})
```
<a name="ENUMS.module_Array"></a>

## Array

* [Array](#ENUMS.module_Array)
    * [~serialize(fetched, cb)](#ENUMS.module_Array..serialize)
    * [~any(cb)](#ENUMS.module_Array..any) ⇒
    * [~all(cb)](#ENUMS.module_Array..all) ⇒
    * [~get(index, ctx)](#ENUMS.module_Array..get) ⇒ <code>Object</code>

<a name="ENUMS.module_Array..serialize"></a>

### Array~serialize(fetched, cb)
Serialize an Array to the callback cb(rec,info) or cb(null,stack) at end given 
a sync/async fetcher( rec, res ).

**Kind**: inner method of [<code>Array</code>](#ENUMS.module_Array)  

| Param | Type | Description |
| --- | --- | --- |
| fetched | <code>function</code> | Callback to fetch the data sent to the cb |
| cb | <code>function</code> | Callback to process the fetched data. |

<a name="ENUMS.module_Array..any"></a>

### Array~any(cb) ⇒
**Kind**: inner method of [<code>Array</code>](#ENUMS.module_Array)  
**Returns**: this  

| Param | Type | Description |
| --- | --- | --- |
| cb | <code>function</code> | Callback(arg,idx) |

<a name="ENUMS.module_Array..all"></a>

### Array~all(cb) ⇒
**Kind**: inner method of [<code>Array</code>](#ENUMS.module_Array)  
**Returns**: this  

| Param | Type | Description |
| --- | --- | --- |
| cb | <code>function</code> | Callback(arg,idx) |

<a name="ENUMS.module_Array..get"></a>

### Array~get(index, ctx) ⇒ <code>Object</code>
Index an array using a indexor:

	string of the form "to=from & to=eval & to & ... & !where=eval"
	hash of the form {to: from, ...}
	callback of the form (idx,array) => { ... }

The "!where" clause returns only records having a nonzero eval.

**Kind**: inner method of [<code>Array</code>](#ENUMS.module_Array)  
**Returns**: <code>Object</code> - Indexed data  

| Param | Type | Description |
| --- | --- | --- |
| index | <code>String</code> \| <code>Object</code> \| <code>function</code> | Indexer |
| ctx | <code>Object</code> | Context of functions etc |

**Example**  
```js
[{x:1,y:2},{x:10,y:20}].get("u=x+1&v=sin(y)&!where=x>5",Math)
{ u: [ 11 ], v: [ 0.9129452507276277 ] }
```
**Example**  
```js
[{x:1,y:2},{x:10,y:20}].get("x")
{ x: [ 1, 10 ] }
```
**Example**  
```js
[{x:1,y:2},{x:10,y:20}].get("x&mydata=y")
{ mydata: [ 2, 20 ], x: [ 1, 10 ] }
```
**Example**  
```js
[{x:1,y:2},{x:10,y:20}].get("mydata=[x,y]")
{ mydata: [ [ 1, 2 ], [ 10, 20 ] ] }
```
**Example**  
```js
[{x:1,y:2},{x:10,y:20}].get("mydata=x+1")
{ mydata: [ 2, 11 ] }
```
**Example**  
```js
[{x:1,y:2},{x:10,y:20}].get("",{"!all":1})
{ x: [ 1, 10 ], y: [ 2, 20 ] }
```
**Example**  
```js
[{x:1,y:2},{x:10,y:20}].get("")
[ { x: 1, y: 2 }, { x: 10, y: 20 } ]
```
**Example**  
```js
[{x:1,y:2},{x:10,y:20}].get("u")
{ u: [ undefined, undefined ] }
```
**Example**  
```js
[[1,2,3],[10,20,30]].get("1&0")
{ '0': [ 1, 10 ], '1': [ 2, 20 ] }	
```
<a name="ENUMS.module_String"></a>

## String

* [String](#ENUMS.module_String)
    * [~replaceSync()](#ENUMS.module_String..replaceSync)
    * [~tag(el, at)](#ENUMS.module_String..tag) ⇒ <code>String</code>
    * [~parseEval($)](#ENUMS.module_String..parseEval)
    * [~parseJS(ctx)](#ENUMS.module_String..parseJS)
    * [~parse$(query)](#ENUMS.module_String..parse$)
    * [~parseJSON(def)](#ENUMS.module_String..parseJSON)
    * [~parsePath(query, index, flags, where)](#ENUMS.module_String..parsePath) ⇒ <code>Array</code>
    * [~chunkFile(path, opts, {Function))](#ENUMS.module_String..chunkFile)
    * [~parseFile(path, opts, cb)](#ENUMS.module_String..parseFile)
    * [~streamFile(path, opts, cb)](#ENUMS.module_String..streamFile)
    * [~trace(msg, req, res)](#ENUMS.module_String..trace)
    * [~serialize()](#ENUMS.module_String..serialize)
    * [~get()](#ENUMS.module_String..get)

<a name="ENUMS.module_String..replaceSync"></a>

### String~replaceSync()
**Kind**: inner method of [<code>String</code>](#ENUMS.module_String)  
<a name="ENUMS.module_String..tag"></a>

### String~tag(el, at) ⇒ <code>String</code>
Tag url with specified attributes.

**Kind**: inner method of [<code>String</code>](#ENUMS.module_String)  
**Returns**: <code>String</code> - tagged results  

| Param | Type | Description |
| --- | --- | --- |
| el | <code>String</code> | tag html element or one of "?&/:=" |
| at | <code>String</code> | tag attributes = {key: val, ...} |

<a name="ENUMS.module_String..parseEval"></a>

### String~parseEval($)
Parse "$.KEY" || "$[INDEX]" expressions given $ hash.

**Kind**: inner method of [<code>String</code>](#ENUMS.module_String)  

| Param | Type | Description |
| --- | --- | --- |
| $ | <code>Object</code> | source hash |

<a name="ENUMS.module_String..parseJS"></a>

### String~parseJS(ctx)
Run JS against string in specified context.

**Kind**: inner method of [<code>String</code>](#ENUMS.module_String)  

| Param | Type | Description |
| --- | --- | --- |
| ctx | <code>Object</code> | context hash |

<a name="ENUMS.module_String..parse$"></a>

### String~parse$(query)
Return an EMAC "...${...}..." string using supplied context.

**Kind**: inner method of [<code>String</code>](#ENUMS.module_String)  

| Param | Type | Description |
| --- | --- | --- |
| query | <code>Object</code> | context hash |

<a name="ENUMS.module_String..parseJSON"></a>

### String~parseJSON(def)
Parse string into json or set to default value/callback if invalid json.

**Kind**: inner method of [<code>String</code>](#ENUMS.module_String)  

| Param | Type | Description |
| --- | --- | --- |
| def | <code>function</code> \| <code>Object</code> | default object or callback that returns default |

<a name="ENUMS.module_String..parsePath"></a>

### String~parsePath(query, index, flags, where) ⇒ <code>Array</code>
Parse a "PATH?PARM&PARM&..." url into the specified query, index, flags, or keys hash
as directed by the PARM = ASKEY := REL || REL || _FLAG = VALUE where 
REL = X OP X || X, X = KEY || KEY$[IDX] || KEY$.KEY and returns [path,file,type].

**Kind**: inner method of [<code>String</code>](#ENUMS.module_String)  
**Returns**: <code>Array</code> - [path,table,type,area,url]  

| Param | Type | Description |
| --- | --- | --- |
| query | <code>Object</code> | hash of query keys |
| index | <code>Object</code> | hash of sql-ized indexing keys |
| flags | <code>Object</code> | hash of flag keys |
| where | <code>Object</code> | hash of sql-ized conditional keys |

<a name="ENUMS.module_String..chunkFile"></a>

### String~chunkFile(path, opts, {Function))
Chunk stream at path by splitting into newline-terminated records.
Callback cb(record) until the limit is reached (until eof when !limit)
with cb(null) at end.

**Kind**: inner method of [<code>String</code>](#ENUMS.module_String)  

| Param | Type | Description |
| --- | --- | --- |
| path | <code>String</code> | source file |
| opts | <code>Object</code> | {newline,limit} options |
| {Function) |  | cb Callback(record) |

<a name="ENUMS.module_String..parseFile"></a>

### String~parseFile(path, opts, cb)
Parse a csv/txt/json stream at the specified path dependings on if the
keys is

	[] then record keys are determined by the first header record; 
	[ 'key', 'key', ...] then header keys were preset; 
	null then raw text records are returned; 
	function then use to parse records.  

The file is chunked using the (newline,limit) chinkFile parameters.  
Callsback cb(record) for each record with cb(null) at end.

**Kind**: inner method of [<code>String</code>](#ENUMS.module_String)  

| Param | Type | Description |
| --- | --- | --- |
| path | <code>String</code> | source file |
| opts | <code>Object</code> | {keys,comma,newline,limit} options |
| cb | <code>function</code> | Callback(record || null) |

<a name="ENUMS.module_String..streamFile"></a>

### String~streamFile(path, opts, cb)
Stream file at path containing comma delimited values.  The file is split using the (keys,comma) 
file splitting parameters, and chunked using the (newline,comma) file chunking parameters. Callsback 
cb( [record,...] ) with the record batch or cb( null ) at end.

**Kind**: inner method of [<code>String</code>](#ENUMS.module_String)  

| Param | Type | Description |
| --- | --- | --- |
| path | <code>String</code> | source file |
| opts | <code>Object</code> | {keys,comma,newline,limit,batch} options |
| cb | <code>function</code> | Callback( [record,...] || null ) |

<a name="ENUMS.module_String..trace"></a>

### String~trace(msg, req, res)
Trace message to console with optional request to place into syslogs

**Kind**: inner method of [<code>String</code>](#ENUMS.module_String)  

| Param | Type | Description |
| --- | --- | --- |
| msg | <code>String</code> | message to trace |
| req | <code>Object</code> | request { sql, query, client, action, table } |
| res | <code>function</code> | response callback(msg) |

<a name="ENUMS.module_String..serialize"></a>

### String~serialize()
Serialize this String to the callback(results) given a sync/asyn fetcher(rec,res) where
rec = {ID, arg0, arg1, ...} contains args produced by regex.  Provide a unique placeholder
key to back-substitute results.

**Kind**: inner method of [<code>String</code>](#ENUMS.module_String)  
**Example**  
```js
"junkabc;junkdef;"
	.serialize( (rec,cb) => cb("$"), /junk([^;]*);/g, "@tag", msg => console.log(msg) )

produces:

	"$$"
```
<a name="ENUMS.module_String..get"></a>

### String~get()
Fetch using supplied url.

**Kind**: inner method of [<code>String</code>](#ENUMS.module_String)  
<a name="ENUMS.module_Clock"></a>

## Clock
Create a clock object with specified trace switch, every interval, on-off times, and 
start date.  See the clock tick method for more information.


| Param | Type | Description |
| --- | --- | --- |
| trace | <code>Boolean</code> | tracking switch |
| every | <code>String</code> \| <code>Float</code> | tick interval |
| on | <code>Float</code> | on-time or 0 implies infinity |
| off | <code>Float</code> | off-time or 0 |
| start | <code>Date</code> | start date |


* [Clock](#ENUMS.module_Clock)
    * [~now()](#ENUMS.module_Clock..now) ⇒ <code>Date</code>
    * [~tick(cb)](#ENUMS.module_Clock..tick) ⇒ <code>Date</code>

<a name="ENUMS.module_Clock..now"></a>

### Clock~now() ⇒ <code>Date</code>
**Kind**: inner method of [<code>Clock</code>](#ENUMS.module_Clock)  
**Returns**: <code>Date</code> - Current clock time  
<a name="ENUMS.module_Clock..tick"></a>

### Clock~tick(cb) ⇒ <code>Date</code>
Return the wait time to next event, with callback(wait,next) when at snapshot events.

Example below for ON = 4 and OFF = 3 steps of length clock.every = sec|min|hour|...

Here S|B|* indicates the end of snapshot|batch|start events.  The clock starts on epoch = OFF 
with a wait = 0.  The clock's host has 1 step to complete its batch tasks, and OFF steps to 
complete its snapshot tasks.  Here, the work CYCLE = ON+OFF with a utilization = ON/CYCLE.  
Use OFF = 0 to create a continious process.  

		S			*	B	B	B	S			*	B	B	B
		|			|	|	|	|	|			|	|	|	|		...
		|			|	|	|	|	|			|	|	|	|		
		x-->x-->x-->x-->x-->x-->x-->x-->x-->x-->x-->x-->x-->x-->x-->x-->x-->x
epoch	0	1	2	3	4	5	6	7	8	9	10	11	12	13	14	15	16	17

		|<-- OFF -->|<---- ON ----->|

**Kind**: inner method of [<code>Clock</code>](#ENUMS.module_Clock)  
**Returns**: <code>Date</code> - Wait time  

| Param | Type | Description |
| --- | --- | --- |
| cb | <code>function</code> | Callback |

</details>

## Contacting, Contributing, Following

Feel free to 
* submit and status **TOTEM** issues (
[WWW](http://totem.zapto.org/issues.view) 
[COE](https://totem.west.ile.nga.ic.gov/issues.view) 
[SBU](https://totem.nga.mil/issues.view)
)  
* contribute to **TOTEM** notebooks (
[WWW](http://totem.zapto.org/shares/notebooks/) 
[COE](https://totem.west.ile.nga.ic.gov/shares/notebooks/) 
[SBU](https://totem.nga.mil/shares/notebooks/)
)  
* revise **TOTEM** requirements (
[WWW](http://totem.zapto.org/reqts.view) 
[COE](https://totem.west.ile.nga.ic.gov/reqts.view) 
[SBU](https://totem.nga.mil/reqts.view), 
)  
* browse **TOTEM** holdings (
[WWW](http://totem.zapto.org/) 
[COE](https://totem.west.ile.nga.ic.gov/) 
[SBU](https://totem.nga.mil/)
)  
* or follow **TOTEM** milestones (
[WWW](http://totem.zapto.org/milestones.view) 
[COE](https://totem.west.ile.nga.ic.gov/milestones.view) 
[SBU](https://totem.nga.mil/milestones.view)
).

## License

[MIT](LICENSE)

* * *

&copy; 2012 ACMESDS