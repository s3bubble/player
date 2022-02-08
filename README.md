# S3Bubble Player

```
npm install @s3bubble/player
```

## Setup Globals
```js
window.s3bubbleGlobals = {
    debug: false,
    autoplay: true,
    poweredBy: [{
        href: "https://s3bubble.com",
        label: "Powered by dave.com"
    }, ],
    api: '<api key>',
    locale: 'en',
    poster: 'https://images.pexels.com/photos/8748734/pexels-photo-8748734.jpeg?auto=compress&cs=tinysrgb&dpr=3&h=750&w=1260',
    drm: {
        widevine: {
            keysystem: 'com.widevine.alpha',
            license: 'https://widevine-dash.ezdrm.com/widevine-php/widevine-foreignkey.php?pX=000000'
        },
        fairplay: {
            keysystem: 'com.apple.fps.1_0',
            license: 'https://fps.ezdrm.com/api/licenses/347A5AB7-6A18-4710-0000-86AD80FDB943',
            certificate: 'https://d25hd5yfa00000.cloudfront.net/fairplay.cer'
        },
        playeready: {
            keysystem: 'com.microsoft.playready',
            license: 'https://playready.ezdrm.com/cency/preauth.aspx?pX=000000'
        }
    }
}
```

## DRM Example
```js
s3bubble('<your div>').drm({
    meta: {
        subTitle: '<your sub title>',
        title: '<your title>',
        para: '<your description>',
        showSocial: true,
    },
    widevine: '<your widevine code>',
    playready: '<your playready code>',
    fairplay: '<your fairplay code>',
    assetid: '<your fairplay asset id from ezdrm>',
});
```

## Basic Example
```js
s3bubble('<your div>').video({
    code: '<your code>'
}, function(player) {
    // You can listen to any video events here
    player.on('timeupdate', function(event) {
        console.log('event', player.currentTime());
    });
});
```

## HTML Example

``` html
<div class="s3bv" data-code="<your code>"></div>
```

``` html
<div class="s3bdrm" data-widevine="<your widevine code>" data-playready="<your playready code>" data-fairplay="<your fairplay code>" data-assetid="<your fairplay asset id from ezdrm>"></div>
```