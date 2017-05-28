# 地理院タイル Leaflet 実践編
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
