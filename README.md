
# Interactive Video

Add Kaltura video in the Interactive Video Activity.

## Installation
I have created some custom code that needs to be placed in the 'video.js' file in the 'H5P.Video' activity.
```
Previous code :
 if (html5Handler) {
   html5Handler.call(self, sources, options, parameters.l10n);
 }
```
```
Updated Code:
 if (html5Handler) {
  if (sources[0].path.includes("kaltura")) {
    kalturaPath = sources[0].path;
    var splitPath = kalturaPath.split("/");
    var getEntryKey = splitPath[splitPath.length - 1];          
    sources[0].path = `https://www.kaltura.com/p/1660902/sp/0/playManifest/entryId/${getEntryKey}/format/url/flavorParamId/0/video.mp4`;
   }        
   html5Handler.call(self, sources, options, parameters.l10n);
  }
```
Please clone the file and replace it with the existing video.js file or you can directly replace the specific code in the file.

For reference, I have added my video.js file to this repository.