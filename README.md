# vectornator-to-svg
Convert your .vectornator files to SVG for free!  Save your lost art like I did with mine!
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

1. Clone this repository:
```bash
git clone https://github.com/yourusername/vtosvg.git
cd vtosvg
```

2. No additional dependencies required - just Python 3.x!

## 📖 Usage

### Basic Usage

Convert a single file:
```bash
python vtosvg.py input.vectornator
```

This will create `input.svg` in the same directory.
(The output SVG files are optimized for Inkscape and other leading SVG editors / viewers)

### Specify Output File

```bash
python vtosvg.py input.vectornator output.svg
```

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
