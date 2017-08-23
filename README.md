## Welcome

This is a fork of Atomizer's [Muledump](https://github.com/atomizer) made to address the required changes since the most recent upstream release.

##  Important Changes from Upstream Muledump

Muledump has traditionally used Yahoo's YQL service to process account data. This no longer working as Deca rate limits IPs blocking those requests.

This version of Muledump removes YQL and replaces it with the less graceful direct request.

#### Why is this "less graceful"?

In a nutshell, browsers don't like it when a website requests a URL to another website via Javascript. Yahoo YQL explicitly approves this sort of request, so it is fine. But ROTMG's servers do not.

In order to use this version of Muledump you need to be using Chrome with [this extension](https://chrome.google.com/webstore/detail/allow-control-allow-origi/nlfbmbojpeacfghkpbjhddihlkkiljbi) to disable CORS. This extension when enabled will disable this security feature to enable Muledump to work. 

Just remember to turn it off when not using Muledump!

## Account Load Rate Limiting

Deca servers will now block you for 10 minutes if you make too many requests at once. Users with many accounts are finding themselves unable to use Muledump because of this.

This version of Muledump now rate limits how fast you hit Deca's servers in an attempt to prevent you getting blocked. You can fine-tune this setting by adding/changing in accounts.js:

```
accountLoadDelay = 5
```

In this example, and by default, there is a 5-second delay between loading each account.

## Synopsis

This tool allows you to list contents of all your accounts in a single page (characters, their stats and items, items in vaults). Also it generates a summary of all the items - you probably saw screenshots of these in trading forum ([example](http://i755.photobucket.com/albums/xx195/Ind3sisiv3/Ilovemuledump.png)).

The point of playing the game is to have fun. Muling is not fun. I am trying to increase overall fun ratio by decreasing amount of time spent fussing with mules and storagekeeping.

## Download

All released versions are [here](https://github.com/jakcodex/muledump/releases).

## Howto

- unpack
- edit **`accounts_sample.js`**
- rename it to **`accounts.js`**
- add chrome extension **[Allow-Control-Allow-Origin: *](https://chrome.google.com/webstore/detail/allow-control-allow-origi/nlfbmbojpeacfghkpbjhddihlkkiljbi)**
- open **`muledump.html`**

## Not so obvious features

- click on item to filter accounts that hold it
- click on account name for individual options menu
- ctrl-click account name to temporarily hide it from totals
- read the `accounts.js` file, it has some variables to play with

## Head to the [wiki](https://github.com/atomizer/muledump/wiki) for more information!

And of course, feel free to contribute to it!

## License

Copyright (c) 2013 [atomizer](https://github.com/atomizer)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
