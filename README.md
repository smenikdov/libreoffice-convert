# @smenikdov/libreoffice-convert

A package to convert files using LibreOffice. This package is a modernized version of an older, unmaintained project.

## Installation

```bash
npm install @smenikdov/libreoffice-convert
```

## Important Note

This package downloads a portable version of LibreOffice during installation (`postinstall` script). This means that LibreOffice is required for this package to work, and it will be downloaded when you install the package. The correct version for your operating system will be downloaded.

## Usage

### convertWordFiles(pathFile, extOutput, outputDir)

This function converts a file to a specified format using LibreOffice.

*   `pathFile` (string): The path to the file to be converted.
*   `extOutput` (string): The extension of the output file (e.g., 'pdf', 'docx').
*   `outputDir` (string): The directory where the converted file will be saved.

The function returns a promise that resolves with the path to the converted file.

**Example:**

```javascript
const { convertWordFiles } = require('@smenikdov/libreoffice-convert');
const path = require('path');

const inputPath = path.join(__dirname, 'test.docx');
const outputDir = path.join(__dirname, 'output');

convertWordFiles(inputPath, 'pdf', outputDir)
  .then((outputPath) => {
    console.log(`Successfully converted file: ${outputPath}`);
  })
  .catch((err) => {
    console.error(err);
  });
```
