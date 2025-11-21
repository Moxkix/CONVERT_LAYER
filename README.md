# CONVERT_LAYER
# ArcGIS Pro Layer File Converter (.lyrx)

A web-based tool for converting ArcGIS Pro layer files (.lyrx) between Feature Layers and Raster Layers in both directions.

![License](https://img.shields.io/badge/license-CC%20BY%204.0-blue.svg)
![ArcGIS Pro](https://img.shields.io/badge/ArcGIS%20Pro-3.4.0-green.svg)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6-yellow.svg)
![React](https://img.shields.io/badge/React-18-61dafb.svg)

## 🎯 Overview

This single-page application provides a seamless conversion between ArcGIS Pro Feature Layers (`CIMFeatureLayer`) and Raster Layers (`CIMRasterLayer`) while preserving symbology, colors, and classifications. Perfect for GIS professionals who need to quickly transform layer types without losing their carefully configured visualization settings.

## ✨ Features

### Core Functionality
- **Bidirectional Conversion**: 
  - Feature Layer → Raster Layer
  - Raster Layer → Feature Layer
- **Automatic Detection**: Instantly identifies the layer type upon file upload
- **Symbology Preservation**: Maintains all colors, labels, and classifications during conversion
- **Custom Field Mapping**: Specify the classification field name for raster conversion

### User Interface
- **Drag & Drop Support**: Simply drag your .lyrx file into the browser
- **Real-time Conversion Log**: Track the conversion process step by step
- **Visual Comparison**: Side-by-side view of original and converted structure
- **Instant Download**: Get your converted file with a single click

## 🚀 Getting Started

### Online Version
Simply open the HTML file in any modern web browser. No installation or server required!

### Local Setup
```bash
# Clone the repository
git clone https://github.com/yourusername/arcgis-lyrx-converter.git

# Navigate to the directory
cd arcgis-lyrx-converter

# Open the HTML file in your browser
# (or serve it with any static file server)
open arcgis_lyrx_converter.html
```

## 📖 How to Use

1. **Load Your File**: Drag and drop a .lyrx file or click to browse
2. **Automatic Detection**: The app identifies whether it's a Feature or Raster layer
3. **Configure (if needed)**: For Feature→Raster conversion, specify the classification field name
4. **Convert**: Click the conversion button to transform your layer
5. **Download**: Save your converted file with the appropriate suffix (_RASTER or _FEATURE)

## 🔧 Technical Details

### Supported Conversions

#### Feature Layer → Raster Layer
- Converts `CIMFeatureLayer` to `CIMRasterLayer`
- Transforms `renderer` to `colorizer` (CIMRasterUniqueValueColorizer)
- Creates appropriate data connection for raster datasets
- Converts feature classes to raster unique value classes
- Adds raster-specific properties and attribute table

#### Raster Layer → Feature Layer
- Converts `CIMRasterLayer` to `CIMFeatureLayer`
- Transforms `colorizer` to `renderer` (CIMUniqueValueRenderer)
- Creates polygon symbols from raster colors
- Adds 3D layer properties
- Configures feature-specific settings (snapping, scaling, etc.)

### File Structure Preservation
- Layer names and descriptions
- Color values (RGB with alpha)
- Class labels and values
- Coordinate systems references
- Layer visibility settings

## 🛠️ Technologies Used

- **React 18**: For reactive UI components
- **Tailwind CSS**: For modern, responsive styling
- **Vanilla JavaScript**: For file processing and JSON manipulation
- **HTML5 File API**: For drag-and-drop functionality

## 📋 Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge)
- ArcGIS Pro .lyrx files (version 3.4.0 or compatible)
- No server or backend required - runs entirely in the browser

## 🎨 Use Cases

- **Data Migration**: Convert existing feature layers to raster format for analysis
- **Visualization Switching**: Switch between vector and raster visualization methods
- **Workflow Optimization**: Quickly prepare layers for different GIS operations
- **Batch Processing Preparation**: Convert multiple layers for consistent processing
- **Cross-Platform Compatibility**: Ensure layers work across different GIS tools

## ⚠️ Limitations

- Only processes .lyrx files from ArcGIS Pro
- Preserves unique value classifications only (not graduated colors or other renderer types)
- Some advanced layer properties may not be fully converted
- Large files may take longer to process

## 📝 License

This work by **Iñaki Moro** is licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).

You are free to:
- **Share** — copy and redistribute the material in any medium or format
- **Adapt** — remix, transform, and build upon the material for any purpose, even commercially

Under the following terms:
- **Attribution** — You must give appropriate credit, provide a link to the license, and indicate if changes were made

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

## 🐛 Bug Reports

If you find a bug or have a suggestion, please open an issue on GitHub with:
- Description of the problem
- Steps to reproduce
- Expected behavior
- Actual behavior
- Sample .lyrx file (if possible)

## 👤 Author

**Iñaki Moro**
- Location: Universidad del País Vasco/Euskal Herriko Unibertsitatea (UPV/EHU)
- Specialization: GIS, Academic Administration, Geography

## 🙏 Acknowledgments

- ArcGIS Pro development team for the .lyrx file format
- The open-source GIS community
- Contributors and users who provide feedback

## 📊 Version History

- **v1.0.0** (2024) - Initial release
  - Bidirectional conversion between Feature and Raster layers
  - Full symbology preservation
  - Drag-and-drop interface

---

Made with ❤️ for the GIS community
