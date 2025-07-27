# Document-Scanner
This project is a web application that allows users to upload images and convert them into a single PDF document. It uses OpenCV for document cropping and image processing, and Flask for the web interface.

Project Structure
The project directory document scanner.zip contains the following:

document scanner.zip/
├── document/
│   ├── app.py
│   ├── document.py
│   ├── 1.jpg
│   ├── 2.jpg
│   ├── scanned_document.pdf
│   ├── scanned_document (1).pdf
│   ├── templates/
│   │   └── index.html
│   └── uploads/
│       ├── 1.jpg
│       ├── 2.jpg
│       └── scanned_document.pdf
└── README.md
app.py: This is the main Flask application file. It handles file uploads, processes images using the functions from document.py, and serves the web interface.

document.py: This file contains the core image processing logic, including functions for:

order_points: Orders the four corner points of a document.

four_point_transform: Applies a perspective transform to an image.

crop_document: Detects and crops a document from an image.

convert_to_grayscale: Converts an image to grayscale.

convert_to_sepia: Applies a sepia tint to an image.

invert_colors: Inverts the colors of an image.

enhance_colors: Enhances the colors of an image.

blue_tint: Applies a blue tint to an image.

save_as_pdf: Saves a list of images as a multi-page PDF, with an optional color transformation.

1.jpg, 2.jpg: Sample input image files.

scanned_document.pdf, scanned_document (1).pdf: Sample output PDF files.

templates/index.html: The HTML template for the web interface, providing the image upload form.

uploads/: A directory where uploaded images and generated PDF files are temporarily stored.

How to Run
To run this project, follow these steps:

1. Prerequisites
Make sure you have Python installed. This project also requires the following Python libraries:

Flask

OpenCV (cv2)

Pillow (PIL)

Numpy

You can install them using pip:

Bash

pip install Flask opencv-python Pillow numpy
2. Navigate to the Project Directory
Open your terminal or command prompt and navigate to the document scanner/document/ directory where app.py is located:

Bash

cd "document scanner.zip/document scanner/document/"
3. Run the Flask Application
Execute the app.py file to start the Flask development server:

Bash

python app.py
4. Access the Web Interface
Once the server is running (you'll see output like * Running on http://127.0.0.1:5000/), open your web browser and go to:

http://127.0.0.1:5000/
5. Upload Images and Convert to PDF
On the web page, you will see a button to "Choose Files".

Select one or more image files (e.g., 1.jpg, 2.jpg) from your computer.

Click the "Convert to PDF" button.

The application will process the images, crop the documents, and then download a scanned_document.pdf file to your browser.

Notes:
The debug=True setting in app.py means the server will automatically reload if you make code changes. It also provides more detailed error messages, which is useful for development but should be set to False in a production environment.

The uploads directory will be created automatically if it doesn't exist.

The document.py file also contains examples of how to apply different color transformations (grayscale, sepia, invert, enhance, blue tint) to the cropped images before saving them as a PDF. These transformations are currently called within document.py for local testing but are not directly exposed via the app.py web interface in the provided app.py file. If you want to integrate these filters into the web app, you would need to modify index.html and app.py to allow users to select them.
