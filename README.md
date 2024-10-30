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

## Usage
Availabe options:
``` bash
-f / --file: the source image file, eg. mylarge.tif
-o / --output-dir: the target folder, for *.mbtiles result temporary created files
-t / --image-type: the target image type: PNG (true color PNG), PNG8 (for 8 bit PNG), JPEG
-q / --quality: JPEG quality setting (eg 70, 75, 90), only applied to -t JPEG
-sz / --start-zoom: starting zoom level (16 by default)
-ez / --end-zoom: end zoom level (21 by default)
-p / --processors: number of core allocated for processing
```

Examples:
``` bash
gd2mbt -f mylargefile.tif -t JPEG -q 70 -sz 16 -ez 20 -o ./output
```
