### Reproduction Steps

1. Install dependencies
```bash
yarn
```
2. Run the development debug variant of the Android app
```bash
yarn android --variant developmentDebug
```
3. See the following error in the console
```
Failed to link source maps because the source map URL "index.android.bundle.packager.map" is corrupt: TypeError: Invalid URL
    at new NodeError (node:internal/errors:405:5)
    at new URL (node:internal/url:637:13)
    at Chunk.getAdjustedSourceMapUrl (/Users/thespacemanatee/Documents/GitHub/source-map-repro/node_modules/@expo/metro-config/src/serializer/serializeChunks.ts:335:22)
    at Chunk.serializeToCode (/Users/thespacemanatee/Documents/GitHub/source-map-repro/node_modules/@expo/metro-config/src/serializer/serializeChunks.ts:357:26)
    at Chunk.serializeToAssetsAsync (/Users/thespacemanatee/Documents/GitHub/source-map-repro/node_modules/@expo/metro-config/src/serializer/serializeChunks.ts:386:25)
    at /Users/thespacemanatee/Documents/GitHub/source-map-repro/node_modules/@expo/metro-config/src/serializer/serializeChunks.ts:615:25
    at Array.map (<anonymous>)
    at serializeChunksAsync (/Users/thespacemanatee/Documents/GitHub/source-map-repro/node_modules/@expo/metro-config/src/serializer/serializeChunks.ts:613:17)
    at graphToSerialAssetsAsync (/Users/thespacemanatee/Documents/GitHub/source-map-repro/node_modules/@expo/metro-config/src/serializer/serializeChunks.ts:150:26)
    at /Users/thespacemanatee/Documents/GitHub/source-map-repro/node_modules/@expo/metro-config/src/serializer/withExpoSerializers.ts:263:50 {
  input: '/_expo/static/js/android/AppEntry-c48a6064bd4fa39bfab2eb477ae36e82.js.map',
  code: 'ERR_INVALID_URL'
}
```

The build succeeds in this project but fails in our main proect.