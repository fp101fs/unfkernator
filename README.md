# .vectornator-to-svg
Convert your .vectornator files to SVG for free!  Save your lost art like I did!
This repository is a work-in-progress.  There are known issues.  Please help me make this better.  Just drop the scripts into Claude.ai!

# 🎨 Vectornator to SVG Converter

A simple Python tool to convert Vectornator files (.vectornator) to standard SVG format. Perfect for web use, further editing, or integration with other tools.

## ✨ Features

- Converts .vectornator files to clean SVG
- Preserves paths, colors, and opacity
- Handles compound paths
- Maintains original canvas dimensions
- Processes multiple layers
- Cleans up redundant path data

## 🚀 Installation

1. Go to vectornator-to-svg's [latest Release](https://github.com/fp101fs/vectornator-to-svg/releases/latest)

2. In the Assets section, click on vectornator-to-svg-vXYZ.zip to Download the ZIP file

3. Extract the ZIP file

4. Open the Terminal and Run the command below (but replace myfile.vectornator with your File name):

```bash
python vtosvg.py myfile.vectornator
```
Also try these:
```bash
python vtosvg_special.py myfile.vectornator
python vtosvg_img.py myfile.vectornator
```

Yes - I recommend you try all scripts above on your file(s) - because each script does a different thing (see detailed file structure and purposes below)

For example, vtosvg.py might convert your file(s) with no issues.  
But if not, then vtosvg_special.py might do it.  
And last but not least, vtosvg_img.py should extract any "image" layers from your .vectornator files (for example - a sketch you snapped a photo of and then used Vectornator's Auto-Trace feature).

No additional dependencies required - just Python 3.x!  Intended to be cross-platform.

# 🎨 Vectornator to SVG Converter
Convert your .vectornator files to SVG for free! Save your lost art like I did with mine!

## 📦 Script Components

### 🟢 vtosvg.py - Main Conversion Script
The primary script for converting Vectornator files to SVG format.

**Purpose:**
- Handles the main conversion process
- Manages layer organization
- Preserves SVG structure and attributes
- Supports Inkscape-compatible output

**Example:**
```bash
python vtosvg.py design.vectornator
# Creates design.svg with preserved layers and attributes
```

**Usage:**
```bash
# Basic conversion
python vtosvg.py input.vectornator

# Specify output file
python vtosvg.py input.vectornator output.svg
```

### 🟢 vtosvg_special.py - Special Elements Handler
This is an experimental script!  This script was created to try to recover some of the elements of my more "complex" sketches in Vectornator / Linearity Curve. 
 This script handles complex Vectornator elements and features than the vtosvg.py script.

**Purpose:**
- Processes compound paths
- Handles gradients
- Manages special color formats
- Processes complex transformations

**Example:**
```bash
python vtosvg_special.py complex_design.vectornator
# Handles special elements like gradients and compounds
```

### 🟢 vtosvg_img.py - Image Data Extraction & Analysis Tool
Analyzes and extracts image components from Vectornator files.

**Purpose:**
- Identifies embedded images
- Extracts thumbnail data
- Analyzes .dat files for image content
- Saves extracted images

**Example:**
```bash
python vtosvg_img.py design_with_images.vectornator
# Extracts and saves images as separate files
```

**Usage:**
```bash
python vtosvg_img.py input.vectornator
# Creates:
# - input_thumbnail.png
# - input_image1.png
# - input_image2.png (if multiple images exist)
```

### 🟢 vtosvg_utils.py - Utility Functions (not intended for direct use - this is a "helper" script for vtosvg.py)
A collection of helper functions for SVG processing and conversion.

**Purpose:**
- Color conversion (HSB to RGB)
- Path data processing
- Style handling
- Compound path processing
- Image element handling

**Example:**
```python
from vtosvg_utils import convert_nodes_to_path_data, hsb_to_rgb

# Convert HSB color to RGB
rgb_color = hsb_to_rgb(0.5, 0.8, 1.0)  # Returns "rgb(51,255,255)"

# Process path nodes
path_data = convert_nodes_to_path_data(nodes)
```

## 🚀 Quick Start

1. Clone the repository:
```bash
git clone https://github.com/yourusername/vectornator-to-svg.git
```

2. Convert a file:
```bash
python vtosvg.py your_design.vectornator
```

## 📋 Requirements
- Python 3.x
- No additional dependencies required

## ⚠️ Known Issues
- Some gradient effects may not convert perfectly
- Text elements are converted to paths
- Complex effects might require manual adjustment

### Batch Processing

You can easily create a simple batch script. For example:

```bash
for file in *.vectornator; do
    python vtosvg.py "$file"
done
```

## 📂 File Structure

- `vtosvg.py` - Main conversion script
- `vtosvg_utils.py` - Utility functions for SVG processing

## 🔍 Example Output

Input:
```
MyDesign.vectornator (Binary file)
```

Output:
```xml
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<svg xmlns="http://www.w3.org/2000/svg" version="1.1"
     width="3000" height="3000" viewBox="0 0 3000 3000">
  <!-- Converted paths and elements -->
</svg>
```

## 🤝 Contributing

Contributions are welcome! Feel free to:

1. Fork the repository
2. Create a new branch
3. Make your changes
4. Submit a pull request

## ⚠️ Known Limitations

- Gradients are currently converted to solid colors
- Text elements are converted to paths
- Some complex effects may not transfer perfectly

## 📝 License

MIT License - feel free to use in your own projects!

## 🙏 Credits

Created to solve the challenge of using Vectornator artwork in web projects. Inspired by the need for clean SVG output from Vectornator's native format.
