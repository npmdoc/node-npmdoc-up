# api documentation for  [up (v0.7.0)](https://github.com/Automattic/cloudup-cli#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-up.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-up) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-up.svg)](https://travis-ci.org/npmdoc/node-npmdoc-up)
#### cloudup command-line executable

[![NPM](https://nodei.co/npm/up.png?downloads=true)](https://www.npmjs.com/package/up)

[![apidoc](https://npmdoc.github.io/node-npmdoc-up/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-up_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-up/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-up/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-up/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "bin": {
        "up": "bin/up",
        "up-streams": "bin/up-streams",
        "up-config": "bin/up-config",
        "up-copy": "bin/up-copy",
        "up-open": "bin/up-open"
    },
    "bugs": {
        "url": "https://github.com/Automattic/cloudup-cli/issues"
    },
    "dependencies": {
        "ansi": "~0.3.0",
        "bytes": "~2.1.0",
        "cliparoo": "1.0.0",
        "cloudup-client": "0.3.2",
        "co": "3.1.0",
        "co-prompt": "1.0.0",
        "commander": "1.3.2",
        "gnode": "0.1.1",
        "head": "~1.0.0",
        "is-code": "~1.1.0",
        "max-component": "~1.0.0",
        "ms": "0.7.1",
        "open": "0.0.5",
        "osenv": "~0.1.1",
        "osthumb": "0.0.1",
        "printf": "0.2.2",
        "sum-component": "~0.1.1",
        "term-list": "0.2.1",
        "thunkify": "2.1.2",
        "uid2": "0.0.3"
    },
    "description": "cloudup command-line executable",
    "devDependencies": {
        "better-assert": "*",
        "mocha": "*",
        "should": "*"
    },
    "directories": {},
    "dist": {
        "shasum": "3bd928e781313ce332d142eb6f43782dc24d2257",
        "tarball": "https://registry.npmjs.org/up/-/up-0.7.0.tgz"
    },
    "engines": {
        "node": ">=0.8.0"
    },
    "gitHead": "7c414a2b53c08ac2ab5a6b98c2f072deae0ff1bd",
    "homepage": "https://github.com/Automattic/cloudup-cli#readme",
    "keywords": [
        "cloudup",
        "upload",
        "file",
        "files",
        "cli"
    ],
    "license": "MIT",
    "maintainers": [
        {
            "name": "tjholowaychuk",
            "email": "tj@vision-media.ca"
        },
        {
            "name": "rauchg",
            "email": "rauchg@gmail.com"
        },
        {
            "name": "tootallnate",
            "email": "nathan@tootallnate.net"
        }
    ],
    "name": "up",
    "optionalDependencies": {},
    "preferGlobal": true,
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/Automattic/cloudup-cli.git"
    },
    "scripts": {},
    "version": "0.7.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module up](#apidoc.module.up)
1.  [function <span class="apidocSignatureSpan">up.</span>client (opts)](#apidoc.element.up.client)
1.  [function <span class="apidocSignatureSpan">up.</span>console (stream, options)](#apidoc.element.up.console)
1.  [function <span class="apidocSignatureSpan">up.</span>readConfig ()](#apidoc.element.up.readConfig)
1.  [function <span class="apidocSignatureSpan">up.</span>saveConfig (obj)](#apidoc.element.up.saveConfig)
1.  object <span class="apidocSignatureSpan">up.</span>console.prototype
1.  string <span class="apidocSignatureSpan">up.</span>configPath

#### [module up.console](#apidoc.module.up.console)
1.  [function <span class="apidocSignatureSpan">up.</span>console (stream, options)](#apidoc.element.up.console.console)

#### [module up.console.prototype](#apidoc.module.up.console.prototype)
1.  [function <span class="apidocSignatureSpan">up.console.prototype.</span>aggregate (item)](#apidoc.element.up.console.prototype.aggregate)
1.  [function <span class="apidocSignatureSpan">up.console.prototype.</span>log (y, key, str)](#apidoc.element.up.console.prototype.log)
1.  [function <span class="apidocSignatureSpan">up.console.prototype.</span>onend ()](#apidoc.element.up.console.prototype.onend)
1.  [function <span class="apidocSignatureSpan">up.console.prototype.</span>onitem (item)](#apidoc.element.up.console.prototype.onitem)
1.  [function <span class="apidocSignatureSpan">up.console.prototype.</span>onsave ()](#apidoc.element.up.console.prototype.onsave)
1.  [function <span class="apidocSignatureSpan">up.console.prototype.</span>progress (item)](#apidoc.element.up.console.prototype.progress)
1.  [function <span class="apidocSignatureSpan">up.console.prototype.</span>update ()](#apidoc.element.up.console.prototype.update)



# <a name="apidoc.module.up"></a>[module up](#apidoc.module.up)

#### <a name="apidoc.element.up.client"></a>[function <span class="apidocSignatureSpan">up.</span>client (opts)](#apidoc.element.up.client)
- description and source-code
```javascript
client = function (opts){
  opts = opts || {};
  opts.useragent = 'cloudup-cli/' + pkg.version;
  if (process.env.UP_API_URL) opts.url = process.env.UP_API_URL;
  if (process.env.UP_CLOUDUP_URL) opts.cloudupUrl = process.env.UP_CLOUDUP_URL;
  return new Cloudup(opts);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.up.console"></a>[function <span class="apidocSignatureSpan">up.</span>console (stream, options)](#apidoc.element.up.console)
- description and source-code
```javascript
function Console(stream, options) {
  this.y = 0;
  this.newlines = 0;
  this.items = [];
  this.cursor = ansi(process.stdout);
  this.stream = stream;
  this.direct = options.direct;
  this.progressOnly = options.progressOnly;

  // bind event listeners to 'this'
  this.onitem = this.onitem.bind(this);
  this.onsave = this.onsave.bind(this);
  this.onend = this.onend.bind(this);

  // attach event listeners to 'stream'
  stream.on('item', this.onitem);
  stream.on('save', this.onsave);
  stream.on('end', this.onend);

  // setup the cursor and global event listeners
  this.cursor.hide();
  var self = this;
  function showCursor(){
    self.cursor.show();
  }
  process.on('uncaughtException', showCursor);
  process.on('uncaughtException', fatal);
  process.on('exit', showCursor);
  process.on('SIGINT', showCursor);
  process.on('SIGINT', process.exit.bind(null, 1));
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.up.readConfig"></a>[function <span class="apidocSignatureSpan">up.</span>readConfig ()](#apidoc.element.up.readConfig)
- description and source-code
```javascript
readConfig = function (){
  var json, obj;

  // read
  try {
    json = fs.readFileSync(exports.configPath, 'utf8');
  } catch (err) {
    console.error('\n  Failed to load configuration.');
    console.error('  Execute: 'up config' to get started!\n');
    process.exit(1);
  }

  // parse
  try {
    obj = JSON.parse(json);
  } catch (err) {
    console.error('\n  Failed to parse ' + exports.configPath + '\n');
    process.exit(1);
  }

  // validate
  if (!(obj.user && obj.token)) {
    console.error('\n  Auth token missing.');
    console.error('  Execute: 'up config' to get a token!\n');
    process.exit(1);
  }

  return obj;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.up.saveConfig"></a>[function <span class="apidocSignatureSpan">up.</span>saveConfig (obj)](#apidoc.element.up.saveConfig)
- description and source-code
```javascript
saveConfig = function (obj){
  var json = JSON.stringify(obj, null, 2) + '\n';
  fs.writeFileSync(exports.configPath, json);
  // chmod the config file to rw for owner only to prevent other users from
  // stealing the token
  fs.chmodSync(exports.configPath, 0600);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.up.console"></a>[module up.console](#apidoc.module.up.console)

#### <a name="apidoc.element.up.console.console"></a>[function <span class="apidocSignatureSpan">up.</span>console (stream, options)](#apidoc.element.up.console.console)
- description and source-code
```javascript
function Console(stream, options) {
  this.y = 0;
  this.newlines = 0;
  this.items = [];
  this.cursor = ansi(process.stdout);
  this.stream = stream;
  this.direct = options.direct;
  this.progressOnly = options.progressOnly;

  // bind event listeners to 'this'
  this.onitem = this.onitem.bind(this);
  this.onsave = this.onsave.bind(this);
  this.onend = this.onend.bind(this);

  // attach event listeners to 'stream'
  stream.on('item', this.onitem);
  stream.on('save', this.onsave);
  stream.on('end', this.onend);

  // setup the cursor and global event listeners
  this.cursor.hide();
  var self = this;
  function showCursor(){
    self.cursor.show();
  }
  process.on('uncaughtException', showCursor);
  process.on('uncaughtException', fatal);
  process.on('exit', showCursor);
  process.on('SIGINT', showCursor);
  process.on('SIGINT', process.exit.bind(null, 1));
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.up.console.prototype"></a>[module up.console.prototype](#apidoc.module.up.console.prototype)

#### <a name="apidoc.element.up.console.prototype.aggregate"></a>[function <span class="apidocSignatureSpan">up.console.prototype.</span>aggregate (item)](#apidoc.element.up.console.prototype.aggregate)
- description and source-code
```javascript
aggregate = function (item){
  var self = this;
  item.progress = 0;
  item.on('progress', function(e){
    item.progress = e.percent;
    self.update();
  });
}
```
- example usage
```shell
...
*
* @api private
*/

Console.prototype.onitem = function(item){
 this.items.push(item);
 if (this.progressOnly) {
   this.aggregate(item);
 } else {
   this.progress(item);
 }
};

/**
* Item aggregate progress.
...
```

#### <a name="apidoc.element.up.console.prototype.log"></a>[function <span class="apidocSignatureSpan">up.console.prototype.</span>log (y, key, str)](#apidoc.element.up.console.prototype.log)
- description and source-code
```javascript
log = function (y, key, str){

  var up = 0;
  var moved = false;
  if (this.cursor.enabled) {
    // first ensure that we've at least written 'y' newlines by now
    while (this.newlines < y) {
      this.cursor.write('\n');
      this.newlines++;
    }

    // at this point, we may need to move the cursor up one or more
    // rows in order to be on the correct 'y' line before writing
    up = this.newlines - y;
    moved = false;
    if (up > 0) {
      moved = true;
      this.cursor.up(up);
    }
  }

  // now that we know we're on the correct 'y' line, output the text
  this.cursor
    .fg.cyan()
    .write(sprintf('%25s', key))
    .fg.reset()
    .write(' : ')
    .fg.brightBlack()
    .write(str)
    .fg.reset()
    .write('\n');

  if (this.cursor.enabled) {
    up--; // subtract from 'up' since we just output a \n
    if (up > 0) {
      this.cursor.down(up);
    }
    if (!moved) {
      // if we didn't call 'cursor.up()' before, then we can increment the \n count
      this.newlines++;
    }
  }
}
```
- example usage
```shell
...
*
* @api private
*/

Console.prototype.update = function(){
 var len = this.items.length;
 var percent = sum(this.items, 'progress') / len | 0;
 this.log(0, len + ' items', percent + '%');
};

/**
* Item progress reporting.
*
* @api private
*/
...
```

#### <a name="apidoc.element.up.console.prototype.onend"></a>[function <span class="apidocSignatureSpan">up.console.prototype.</span>onend ()](#apidoc.element.up.console.prototype.onend)
- description and source-code
```javascript
onend = function (){
  // no-op
  //var y = this.progressOnly ? 2 : this.items.length + 1;
  //this.log(y, 'that\'s all', 'folks!');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.up.console.prototype.onitem"></a>[function <span class="apidocSignatureSpan">up.console.prototype.</span>onitem (item)](#apidoc.element.up.console.prototype.onitem)
- description and source-code
```javascript
onitem = function (item){
  this.items.push(item);
  if (this.progressOnly) {
    this.aggregate(item);
  } else {
    this.progress(item);
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.up.console.prototype.onsave"></a>[function <span class="apidocSignatureSpan">up.console.prototype.</span>onsave ()](#apidoc.element.up.console.prototype.onsave)
- description and source-code
```javascript
onsave = function (){
  var y = this.progressOnly ? 1 : this.items.length;
  this.log(y, 'stream', this.stream.url);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.up.console.prototype.progress"></a>[function <span class="apidocSignatureSpan">up.console.prototype.</span>progress (item)](#apidoc.element.up.console.prototype.progress)
- description and source-code
```javascript
progress = function (item){
  var y = this.y++;
  var self = this;
  var direct = this.direct;
  var cursor = this.cursor;

  function onprogress(e){
    var n = e.percent | 0;
    self.log(y, ctx(item), n + '%');
  }

  function onend(){
    var url = direct ? item.direct_url : item.url;
    self.log(y, ctx(item), url);
  }

  if (cursor.enabled) {
    process.nextTick(function(){
      // fire off a fake 0% event so that the line gets rendered
      item.emit('progress', 0);
    });

    item.on('progress', onprogress);
  }

  item.on('end', onend);
}
```
- example usage
```shell
...
*/

Console.prototype.onitem = function(item){
 this.items.push(item);
 if (this.progressOnly) {
   this.aggregate(item);
 } else {
   this.progress(item);
 }
};

/**
* Item aggregate progress.
*
* @api private
...
```

#### <a name="apidoc.element.up.console.prototype.update"></a>[function <span class="apidocSignatureSpan">up.console.prototype.</span>update ()](#apidoc.element.up.console.prototype.update)
- description and source-code
```javascript
update = function (){
  var len = this.items.length;
  var percent = sum(this.items, 'progress') / len | 0;
  this.log(0, len + ' items', percent + '%');
}
```
- example usage
```shell
...
*/

Console.prototype.aggregate = function(item){
 var self = this;
 item.progress = 0;
 item.on('progress', function(e){
   item.progress = e.percent;
   self.update();
 });
};

/**
* Update aggregate progress.
*
* @api private
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
