JPEGLosslessDecoderJS
=====
A common DICOM compression format is JPEG Lossless.  This format is generally not supported in standard JPEG decoder libraries. 

This decoder can read data from the following DICOM transfer syntaxes:

- 1.2.840.10008.1.2.4.57    JPEG Lossless, Nonhierarchical (Processes 14)
- 1.2.840.10008.1.2.4.70    JPEG Lossless, Nonhierarchical (Processes 14 [Selection 1])

###Usage
See tests/driver.js to run this example:

```javascript
var decoder = new jpeg.lossless.Decoder(compressedBytes);  // optional second parameter to specify 1 or 2 byte output
var decompressedData = decoder.decode();
```

###Testing
```
npm test
```

###Building
See the [release folder](https://github.com/rii-mango/JPEGLosslessDecoderJS/tree/master/release) for the latest builds or build it yourself using:
```
npm run build
```
This will output lossless.js and lossless-min.js to build/.

###Bower

This library is distributed via [bower](http://bower.io/) under the name jpeg-lossless-decoder-js.  Bower utilizes git's
tagging mechanism to manage versions.  Each time a new version is released, the version should be tagged using git
so it can be found by bower. After a new version is released and pushed to github, you can do the following:

# tag the current head with a version number (e.g. 1.0.0)

> git tag -a 1.0.0 -m "Version 1.0.0"

# push the tags to github

> git push origin master --tags

###Acknowledgments
This decoder was originally written by Helmut Dersch for Java, later released by [JNode](https://github.com/jnode/jnode).  I added support for selection values 2 to 7 and ported to JavaScript.

