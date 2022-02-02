# S3Bubble Player

```
npm install @s3bubble/player
```

## DRM Example
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
        backButton: 'yes',
        subTitle: 'Hello World',
        title: 'Title',
        para: 'This is awesome',
        showSocial: true,
    },
    widevine: 'r3eh9b',
    playready: 'r3eh9b',
    fairplay: 'r3ei3d',
    assetid: '8a450047-23f1-4ebe-8b58-9fd82cf6362c',
});
```

## Basic Example
```js
s3bubble('<your div>').video({
    code: 'r5tbwg'
}, function(player) {
    console.log(player);
    player.on('timeupdate', function(event) {
        console.log('event', player.currentTime());
    });
});
```

## HTML Example

``` html
<div class="s3bv" data-code="r5tbwg"></div>
```

``` html
<div class="s3bdrm" data-widevine="r3eh9b" data-playready="r3eh9b" data-fairplay="r3ei3d" data-assetid="8a450047-23f1-4ebe-8b58-9fd82cf6362c"></div>
```