# Upgrade Guide

## Migrating from react-map-gl

### Update Imports

`@vis.gl/react-maplibre` v1.0 can be used as a drop-in replacement of `react-map-gl` v7:

```patch
- import {Map, Marker} from 'react-map-gl/maplibre';
+ import {Map, Marker} from '@vis.gl/react-maplibre';
```

### Remove Mapbox-only Props

The following Mapbox-only props from `react-map-gl`'s Map component are removed:

- `mapboxAccessToken`
- `workerClass`
- `baseApiUrl`

### Explicitly set `RTLTextPlugin` (if needed)

The default `RTLTextPlugin` loaded from mapbox.com has been removed.
To keep the previous behavior, specify the `pluginUrl` which was previously used or supply the plugin from any other source:

```tsx
<Map
  RTLTextPlugin={{
    pluginUrl:
      'https://api.mapbox.com/mapbox-gl-js/plugins/mapbox-gl-rtl-text/v0.2.3/mapbox-gl-rtl-text.js'
  }}
/>
```
