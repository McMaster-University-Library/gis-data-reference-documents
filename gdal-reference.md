- Compress TIFF to lossless JPEG 2000  
```gdal_translate -of JP2OpenJPEG -co QUALITY=100 -co REVERSIBLE=YES -co YCBCR420=NO "D:/Dropbox (MUL)/GIS/SCOOP File Comparisons/1km177130490802013SCOOP.tif" "D:/Dropbox (MUL)/GIS/SCOOP File Comparisons/1km177130490802013SCOOP-JP2GDAL-lossless.jp2"```

- using gdal_merge to merge multiple georeferenced images into one:  
```gdal_merge.bat -of GTiff -o merged.tif 1km17592047920SWOOP2015.img 1km17591047890SWOOP2015.img 1km17590047880SWOOP2015.img 1km17589047870SWOOP2015.img 1km17591047900SWOOP2015.img 1km17590047890SWOOP2015.img 1km17589047880SWOOP2015.img 1km17591047910SWOOP2015.img 1km17590047900SWOOP2015.img 1km17589047890SWOOP2015.img 1km17591047920SWOOP2015.img 1km17590047910SWOOP2015.img 1km17589047900SWOOP2015.img 1km17590047920SWOOP2015.img 1km17589047910SWOOP2015.img 1km17589047920SWOOP2015.img 1km17597047860SWOOP2015.img```

- building tile index from a directory:   
```gdaltindex index.shp *.img```

- Building tiles of merged topo maps:  
```
gdalbuildvrt -overwrite -a_srs EPSG:4269 outputfile.vrt 030M04_1907.tif 030M05_1919.tif 040P01_1916.tif 040P08_1916.tif
gdal2tiles -s EPSG:4269 -q -r cubic -z 6-17 outputfile.vrt 1919
```
- A similar command to what was used to generate webtiles for the OCUL Topo Digitization Project:  
```gdal2tiles.py -s EPSG:26917 -z 6-16 030L13a_1969.tif```

- Converting GDAL TMS tiles to XYZ tiles:
  - https://gis.stackexchange.com/questions/63024/gdal2tiles-maptiles-from-bsb-kap-are-switched
  - http://osgeo-org.1560.x6.nabble.com/gdal2tiles-tiles-in-wrong-hemisphere-and-or-Openlayers-problem-td3742809.html
  - https://gist.github.com/tmcw/4954720
  - https://gist.github.com/kannes/ebfe021458f96e4f30b5
  - https://github.com/geometalab/pyGeoTile
