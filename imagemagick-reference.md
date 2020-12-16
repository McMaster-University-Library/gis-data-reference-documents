## Resources
[Mogrify reference](https://imagemagick.org/script/mogrify.php)

## Recipes

- Return image specifications  
```identify LCMSDS_WW2_DefOvrPrnt_Emden_1945_c1.tif```

- Compress TIFF using LZW compression  
```convert 030M05_1909.tif -compress LZW 030M05_1909_LZW.tif```

- Rotate CCW by 45 degrees  
```mogrify -rotate "-45" foo.jpg```

- Convert tifs to jpegs; half-size; half-resolution (OCUL Topo Project):  
```mogrify -density 300 -units PixelsPerInch -resize 50% -format jpg *.tif```

- Convert tiff to lossless jp2000:  
```convert 1km177070490902013SCOOP.tif -quality 0 1km177070490902013SCOOP.jp2```

- Convert all .tiffs to jpegs; 4000 pixels wide  
```mogrify -format jpg -resize 4000x *.tiff```

- resize jpeg2000:  
```magick convert test.jp2 -resize 4000x test_resize.jp2```

- jpeg2000 to jpeg:  
```mogrify -format jpg -resize 4000x *.jp2```

- Generating thumbnails for Aerial Photos:  
```mogrify -resize 200x -format jpg *tif```

- Convert tif to jpg:  
```convert Vimy_panorama_full.tif Vimy_panorama_full.jpg```

- converting tiffs to pdfs:  
```mogrify -format pdf -compress jpeg -quality 90 *.tiff```

- Convert tifs to jpg; maximum dimension = 2500 pixels  
```mogrify -format jpg -resize 2500 *.tif```

- convert a tif to a jpg, 75% quality (higher compression)  
```magick convert UofA_WW2_GermanyHollandPoland_25k_1517_Ed4.tif -quality 75 UofA_WW2_GermanyHollandPoland_25k_1517_Ed4_75.jpg```

- Batch convert tifs to jpgs, 75% quality (higher compression)  
```magick mogrify -format jpg -quality 75 *.tif```

- Batch convert tifs to jpgs, 75% quality, max dimension = 5000 pixel (good for creating jpgs for metadata development)
```magick mogrify -format jpg -quality 75 -resize 5000 *.tif```

- Used to annotate a gif with text  
```
convert ^
Toronto_orig.gif -coalesce -font Verdana -pointsize 72 -stroke black ^  
-gravity SouthEast ^  
( -clone 0 -annotate 0 "1909" ) ^  
( -clone 1 -annotate 0 "1915" ) ^  
( -clone 2 -annotate 0 "1918" ) ^  
( -clone 3 -annotate 0 "1921" ) ^  
( -clone 4 -annotate 0 "1927" ) ^  
( -clone 5 -annotate 0 "1931" ) ^  
( -clone 6 -annotate 0 "1942" ) ^  
( -clone 7 -annotate 0 "1949" ) ^  
-delete 0-7 ^  
Toronto_annotated.gif
```

- Used to annotate a gif with text:  
```
convert ^
OttawaCopy.gif -coalesce -font Verdana -pointsize 72 -stroke black ^
-gravity SouthWest ^
( -clone 0 -annotate 0 "1906" ) ^
( -clone 1 -annotate 0 "1908" ) ^
( -clone 2 -annotate 0 "1914" ) ^
( -clone 3 -annotate 0 "1918" ) ^
( -clone 4 -annotate 0 "1920" ) ^
( -clone 5 -annotate 0 "1922" ) ^
( -clone 6 -annotate 0 "1925" ) ^
( -clone 7 -annotate 0 "1927" ) ^
( -clone 8 -annotate 0 "1930" ) ^
( -clone 9 -annotate 0 "1932" ) ^
( -clone 10 -annotate 0 "1933" ) ^
( -clone 11 -annotate 0 "1935" ) ^
( -clone 12 -annotate 0 "1936" ) ^
( -clone 13 -annotate 0 "1938" ) ^
( -clone 14 -annotate 0 "1940" ) ^
( -clone 15 -annotate 0 "1941" ) ^
( -clone 16 -annotate 0 "1948" ) ^
-delete 0-16 ^
OttawaCopyout.gif
```

