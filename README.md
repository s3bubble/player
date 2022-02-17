# S3Bubble Player

![S3Bubble Player](https://s3b-assets-bucket.s3.amazonaws.com/screenshot_2022_02_16_at_18.43.50.png)

```
npm install @s3bubble/player
```

## Setup Globals - Player Options Will Override DRM Globals 
```js
window.s3bubbleGlobals = {
    debug: false,
    autoplay: true,
    poweredBy: [{
        href: "https://s3bubble.com",
        label: "Powered by s3bubble.com"
    }, ],
    api: '<api key>',
    locale: 'en', 
    poster: 'https://images.pexels.com/photos/8748734/pexels-photo-8748734.jpeg?auto=compress&cs=tinysrgb&dpr=3&h=750&w=1260',
    drm: {
        widevine: {
            keysystem: 'com.widevine.alpha',
            license: 'https://<license>?pX=000000'
        },
        fairplay: {
            keysystem: 'com.apple.fps.1_0',
            license: 'https://<license>.com',
            certificate: 'https://d25hd5yfa00000.cloudfront.net/fairplay.cer'
        },
        playeready: {
            keysystem: 'com.microsoft.playready',
            license: 'https://<license>?pX=000000'
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
    tracks: [
        {
            src: '/captions/it.vtt',
            kind: 'captions',
            srclang: 'it',
            label: 'Italian'
        },
        {
            src: '/captions/fr.vtt',
            kind: 'captions',
            srclang: 'fr',
            label: 'French',
            default: true
        },
        {
            src: '/captions/chapters.vtt',
            kind: 'chapters',
            srclang: 'de',
            label: 'German'
        }
    ],
    drm: {
        authenticationXml: '<authenticationXml BuyDRM only>',
        widevine: {
            code: '<your widevine code>',
            keysystem: 'com.widevine.alpha',
            license: 'https://<license>.com'
        },
        playready: {
            code: '<your playready code>',
            keysystem: 'com.microsoft.playready',
            license: 'https://<license>/rightsmanager.asmx'
        },
        fairplay: {
            code: '<your fairplay code>',
            keysystem: 'com.apple.fps.1_0',
            assetid: '<assetid EZDRM only>',
            license: 'https://<license>/getkey',
            certificate: 'https://000000.cloudfront.net/fairplay.cer'
        },
    }
}, function(player) {
    // You can listen to any video events here
    player.on('timeupdate', function(event) {
        console.log('event', player.currentTime());
    });
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

## Video Example
[open demo](https://s3bubble.com/documentation/example-ezdrm-widevine-fairplay-playready-dash-hls)