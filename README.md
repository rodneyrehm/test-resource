# Test Resource #

provides a dynamic resource required for testing resource handling:

* Delay responses
* Overwrite `Content-Type` header
* Define charset / encoding
* Define response status and message
* Relocate (after possible delay) to another resource

## W3C Test Framework ##

The test-resource is available at [http://w3c-test.org/delay/](http://w3c-test.org/delay/) and [http://test.csswg.org/delay/](http://test.csswg.org/delay/) (also via HTTPS at both locations).

## Usage ##

Send a `GET` or `POST` request to `test-resource.php` - see parameters listed below.

Required Parameters:

* **type** (`type=help`) - the type of content to return, currently supports:
  * `gif` - returning a proper 1x1 pixel GIF image
  * `svg` - returning a proper SVG image
  * `html` - returning proper HTML
  * `css` - returning proper CSS
  * `js` - retuning proper JavaScript
  * `json` - returning proper JSON data

Optional Parameters:

* **delay** (`delay=1000`) - delay response for 1000ms
* **status** (`status=404`) - http response code
* **message** (`message=Not+Found`) - http response message
* **content-type** (`content-type=text%2Fhtml`) - overwrite default mime types
* **relocate** `relocate=http%3A%2F%2Fexample.com%2F` - relocate to given URL (overwrites code=302, message=Moved+Temporarily)
* **charset** (`charset=UTF-8`) - have non-binary output encoded to specific encoding (e.g. `ISO-8859-1` or `UTF-16BE` see [mb_list_encodings()](http://php.net/manual/en/function.mb-list-encodings.php#example-2615) for more)

Example: `test-resource.php?type=js&delay=500&status=404&message=Not+Found`


## License ##

This software is distributed under the following licenses, choose whatever suits you best:

* [W3C® Software License](http://www.w3.org/Consortium/Legal/2002/copyright-software-20021231)
* [MIT License](http://opensource.org/licenses/mit-license)


## Changelog ##

### 1.0.0 (January 24th 2013) ###

* initial release


## Alternate Solutions ##

* [hang (webservice)](http://hang.nodester.com/) - [hang (source)](https://github.com/remy/hang) - JavaScript / Node.js

