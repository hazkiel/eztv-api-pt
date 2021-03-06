# eztv-api-pt

[![Build Status](https://travis-ci.org/ChrisAlderson/eztv-api-pt.svg?branch=master)]()
[![Dependency Status](https://david-dm.org/ChrisAlderson/eztv-api-pt.svg)](https://david-dm.org/ChrisAlderson/eztv-api-pt)
[![devDependency Status](https://david-dm.org/ChrisAlderson/eztv-api-pt/dev-status.svg)](https://david-dm.org/ChrisAlderson/eztv-api-pt#info=devDependencies)

An EZTV API wrapper to get data from [eztv.ag](https://eztv.ag/).

## Usage

#### Setup
```
npm install --save eztv-api-pt
```

#### Initialize
```js
const EZTV = require('eztv-api-pt');

// Options are the request default options.
let eztv = new EZTV({[options, debug]});
```

#### Example usage
```js
// Get all available shows on eztv.
eztv.getAllShows().then(res => {
  const data = res[0];
  console.log(data);

  // Get data including episodes from eztv.
  eztv.getShowData(data).then(res => console.log(res));
}).catch(err => console.error(err));
```

## Output

#### getAllShows
```js
[{
    show: "10 O\"Clock Live",
    id: "449",
    slug: "10-o-clock-live"
  }, {
    show: "10 Things I Hate About You",
    id: "308",
    slug: "10-things-i-hate-about-you"
  },
  ...
]
```

#### getShowData
```js
{ show: "10 O\'Clock Live",
  id: "449",
  slug: "tt1811399",
  episodes:
   { "1":
      { "1":
         { "480p":
            { url: "magnet:?xt=urn:btih:LMJXHHNOW33Z3YGXJLCTJZ23WK2D6VO4&dn=10.OClock.Live.S01E01.WS.PDTV.XviD-PVR&tr=udp://tracker.openbittorrent.com:80&tr=udp://open.demonii.com:80&tr=udp://tracker.coppersurfer.tk:80&tr=udp://tracker.leechers-paradise.org:6969&tr=udp://exodus.desync.com:6969",
              seeds: 0,
              peers: 0,
              provider: "EZTV" } },
        ...
      }
    }
}
```

Nested within the `episodes` property there is the `season number`
within the `season number` is the `episode number` and within the `episode number` are the different `qualities` of the torrent.

# License

MIT License

Copyright (c) 2016 - eztv-api-pt - Released under the MIT license.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
