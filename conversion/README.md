# BMP Converter: Mac Setup and Installation Guide

## Prerequisites

### 1. Install Homebrew (if not already installed)
If you don't have Homebrew, install it by running:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### 2. Install Python
```bash
brew install python
```

## Setup Python Environment

### 1. Create a Virtual Environment
```bash
# Navigate to your project directory
cd /path/to/your/project

# Create a virtual environment
python3 -m venv venv

# Activate the virtual environment
source venv/bin/activate
```

### 2. Install Required Dependencies
```bash
pip install pillow
pip install tkcalendar
```

## Running the Application

### 1. Ensure All Files are in the Same Directory
Make sure you have the following files:
- `converter.py`
- `imageHandler.py`

### 2. Run the Application
```bash
python3 converter.py
```

## Troubleshooting

### Python Tkinter Issues
If you encounter issues with Tkinter, you might need to install it separately:
```bash
brew install python-tk@3.9  # Replace 3.9 with your Python version
```

### Permission Issues
If you get permission errors:
```bash
chmod +x converter.py
```

## Development Notes

### Dependencies
- Python 3.7+
- tkinter
- Pillow (PIL)
- tkcalendar

### Supported Image Formats
- .jpg
- .jpeg
- .png
- .bmp

## Features

- Load multiple images
- Rotate images
- Scale images
- Offset image positioning
- Export images with date-based naming
- Backup and restore image settings

## Contributing
Feel free to fork the repository and submit pull requests with improvements or bug fixes.

## Additional Notes

### macOS-Specific Considerations
- Ensure you have the latest version of Python
- Some versions of macOS come with Python pre-installed, but it's recommended to use Homebrew's version
- You may need to adjust Python path depending on your system configuration

### Recommended Python Version
- Python 3.8 or higher is recommended
- Verify your Python version with `python3 --version`

### Potential Virtual Environment Alternative
If `venv` doesn't work, you can try:
```bash
pip3 install virtualenv
virtualenv venv
source venv/bin/activate
```
