# ImageBase64Encoder
Encode an image into a base64 String. Why?, you may ask. In order to upload an image from Android to a server, you cannot just send a physical image file. Instead, you need to encode it into a base64 String first. And when it reaches a web server, you can decode it back to an image, and lastly save it onto a hard disk.

# How to Use
### ``EncodeResource()`` method
Encode a resource image file into a base64 String. 
```java
String encodedRes = ImageBase64
                .with(getApplicationContext())
                .requestSize(512, 512)
                .encodeResource(R.drawable.angkorwat);
```
### ``EncodeFile()`` method
Encode a file into a base64 String.
```java
try {
    String encodedImage = ImageBase64
                      .with(getApplicationContext())
                      .requestSize(512, 512)
                      .encodeFile("/storage/emulated/0/some image file.jpeg");
} catch (FileNotFoundException e) {
    e.printStackTrace();
}
```

### ``requestSize(width, height)`` method
You can request the width and height of an image for sampling. The width and height are not the exact sizes. The image ratio won't change but the size will be scaled down according the width and height. It helps to reduce the usage of memory. If it is absent, the default width and height are 128px each.
```java
String encodedImage = ImageBase64
                      .with(getApplicationContext())
                      .requestSize(128, 128) // default size
                      .encodeFile("/storage/emulated/0/some image file.jpeg");
```

### ``noScale()`` method
You can set noScale() to encode an image *without scaling* although it is not recommended because it can cause an out of memory exception. If it is set, the requestSize() method has no effect.
```java
String encodedImage = ImageBase64
                      .with(getApplicationContext())
                      .noScale()
                      .encodeFile("/storage/emulated/0/some image file.jpeg");
```


# SETUP
1. Download ImageBase64Encoder.jar
2. Copy it and paste into your Android project at *App* > *libs* > right click on the jar file and choose *Add as Library*



## Follow Me
 * Get more free source code at https://github.com/kosalgeek
 * Watch my video tutorials at my YouTube channel https://youtube.com/user/oumsaokosal
 * Like my Facebook Page at https://facebook.com/kosalgeek
 * Follow me on Twitter https://twitter.com/okosal
 * Get more tutorials at http://www.kosalgeek.com and http://www.top12review.com
 
# LICENSE

(The MIT License)
Copyright (c) 2016 KosalGeek. (kosalgeek at gmail dot com)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
