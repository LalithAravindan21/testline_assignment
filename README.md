PDF Content Extractor for Olympiad Papers 📝
This Python tool analyzes PDF files of educational content, specifically designed for question papers like the IMO (International Mathematics Olympiad) samples. It extracts all text and images, intelligently groups them by question, and outputs the structured data into a JSON file.

This script is notable for performing its pattern matching to identify questions without using regular expressions (regex), relying instead on basic string manipulation and the powerful PyMuPDF library.

## Features ✨
Text Extraction: Pulls all textual content from the PDF.

Image Extraction: Identifies and saves all images as separate files (e.g., .png, .jpg).

Intelligent Grouping: Analyzes the document structure to associate text and images with the correct question number.

Structured JSON Output: Creates a clean, organized JSON file containing a list of questions, each with its corresponding text and image paths.

## Prerequisites & Installation 🔧
Before you begin, ensure you have Python 3 installed on your system.

Clone the repository:

Bash

git clone <your-repository-url>
cd <your-repository-name>
Install the required libraries:
This project depends on PyMuPDF and Pillow. You can install them using pip.

Bash

pip install PyMuPDF pillow
## How to Use 🚀
Place the target PDF file in the root directory of the project. The script is currently configured to look for IMO Grade 1 - 1-2.pdf.

Run the script from your terminal:

Bash

python extract_olympiad_content_no_regex.py
That's it! The script will process the PDF and create an output directory.

## Output 📂
After the script runs successfully, it will create a new directory (e.g., output_no_regex/). Inside, you will find:

images/: A sub-directory containing all the images extracted from the PDF, named by page and image number (e.g., page1_image1.png).

extracted_content.json: A JSON file with the structured content.

### Example JSON Structure:
JSON

[
    {
        "question": "1. Find the matching pair.",
        "images": "output_no_regex/images/page1_image1.png",
        "option_images": [
            "output_no_regex/images/page1_image2.png",
            "output_no_regex/images/page1_image3.png"
        ]
    },
    {
        "question": "2. What is the next figure in the sequence below?",
        "images": "output_no_regex/images/page2_image1.png",
        "option_images": [
            "output_no_regex/images/page2_image2.png"
        ]
    }
]
