![nails-framework](https://f.cloud.github.com/assets/1144357/2225403/4529567e-9a8d-11e3-80a4-23ba637b5f26.png)

# nails-scraper
*Scraper service for [nails-framework](http://ghub.io/nails-framework)*

Powered by [cheerio](https://ghub.io/cheerio).

## Install
```bash
$ npm install --save nails-scraper
```

## Defining Models
```javascript
// Load the plugin before calling app.start()
app.plugin('nails-scraper');

// Use the service
var scraper = app.service.get('scraper');
var request = app.service.get('request');

// Grab the Apple homepage and extract the copyright text
request.get('http://www.apple.com', function(err, response, body) {
  var $ = scraper(body);
  var copyright = $('p.copyright');
});
```

Most methods from jQuery are available.

See the [cheerio documentation](https://ghub.io/cheerio) for more information.

## Licence

The MIT License (MIT)

Copyright (c) 2014 James Wyse <james@jameswyse.net>

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
