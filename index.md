## 北緯35度、東経135度の地図を表示

<iframe width="100%" height="400px" frameborder="0" src="html/35135.html"></iframe>

```html
<!doctype html>
<html>
<head>
<link rel="stylesheet"
  href="//unpkg.com/leaflet@1.0.3/dist/leaflet.css"/>
<style>
  body {padding: 0; margin: 0}
  html, body, #map {height: 100%; width: 100%;}
</style>
<script
  src="//unpkg.com/leaflet@1.0.3/dist/leaflet.js"></script>
</head>
<body>
<div id="map"></div>
<script>
var map = L.map('map').setView([35, 135], 15);
var attr = "<a href='//maps.gsi.go.jp/development/ichiran.html'" +
  "target='_blank'>地理院タイル</a>";
L.tileLayer('//cyberjapandata.gsi.go.jp/xyz/std/{z}/{x}/{y}.png', {
  attribution: attr
}).addTo(map);
</script>
</body>
</html>
```

## 35度135度にマーカーを表示

<iframe width="100%" height="400px" frameborder="0" src="html/marker.html"></iframe>

```html
<!doctype html>
<html>
<head>
<link rel="stylesheet"
  href="//unpkg.com/leaflet@1.0.3/dist/leaflet.css"/>
<style>
  body {padding: 0; margin: 0}
  html, body, #map {height: 100%; width: 100%;}
</style>
<script
  src="//unpkg.com/leaflet@1.0.3/dist/leaflet.js"></script>
</head>
<body>
<div id="map"></div>
<script>
var map = L.map('map').setView([35, 135], 15);
var attr = "<a href='//maps.gsi.go.jp/development/ichiran.html'" +
  "target='_blank'>地理院タイル</a>";
L.tileLayer('//cyberjapandata.gsi.go.jp/xyz/std/{z}/{x}/{y}.png', {
  attribution: attr
}).addTo(map);
L.marker([35, 135]).addTo(map)
  .bindPopup('北緯35度、東経135度')
  .openPopup();
</script>
</body>
</html>
```

## レイヤを切り替え

<iframe width="100%" height="400px" frameborder="0" src="html/layers.html"></iframe>

```html
<!doctype html>
<html>
<head>
<meta charset='utf-8'></meta>
<link rel="stylesheet"
  href="//unpkg.com/leaflet@1.0.3/dist/leaflet.css"/>
<style>
  body {padding: 0; margin: 0}
  html, body, #map {height: 100%; width: 100%;}
</style>
<script
  src="//unpkg.com/leaflet@1.0.3/dist/leaflet.js"></script>
</head>
<body>
<div id="map"></div>
<script>
var map = L.map('map').setView([35, 135], 15);
var attr = "<a href='//maps.gsi.go.jp/development/ichiran.html'" +
  "target='_blank'>地理院タイル</a>";
L.tileLayer('//cyberjapandata.gsi.go.jp/xyz/std/{z}/{x}/{y}.png', {
  attribution: attr
}).addTo(map);
L.control.layers({
  '標準地図': L.tileLayer(
    '//cyberjapandata.gsi.go.jp/xyz/std/{z}/{x}/{y}.png',
    {attribution: attr}),
  '淡色地図': L.tileLayer(
    '//cyberjapandata.gsi.go.jp/xyz/pale/{z}/{x}/{y}.png',
    {attribution: attr}),
  '色別標高図': L.tileLayer(
    '//cyberjapandata.gsi.go.jp/xyz/relief/{z}/{x}/{y}.png',
    {attribution: attr, maxNativeZoom: 15}),
  '傾斜量図': L.tileLayer(
    '//cyberjapandata.gsi.go.jp/xyz/slopemap/{z}/{x}/{y}.png',
    {attribution: attr, maxNativeZoom: 15}),
  'シームレス空中写真': L.tileLayer(
    '//cyberjapandata.gsi.go.jp/xyz/seamlessphoto/{z}/{x}/{y}.jpg',
    {attribution: attr}),
}, {}).addTo(map);
</script>
</body>
</html>
```
