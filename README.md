# Map1
primer mapa web
<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8' />
    <title>Display a map</title>
    <meta name='viewport' content='initial-scale=1,maximum-scale=1,user-scalable=no' />
    <script src='https://api.tiles.mapbox.com/mapbox-gl-js/v1.4.0/mapbox-gl.js'></script>
    <link href='https://api.tiles.mapbox.com/mapbox-gl-js/v1.4.0/mapbox-gl.css' rel='stylesheet' />
    <style>
        body { margin:0; padding:0; }
        #map { position:absolute; top:0; bottom:0; width:100%; }
    </style>
</head>
<body>
<style>
#menu {
background: #fff;
position: absolute;
z-index: 1;
top: 10px;
right: 10px;
border-radius: 3px;
width: 120px;
border: 1px solid rgba(0,0,0,0.4);
font-family: 'Open Sans', sans-serif;
}

#menu a {
font-size: 13px;
color: #404040;
display: block;
margin: 0;
padding: 0;
padding: 10px;
text-decoration: none;
border-bottom: 1px solid rgba(0,0,0,0.25);
text-align: center;
}

#menu a:last-child {
border: none;
}

#menu a:hover {
background-color: #f8f8f8;
color: #404040;
}

#menu a.active {
background-color: #3887be;
color: #ffffff;
}

#menu a.active:hover {
background: #3074a4;
}
</style>


<nav id='menu'></nav>
<div id='map'></div>
<script>
mapboxgl.accessToken = 'pk.eyJ1IjoiZnJhbmlzY28iLCJhIjoiY2o1dmNiMXNpMDBnbTJ3bXgzdGswaGFjMiJ9.artmfOu4BiUb7UaNpJ7peA';
var map = new mapboxgl.Map({
    container: 'map', // container id
    style: 'mapbox://styles/franisco/ck3ubkq4z0pwb1cnyn6zhywrf', // stylesheet location
    center: [-84.8419189453125, 12.913552398609209], // starting position [lng, lat]
    zoom: 6 // zoom level
});

var toggleableLayerIds = [ 'healthcare facilities', 'kindergarden' ];

for (var i = 0; i < toggleableLayerIds.length; i++) {
var id = toggleableLayerIds[i];

var link = document.createElement('a');
link.href = '#';
link.className = 'active';
link.textContent = id;

link.onclick = function (e) {
var clickedLayer = this.textContent;
e.preventDefault();
e.stopPropagation();

var visibility = map.getLayoutProperty(clickedLayer, 'visibility');

if (visibility === 'visible' || visibility === undefined) {
map.setLayoutProperty(clickedLayer, 'visibility', 'none');
this.className = '';
} else {
this.className = 'active';
map.setLayoutProperty(clickedLayer, 'visibility', 'visible');
}
};

var layers = document.getElementById('menu');
layers.appendChild(link);
}


</script>

</body>
</html>

<style>
#menu {
background: #fff;
position: absolute;
z-index: 1;
top: 10px;
right: 10px;
border-radius: 3px;
width: 120px;
border: 1px solid rgba(0,0,0,0.4);
font-family: 'Open Sans', sans-serif;
}

#menu a {
font-size: 13px;
color: #404040;
display: block;
margin: 0;
padding: 0;
padding: 10px;
text-decoration: none;
border-bottom: 1px solid rgba(0,0,0,0.25);
text-align: center;
}

#menu a:last-child {
border: none;
}

#menu a:hover {
background-color: #f8f8f8;
color: #404040;
}

#menu a.active {
background-color: #3887be;
color: #ffffff;
}

#menu a.active:hover {
background: #3074a4;
}
</style>

var toggleableLayerIds = [ 'Healthcare Facilities', 'Kindergarten' ];

for (var i = 0; i < toggleableLayerIds.length; i++) {
var id = toggleableLayerIds[i];

var link = document.createElement('a');
link.href = '#';
link.className = 'active';
link.textContent = id;

link.onclick = function (e) {
var clickedLayer = this.textContent;
e.preventDefault();
e.stopPropagation();

var visibility = map.getLayoutProperty(clickedLayer, 'visibility');

if (visibility === 'visible' || visibility === undefined) {
map.setLayoutProperty(clickedLayer, 'visibility', 'none');
this.className = '';
} else {
this.className = 'active';
map.setLayoutProperty(clickedLayer, 'visibility', 'visible');
}
};

var layers = document.getElementById('menu');
layers.appendChild(link);
}
