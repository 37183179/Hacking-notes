## Goal
We found this [file](https://mercury.picoctf.net/static/d0129ad98ba9258ab59e7700a1b18c14/tunn3l_v1s10n). Recover the flag.

## Hints
Weird that it won't display right...
## Solution

+ Download the image
+ Create a copy and add the extension .bmp
+ Open HxD, a hexadecimal editor for Windows, and select the previously modified image.
+ At address 0x0E, we change the BA to 40 and at the next address we change the D0 to 00, the file header is corrected.
+ At address 0x0A, change the BA to 28 and at the next address change the D0 to 00, the offset is corrected.
+ We change the height of the image at address 0x16, the value it has to 40 and at the next address we add the value 04.
+ With this the image is modified and we open the image to see the flag.

	picoCTF{qu1t3_a_v13w_2020}
## Notes

### BMP file format
The **BMP file format** or **bitmap**, is a [raster graphics](https://en.wikipedia.org/wiki/Raster_graphics "Raster graphics") [image file format](https://en.wikipedia.org/wiki/Image_file_format "Image file format") used to store [bitmap](https://en.wikipedia.org/wiki/Bitmap "Bitmap") [digital images](https://en.wikipedia.org/wiki/Digital_image "Digital image"), independently of the [display device](https://en.wikipedia.org/wiki/Display_device "Display device") (such as a [graphics adapter](https://en.wikipedia.org/wiki/Graphics_adapter "Graphics adapter")), especially on [Microsoft Windows](https://en.wikipedia.org/wiki/Microsoft_Windows "Microsoft Windows")[[2]](https://en.wikipedia.org/wiki/BMP_file_format#cite_note-bmp-2) and [OS/2](https://en.wikipedia.org/wiki/OS/2 "OS/2")[[3]](https://en.wikipedia.org/wiki/BMP_file_format#cite_note-os2bmp-3) operating systems.

The BMP file format is capable of storing [two-dimensional](https://en.wikipedia.org/wiki/2D_computer_graphics "2D computer graphics") digital images in various [color depths](https://en.wikipedia.org/wiki/Color_depth "Color depth"), and optionally with [data compression](https://en.wikipedia.org/wiki/Data_compression "Data compression"), [alpha channels](https://en.wikipedia.org/wiki/Alpha_compositing "Alpha compositing"), and [color profiles](https://en.wikipedia.org/wiki/Color_management "Color management"). The [Windows Metafile](https://en.wikipedia.org/wiki/Windows_Metafile "Windows Metafile") (WMF) specification covers the BMP file format.[[4]](https://en.wikipedia.org/wiki/BMP_file_format#cite_note-v11-4)

## References
[BMP file format](https://en.wikipedia.org/wiki/BMP_file_format)