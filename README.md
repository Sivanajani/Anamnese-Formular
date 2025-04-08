# 🧾 Anamnesis Form – Automated PDF Analysis

This project focuses on the automated analysis and processing of anamnesis forms commonly used in medical documentation.  
The goal is to extract printed content from PDF forms, evaluate checkboxes, and match results against a predefined catalog of statements.

> ⚠️ Due to the sensitive nature of the data and documents, the **source code of this repository is not publicly available**.

---

## 🧩 Project Overview

The pipeline consists of several stages:

1. **PDF Conversion**: Convert PDF files into high-resolution images.
2. **Image Preprocessing**: Binarize and deskew images to enhance OCR performance.
3. **Text Extraction (OCR)**: Use Tesseract to extract text and detect checkboxes.
4. **Checkbox Analysis**: Recognize and classify "Yes"/"No" checkbox markings.
5. **Catalog Matching**: Match extracted sentences to a reference statement catalog.
6. **Export**: Output the structured results into CSV files.

---

## ⚙️ Setup & Installation

### 🐍 Python Dependencies

```bash
pip install pdf2image
pip install pytesseract
pip install opencv-python
pip install numpy
pip install Levenshtein
```

### Poppler
Poppler is required for PDF-to-image conversion.

**Windows:**
- [Download Poppler](https://github.com/oschwartz10612/poppler-windows)
- and add `bin`-Ordner to your system PATH

**macOS:**
```bash
brew install poppler
```

**Linux:**
```bash
sudo apt install poppler-utils
```

---

## 🛠️ Key Functions

### Converts a PDF into image files
```python
pdf_to_images(pdf_path)
```

### Preprocessing steps
```python
binarize_image(image)
deskew_image(img_path)
```

### Extract and identify keywords via OCR
```python
get_sentences(img)
get_keywords(words, df)
```

### Detect and filter checkbox data
```python
get_checkboxes(...)
filter_checkboxes_for_outliers(...)
```

### Save results in structured format
```python
export_to_csv(data, file)
```

---

## ⚠️ Known Limitations

- OCR Accuracy depends on scan quality and font.
- Checkbox Detection may fail with very small or unclear boxes.
- At the moment only supports PDF and JPG inputs.
---

## 📄 License
This project was developed as part of a university project at FHNW. The **project presentation** is attached as a PDF file and provides an overview of the key processes, features, and outcomes.

📄 [📥 View the project presentation (Anamnese.pdf)](./Anamnese.pdf)

