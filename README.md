IPA PNG Images Normalizer
===
##这是什么？
使用xcode打包的IPA文件中的png图片有些会被自动压缩成CgBI文件格式，
CgBI得名于其额外的头，是苹果的专有扩展到PNG的图像格式
压缩过得图片将不会是标准的png，详细来说就是
These modifications cause the generated images to be invalid as per the current version of the PNG standard.
*extra critical chunk (CgBI)
*byteswapped (RGBA -> BGRA) pixel data, presumably for high-speed direct blitting to the framebuffer
*zlib header, footer, and CRC removed from the IDAT chunk
*premultiplied alpha (color' = color * alpha / 255)
本脚本可以解码该文件成标准png😀
##原始解码方法
*mac环境下直接使用xcrun -sdk iphoneos pngcrush -revert-iphone-optimizations
*非mac环境下苹果没有直接提供解码方法，可使用本脚本
##使用方法
1.将本文件与*.ipa放在同一目录下
2.python ipin.py
*注意，源文件将会被覆盖

##出处和参考（版权归作者所有）
http://www.axelbrz.com.ar/?mod=iphone-png-images-normalizer
https://gist.github.com/urielka/3609051

