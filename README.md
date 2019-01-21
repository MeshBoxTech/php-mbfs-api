MBFS API wrapper library in PHP
======================================

> A client library for the MBFS API.

# Usage

## Installing

This library requires the cURL module:

```bash
$ sudo apt-get install php5-curl
$ composer require meshboxfoundation/php-mbfs-api
$ composer install
```

```PHP
use Cloutier\PhpIpfsApi\MBFS;

// connect to mbfs daemon API server
$mbfs = new MBFS("localhost", "8080", "5001"); // leaving out the arguments will default to these values

```


## API


#### add

Adds content to MBFS.

**Usage**
```PHP
$hash = $mbfs->add("Hi, I'm Vingo! Welcome to use MBFS!");
```



#### cat

Retrieves the contents of a single hash.

**Usage**
```PHP
$mbfs->cat($hash);
```

#### ls
Gets the node structure of a hash.

**Usage**
```PHP
$obj = $mbfs->ls($hash);

foreach ($obj as $e) {
	echo $e['Hash'];
	echo $e['Size'];
	echo $e['Name'];
}
```


#### Object size

Returns object size.

**Usage**
```PHP
$size = $mbfs->size($hash);
```

#### Pin

Pins a hash.

**Usage**
```PHP
$mbfs->pinAdd($hash);
```

# License

The MIT License (MIT)

Copyright (c) 2019-2026 Vingo MBFoundation
Copyright (c) 2019 MeshBox Technologies

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
