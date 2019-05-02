![Video.js logo][logo]

# [Video.js - HTML5 Video Player][vjs]

[![Build Status][travis-icon]][travis-link]
[![Coverage Status][coveralls-icon]][coveralls-link]
[![Greenkeeper badge](https://badges.greenkeeper.io/videojs/video.js.svg)](https://greenkeeper.io/)
[![Slack Status][slack-icon]][slack-link]

[![NPM][npm-icon]][npm-link]

> Video.js is a web video player built from the ground up for an HTML5 world. It supports HTML5 and Flash video, 
as well as YouTube and Vimeo (through [plugins][plugins]). It supports video playback on desktops and mobile devices. 
This project was started mid 2010, and the player is now used on over ~~50,000~~ ~~100,000~~ ~~200,000~~ [400,000 websites][builtwith].
Video.js是一个基于HTML5世界的web视频播放器。
它支持HTML5和Flash视频，以及YouTube和Vimeo。
它支持桌面和移动设备上的视频播放。
该项目于2010年年中启动，目前玩家使用在~~5万~~ ~10万~~ ~20万~~ ~。
## Table of Contents

* [Quick Start](#quick-start)
* [Contributing](#contributing)
* [Code of Conduct](#code-of-conduct)行为规范
* [License](#license)

## Quick Start

Thanks to the awesome folks over at [Fastly][fastly], there's a free, CDN hosted version of Video.js that anyone can use. 
Add these tags to your document's `<head>`:

```html
<link href="//vjs.zencdn.net/6.10/video-js.min.css" rel="stylesheet">
<script src="//vjs.zencdn.net/6.10/video.min.js"></script>
```
> For the latest version of video.js and URLs to use, check out the [Getting Started][getting-started] page on our website.

> In the `vjs.zencdn.net` CDN-hosted versions of Video.js we include a 
[stripped down Google Analytics pixel](https://github.com/videojs/cdn/blob/master/src/analytics.js) 
that tracks a random sampling (currently 1%) of players loaded from the CDN. This allows us to see (roughly) 
what browsers are in use in the wild, along with other useful metrics such as OS and device. 
If you'd like to disable analytics, you can simply include the following global 
before including Video.js via the free CDN:
>
> ```html
> <script>window.HELP_IMPROVE_VIDEOJS = false;</script>
> ```
> Alternatively, you can include Video.js by getting it from [npm](http://videojs.com/getting-started/#download-npm), 
downloading from [GitHub releases](https://github.com/videojs/video.js/releases) or by including it via 
[unpkg](https://unpkg.com) or another JavaScript CDN like CDNjs. These releases *do not* include Google Analytics tracking at all.
> ```html
> <!-- unpkg -->
> <link href="https://unpkg.com/video.js/dist/video-js.css" rel="stylesheet">
> <script src="https://unpkg.com/video.js/dist/video.js"></script>
>
> <!-- cdnjs -->
> <link href="https://cdnjs.cloudflare.com/ajax/libs/video.js/6.3.3/video-js.css" rel="stylesheet">
> <script src="https://cdnjs.cloudflare.com/ajax/libs/video.js/6.3.3/video.js"></script>
> ```

Next, using Video.js is as simple as creating a `<video>` element, but with an additional `data-setup` attribute. 
At a minimum, this attribute must have a value of `'{}'`, but it can include any Video.js [options][options] - just make sure it contains valid JSON!

```html
<video
    id="my-player"
    class="video-js"
    controls
    preload="auto"
    poster="//vjs.zencdn.net/v/oceans.png"
    data-setup='{}'>
  <source src="//vjs.zencdn.net/v/oceans.mp4" type="video/mp4"></source>
  <source src="//vjs.zencdn.net/v/oceans.webm" type="video/webm"></source>
  <source src="//vjs.zencdn.net/v/oceans.ogv" type="video/ogg"></source>
  <p class="vjs-no-js">
    To view this video please enable JavaScript, and consider upgrading to a
    web browser that
    <a href="http://videojs.com/html5-video-support/" target="_blank">
      supports HTML5 video
    </a>
  </p>
</video>
```

When the page loads, Video.js will find this element and automatically setup a player in its place.
当页面加载时，Video.js会找到这个元素，并自动设置一个播放器在它的位置。
If you don't want to use automatic setup, you can leave off the `data-setup` attribute and initialize a `<video>` element manually using the `videojs` function:
如果不想使用自动设置，可以关闭“data-setup”属性，使用“videojs”函数手动初始化`<video>`

```js
var player = videojs('my-player');
```

The `videojs` function also accepts an `options` object and a callback to be invoked
 when the player is ready:

```js
var options = {};

var player = videojs('my-player', options, function onPlayerReady() {
  videojs.log('Your player is ready!');

  // In this context, `this` is the player that was created by Video.js.
  this.play();

  // How about an event listener?
  this.on('ended', function() {
    videojs.log('Awww...over so soon?!');
  });
});
```

If you're ready to dive in, the [Getting Started][getting-started] page and [documentation][docs] are the best places to go for more information. 
If you get stuck, head over to our [Slack channel][slack-link]!
如果您已经准备好了，那么入门页面和文档是获取更多信息的最佳位置。如果你被困住了，就去我们的放松频道!

## Contributing

Video.js is a free and open source library, and we appreciate any help you're willing to give - whether it's fixing bugs, 
improving documentation, or suggesting new features. Check out the [contributing guide][contributing] for more!
Video.js是一个免费的开源库，我们非常感谢您愿意提供的任何帮助——无论是修复bug，改进文档，或建议新特性。查看更多的贡献!

_Video.js uses [BrowserStack][browserstack] for compatibility testing._
Video.js使用BrowserStack进行兼容性测试

## [Code of Conduct][coc] 行为规范

Please note that this project is released with a [Contributor Code of Conduct][coc]. 
By participating in this project you agree to abide by its terms.
请注意这个项目使用了一个行为规范来发布。通过参与这个项目，你同意遵守它的条款。


## [License][license]

Video.js is [licensed][license] under the Apache License, Version 2.0.

[browserstack]: https://browserstack.com

[builtwith]: https://trends.builtwith.com/media/VideoJS

[contributing]: CONTRIBUTING.md

[coveralls-icon]: https://coveralls.io/repos/github/videojs/video.js/badge.svg?branch=master

[coveralls-link]: https://coveralls.io/github/videojs/video.js?branch=master

[docs]: http://docs.videojs.com

[fastly]: http://www.fastly.com/

[getting-started]: http://videojs.com/getting-started/

[license]: LICENSE

[logo]: http://videojs.com/img/logo.png

[npm-icon]: https://nodei.co/npm/video.js.png?downloads=true&downloadRank=true

[npm-link]: https://nodei.co/npm/video.js/

[options]: docs/guides/options.md

[plugins]: http://videojs.com/plugins/

[slack-icon]: http://slack.videojs.com/badge.svg

[slack-link]: http://slack.videojs.com

[travis-icon]: https://travis-ci.org/videojs/video.js.svg?branch=6.x

[travis-link]: https://travis-ci.org/videojs/video.js

[vjs]: http://videojs.com

[coc]: CODE_OF_CONDUCT.md
