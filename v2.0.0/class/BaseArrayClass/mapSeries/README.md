# baseArrayClass.mapAsync(fn, callback)

<img src="./mapSeries.png" width="500">

```js

var baseArray = new plugin.google.maps.BaseArrayClass([
  {placeId: "ChIJN1t_tDeuEmsRUsoyG83frY4"},
  {placeId: "ChIJyWEHuEmuEmsRm9hTkapTCrk"},
  {placeId: "ChIJLfySpTOuEmsRsc_JfJtljdc"}
]);

var idx = 0;
baseArray.mapSeries(function(placeData, next) {

  // example: Obtain data from your server
  getInfomationFromDB(placeData, function(latLng) {

    map.addMarker({
      "position": latLng,
      "idx": (idx++)
    }, next);

  });

}, function(markers) {

  // markers[0] ... markers[n]

});

```
