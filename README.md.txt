# LoG Filter – Professional Edge Detection

High-performance Laplacian of Gaussian (LoG) edge detection for QGIS raster datasets.

This project provides an optimized implementation of the LoG filter designed for both elevation models (DEM) and remote sensing imagery. The workflow includes automatic raster type detection, adaptive preprocessing, intelligent sigma estimation, and multithreaded execution for efficient processing of large datasets.

---

## Overview

LoG Filter is intended for extracting terrain structures and image features from raster data while maintaining high performance and minimizing user interaction.

The algorithm automatically adapts its processing strategy according to the input data type:

- Digital Elevation Models (DEM)
- Orthophotos and UAV imagery
- Satellite imagery
- Single-band and RGB rasters

---

## Key Features

### Automatic Raster Classification
The script analyzes raster statistics and automatically determines whether the input represents:

- DEM data
- Optical imagery

A confidence-based decision system is used to improve reliability.

### Adaptive Preprocessing
Different preprocessing pipelines are applied depending on the detected raster type:

- Robust normalization for DEM datasets
- Percentile-based contrast enhancement for imagery
- Outlier reduction
- NoData handling

### Adaptive Sigma Selection
Sigma values are automatically calculated based on:

- Raster dimensions
- Data type
- Image quality level

Manual sigma values can also be specified.

### Optimized Raster Processing
Performance improvements include:

- Fast raster reading using NumPy buffers
- Vectorized operations
- Single-block raster writing
- Multithreaded execution
- Progress reporting during processing

### Multi-Band Support
The script supports:

- Single-band rasters
- RGB imagery
- Automatic grayscale conversion

---

## Processing Workflow

1. Load raster data
2. Detect raster type
3. Apply adaptive preprocessing
4. Calculate optimal sigma
5. Perform Laplacian of Gaussian filtering
6. Scale output values
7. Export the resulting raster
8. Automatically add the result to the current QGIS project

---

## Requirements

- QGIS
- Python 3
- NumPy
- SciPy
- PyQt5

---

## Dependencies

```python
numpy
scipy
PyQt5
qgis.core
```

---

## Usage

1. Open QGIS.
2. Select an active raster layer.
3. Execute the script from processing tool.
4. Choose:

   - Raster type (Automatic / DEM / IMAGERY)
   - Quality level
   - Sigma value (Auto or manual)

5. Start processing.
6. The resulting raster will be loaded automatically into the project.

---

## Supported Data

| Dataset Type | Supported |
|--------------|-----------|
| DEM | ✓ |
| Orthophotos | ✓ |
| UAV imagery | ✓ |
| Satellite imagery | ✓ |
| Single-band rasters | ✓ |
| RGB rasters | ✓ |

---

## Output

The generated raster contains enhanced edge information derived from the Laplacian of Gaussian operator and is exported as a GeoTIFF file.

---

## Author

*Rosen Iliev*

---

## Contact

*Email: ilievrosen88@abv.bg*

---

## License

MIT License