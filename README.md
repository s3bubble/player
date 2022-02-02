# S3Bubble Player

```
npm install @s3bubble/player
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
s3bubble('s3bPlayer').video({
    code: 'r5tbwg'
}, function(player) {
    console.log(player);
    player.on('timeupdate', function(event) {
        console.log('event', player.currentTime());
    });
});
```