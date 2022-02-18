# S3Bubble Player

![S3Bubble Player](https://s3b-assets-bucket.s3.amazonaws.com/screenshot_2022_02_16_at_18.43.50.png)

```
npm install @s3bubble/player
```
## BuyDRM Example - [Open Website](https://buydrm.com)
```js
s3bubble('<div>').drm({
    drm: {
        authenticationXml: '<authenticationXml>',
        widevine: {
            code: '<widevine code>',
            keysystem: 'com.widevine.alpha',
            license: 'https://wv-keyos.licensekeyserver.com/'
        },
        playready: {
            code: '<playready code>',
            keysystem: 'com.microsoft.playready',
            license: 'https://pr-keyos.licensekeyserver.com/core/rightsmanager.asmx'
        },
        fairplay: {
            code: '<fairplay code>',
            keysystem: 'com.apple.fps.1_0',
            license: 'https://fp-keyos.licensekeyserver.com/getkey',
            certificate: 'https://00000000000.cloudfront.net/fairplay.cer'
        },
    }
});
```
## EZDRM Example - [Open Website](https://www.ezdrm.com)
```js
s3bubble('<div>').drm({
    drm: {
        widevine: {
            code: '<widevine code>',
            keysystem: 'com.widevine.alpha',
            license: 'https://widevine-dash.ezdrm.com/widevine-php/widevine-foreignkey.php?pX=000000'
        },
        playready: {
            code: '<playready code>',
            keysystem: 'com.microsoft.playready',
            license: 'https://playready.ezdrm.com/cency/preauth.aspx?pX=000000'
        },
        fairplay: {
            code: '<fairplay code>',
            keysystem: 'com.apple.fps.1_0',
            assetid: '8a450047-23f1-0000-8b58-9fd82cf6362c',
            certificate: 'https://00000000000.cloudfront.net/fairplay.cer'
        },
    }
});
```
## Extra DRM Example
```js
s3bubble('<div>').drm({
    meta: {
        subTitle: '<sub title>',
        title: '<title>',
        para: '<description>',
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
            code: '<widevine code>',
            keysystem: 'com.widevine.alpha',
            license: 'https://<license>.com'
        },
        playready: {
            code: '<playready code>',
            keysystem: 'com.microsoft.playready',
            license: 'https://<license>/rightsmanager.asmx'
        },
        fairplay: {
            code: '<fairplay code>',
            keysystem: 'com.apple.fps.1_0',
            assetid: '<assetid EZDRM only>',
            license: 'https://<license>/getkey',
            certificate: 'https://00000000000.cloudfront.net/fairplay.cer'
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
s3bubble('<div>').video({
    code: '<code>'
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
    poster: 'https://images.pexels.com/photos/8748734/pexels-photo-8748734.jpeg',
    drm: {
        widevine: {
            keysystem: 'com.widevine.alpha',
            license: 'https://<license>?pX=000000'
        },
        fairplay: {
            keysystem: 'com.apple.fps.1_0',
            license: 'https://<license>.com',
            certificate: 'https://00000000000.cloudfront.net/fairplay.cer'
        },
        playeready: {
            keysystem: 'com.microsoft.playready',
            license: 'https://<license>?pX=000000'
        }
    }
}
```
## Video Example
[open demo](https://s3bubble.com/documentation/example-ezdrm-widevine-fairplay-playready-dash-hls)