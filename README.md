# OCR-Project


This HTML file provides a user-friendly interface for uploading an image, extracting text from it using a OCR (Optical Character Recognition) API (cloudlabs-image-ocr.p.rapidapi.com), and displaying the extracted text on the page. It uses Axios for making HTTP requests and includes error handling for API call failures.

*Note = the API can only accept 25 requestes per month since published !*


HTML Structure:

This HTML page provides a basic interface for uploading an image file and extracting text from it.
The input element with type="file" allows users to select an image file.
The button element triggers the extraction of text from the uploaded image.
The textarea element displays the extracted text.
The .extracted-content div will show the extracted content (text and images) after extraction.


Styling:

The page uses CSS to style its elements, ensuring a centered, visually appealing layout.
It provides styles for the body, headings (h2), container (div.container), image previews (img), file input (input[type="file"]), buttons (button and its hover state), and text areas (textarea).
The .extracted-content class is initially hidden (display: none) and will be shown after text extraction.

JavaScript Code:

The extractText Function: This function is triggered when the "Extract Text" button is clicked.
It retrieves the selected file from the input element (fileInput).
Checks if a file is selected. If not, it alerts the user and returns.
Creates a FormData object (formData) and appends the selected file to it.
Defines options for the Axios request, including method (POST), URL, headers (X-RapidAPI-Key and X-RapidAPI-Host), and data (the formData).
Uses axios.request to make the API call to extract text from the uploaded image.
Handles the response: If successful (response.status === 200 and result.status === 'success'), it updates the textarea with the extracted text and calls displayExtractedContent to display the extracted content. If unsuccessful, it displays a message.
Catches any errors that occur during the API call and displays an error message.
displayExtractedContent Function:
Clears any previous content in extractedContentDiv.
Creates a p element to display the extracted text (text).
Appends the p element to extractedContentDiv and displays it by setting display to 'block'.
imageInput Event Listener:
Monitors changes in the input element with id="imageInput".
Updates the image preview (imagePreview) with the selected image file using FileReader.

