# leaflet-wms-header
Custom headers on Leaflet TileLayer WMS.
It's an easy plugin that allow to set custom header for WMS interface.

It works with javascript and typescript!!!

Based on https://github.com/Leaflet/Leaflet/issues/2091#issuecomment-302706529.

### Javascript
```sh
$ npm install leaflet leaflet-wms-header --save
```

```html
<!-- Assuming your project root is "../" -->
<script src="../node_modules/leaflet/dist/leaflet.js"></script> 
<script src="../node_modules/leaflet-wms-header/index.js"></script> 
```

```js

// YOUR LEAFLET CODE

var wmsLayer = L.TileLayer.wmsHeader(
    'https://GEOSERVER_PATH/geoserver/wms?',
    {
        layers: 'ne:ne',
        format: 'image/png',
        transparent: true,
    },
    [
        { header: 'Authorization', value: 'JWT ' + MYAUTHTOKEN },
        { header: 'content-type', value: 'text/plain'},
    ]
).addTo(map);
```

### Typescript
```sh
$ npm install leaflet @types/leaflet leaflet-wms-header --save
```
```ts
import * as L from 'leaflet';
import 'leaflet-wms-header';

// YOUR LEAFLET CODE

let wmsLayer: L.TileLayer.WMSHeader = L.TileLayer.wmsHeader(
    'https://GEOSERVER_PATH/geoserver/wms?',
    {
        layers: layers,
        format: 'image/png',
        transparent: true,
    }, [
        { header: 'Authorization', value: 'JWT ' + MYAUTHTOKEN },
        { header: 'content-type', value: 'text/plain'},
    ]
).addTo(map);
```