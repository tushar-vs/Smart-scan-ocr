🧾 SmartScan: AI Invoice & Receipt Parser
SmartScan is an automated data extraction tool built with Python. It uses Deep Learning (OCR) to read text from images of receipts or invoices and uses logical parsing to extract structured financial data (Date, Vendor, Total Amount) for export to CSV.

🚀 Features
Optical Character Recognition (OCR): Utilizes EasyOCR (PyTorch) to extract text from noisy, unstructured images.
Computer Vision Preprocessing: Implements OpenCV to convert images to grayscale and handle varied formats.
Intelligent Parsing: Uses custom Regular Expressions (Regex) to identify dates (DD/MM/YYYY) and currency formats ($10.99) from raw text blocks.
Visual Validation: Draws bounding boxes around detected text on the UI to allow users to verify OCR accuracy.
Data Export: automatically structures extracted data into a Pandas DataFrame and allows one-click CSV download.
🛠️ Installation & Run
Clone the repository

Install Dependencies
pip install streamlit easyocr opencv-python-headless pandas numpy
Run the App
streamlit run app.py
🧠 How It Works
Upload: User drags and drops a receipt image (JPG/PNG).
Pre-processing: The app converts the image to a NumPy array readable by the model.
Inference: The EasyOCR model scans the image and returns text with coordinates.
Logic Layer:
Vendor Extraction: Assumes the first distinct text line is the vendor.
Date: Regex pattern matching for standard date formats.
Total: Context-aware search for the highest monetary value associated with keywords like "Total" or "Amount".
Output: Displays the data and offers a download link.
