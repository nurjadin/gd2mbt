# gd2mbt
GDAL supported image conversion into zoom level 16 Web Mercator compatible grid MBTiles

## Features
- Split GDAL compatible image (tested with GeoTIFF) into some MBTiles that compatible with Web Mercator zoom level 16 grid
- Choose target image format: PNG, PNG8, JPEG
- Allow setting image quality when choosing JPEG image format
- Allow multiple processors
- Automatically split data source into Web Mercator zoom level 16 compatible grid size
- Automatically named mbtiles result into xxxxx_yyyyy.mbtiles, resembles x and y grid coordinate

## Specs
- Depends on existing GDAL binary (gdal_warp, gdal2tiles, gdalinfo)
- Suported image data source format: rely on supported GDAL formats (check it with gdalinfo --formats)
- Require quite large temporary space during processing: projected image, tile image folder etc
- Might not be the most effective nor the fastest way, suggestions/contributions welcome
