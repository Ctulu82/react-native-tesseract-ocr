# react-native-tesseract-ocr [![npm version](https://badge.fury.io/js/react-native-tesseract-ocr.svg)](https://badge.fury.io/js/react-native-tesseract-ocr)

react-native-tesseract-ocr is a react-native wrapper for [Tesseract OCR](https://github.com/tesseract-ocr) using base on
  - [tess-two](https://github.com/rmtheis/tess-two) for Android
  - [Tesseract-OCR-iOS](https://github.com/gali8/Tesseract-OCR-iOS) for iOS *(Not implemented yet)*

## Getting started

`$ yarn add https://github.com/ducnmisbk/react-native-tesseract-ocr.git` 

### Mostly automatic installation

`$ react-native link react-native-tesseract-ocr`

*Don't forget to ...*
- *add [v3.04 trained data files](https://github.com/tesseract-ocr/tessdata/tree/3.04.00) to the appropriate folder*
- *install [CocoaPods](https://cocoapods.org/) in your react-native project and add the following line to your Podfile then run `pod install` __(iOS only)__*
   ```
   pod 'TesseractOCRiOS', '4.0.0'
   pod 'GPUImage', '0.1.7'
   ```
- *disable bitcode*
- *add libz.tbd in target app -> Link Binary With Libraries*

## Usage
```javascript
import RNTesseractOcr from 'react-native-tesseract-ocr';


/**
 * @param {string} imgPath - The path of the image.
 * @param {string} lang - The language you want to process.
 * @param {object} tessOptions - Tesseract options.
 */
 const tessOptions = {
  whitelist: null, 
  blacklist: '1234567890\'!"#$%&/()={}[]+*-_:;<>'
};
RNTesseractOcr.recognize(imgPath, lang, tessOptions)
  .then((result) => {
    this.setState({ ocrResult: result });
    console.log("OCR Result: ", result);
  })
  .catch((err) => {
    console.log("OCR Error: ", err);
  })
  .done();

```

*NOTE: The method _startOcr_ is deprecated. Instead, use _recognize_*


### Supported languages
  - LANG_AFRIKAANS
  - LANG_AMHARIC
  - LANG_ARABIC
  - LANG_ASSAMESE
  - LANG_AZERBAIJANI
  - LANG_BELARUSIAN
  - LANG_BOSNIAN
  - LANG_BULGARIAN
  - LANG_CHINESE_SIMPLIFIED
  - LANG_CHINESE_TRADITIONAL
  - LANG_CROATIAN
  - LANG_DANISH
  - LANG_ENGLISH
  - LANG_ESTONIAN
  - LANG_FRENCH
  - LANG_GALICIAN
  - LANG_GERMAN
  - LANG_HEBREW
  - LANG_HUNGARIAN
  - LANG_ICELANDIC
  - LANG_INDONESIAN
  - LANG_IRISH
  - LANG_ITALIAN
  - LANG_JAPANESE
  - LANG_KOREAN
  - LANG_LATIN
  - LANG_LITHUANIAN
  - LANG_NEPALI
  - LANG_NORWEGIAN
  - LANG_PERSIAN
  - LANG_POLISH
  - LANG_PORTUGUESE
  - LANG_RUSSIAN
  - LANG_SERBIAN
  - LANG_SLOVAK
  - LANG_SPANISH
  - LANG_SWEDISH
  - LANG_TURKISH
  - LANG_UKRAINIAN
  - LANG_VIETNAMESE

### If you want to use your own trained data file
  - LANG_CUSTOM
 
 *Locate your own trained data file as `custom.traineddata` into `android/app/src/main/assets/tessdata`.*

## Contribution
Contributions are welcome :raised_hands:

## License
This repository is distributed under [MIT license](https://github.com/jonathanpalma/react-native-tesseract-ocr/blob/master/LICENSE) 
 - [Tesseract OCR](https://github.com/tesseract-ocr) - maintained by Google, is distributed under [Apache 2.0 license](http://www.apache.org/licenses/LICENSE-2.0)
 - [tess-two](https://github.com/rmtheis/tess-two) is distributed under [Apache 2.0 license](https://github.com/rmtheis/tess-two/blob/master/COPYING)
 - [Tesseract-OCR-iOS](https://github.com/gali8/Tesseract-OCR-iOS) is distributed under [MIT license](https://github.com/gali8/Tesseract-OCR-iOS/blob/master/LICENSE.md)
 
