```js
const Map = require('react-leaflet').Map;
const TileLayer = require('react-leaflet').TileLayer;
const Patterns = require('./index.js').default;

<Map center={[47.9, -71.4]} zoom={10} style={{ height: "300px" }}>
  <TileLayer
    attribution="&amp;copy <a href=&quot;http://osm.org/copyright&quot;>OpenStreetMap</a> contributors"
    url="https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png"
  />
  <GeoJSONFillable
    data={{
      type: "FeatureCollection",
      features: [
        {
          type: "Feature",
          properties: {
            style: "stripe",
            name: "Loisirs Lavoie et St-Jean-Baptiste"
          },
          geometry: {
            type: "Polygon",
            coordinates: [
              [
                [-71.729270299794578, 48.010418784700107],
                [-71.291070323784993, 48.004374022337799],
                [-71.291070323784993, 47.777183877693901],
                [-71.729270299794578, 47.786290622064854],
                [-71.729270299794578, 48.010418784700107]
              ]
            ]
          }
        }
      ]
    }}
    style={feature => ({
      color: "orange",
      fillPattern: Patterns.PathPattern({
        d: "M10 0 L7 20 L25 20 Z",
        x: 5,
        y: 5,
        fill: true,
        width: 25,
        height: 25,
        color: "orange",
        key: "path"
      })
    })}
  />
</Map>;


```
