# Libreoffice Convert

A package to convert files using LibreOffice.

## Installation

```bash
npm install libreoffice-convert
```

## Usage

```javascript
const libreofficeConvert = require('libreoffice-convert');
const path = require('path');
const fs = require('fs');

const inputPath = path.join(__dirname, 'test.docx');
const outputPath = path.join(__dirname, 'test.pdf');

const file = fs.readFileSync(inputPath);

libreofficeConvert.convert(file, '.pdf', undefined, (err, result) => {
    if (err) {
        console.log(`Error: ${err}`);
    }
    fs.writeFileSync(outputPath, result);
});
```
