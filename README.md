This frontal face detector, WebAssemby model is pre-trained on the Genki-4K datatset for Web oriented applications. The model is production ready, works at Real-Time on all modern browsers (mobile devices included). Usage instruction already included in the package.
Setting Up a WebAssembly-Based Face Detector Using SOD Library
This guide walks you through deploying a WebAssembly (Wasm) face detector model pre-trained on the Genki-4K dataset for web applications. The face detector is designed to work in real-time on all modern browsers, including mobile devices.

Step 1: Download the Model
Visit the SOD project download page at pixlab.io/downloads.
Download the WebAssembly face detector model.
Step 2: Set Up Your Project
Project Directory:
Create a directory for your project. Ensure that the usage.html file and the downloaded .wasm file are in the same directory.
Step 3: Configure Your Web Server
To serve the WebAssembly model correctly, configure your web server to return the appropriate MIME type for .wasm files.

For Apache:

Open your .htaccess file or your virtual host configuration file.
Add the following directives:
apache
Copy code
AddType application/wasm .wasm
AddOutputFilterByType DEFLATE application/wasm
For Nginx:

Edit your Nginx configuration file.
Add the following directives:
nginx
Copy code
types {
    application/wasm wasm;
}
Step 4: Running Locally and on the Server
For Chrome users, testing WebAssembly modules requires running them from a web server (either locally or remotely). Simply opening the HTML file from the file system won't work due to Chrome's security restrictions.

Testing Locally:

Use a local server like Python's HTTP server:
sh
Copy code
python -m http.server
Navigate to http://127.0.0.1:8000 in your browser.
Testing Remotely:

Upload your project directory to your remote server.
Ensure that your server is configured correctly to serve .wasm files.
Additional Information on SOD Library
The SOD library offers a range of computer vision and machine learning tools designed for real-time applications and embedded systems. Some of the capabilities include:

Real-time object detection and classification using CNNs.
Embedded system support, allowing deployment on devices with limited resources.
A variety of pre-trained models available for different tasks.
Resources:

SOD in 5 Minutes or Less: A quick introduction to programming with the SOD Embedded C/C++ API.
C/C++ API Reference Guide: Detailed documentation of each API function.
License Plate Detection: Example of detecting vehicle license plates using SOD.
By following these steps, you can effectively deploy a WebAssembly-based face detector using the SOD library. This setup is ideal for applications requiring real-time face detection in web environments.

How to See the Result
Deployment:

Ensure the Wasm model and usage.html are correctly deployed on your server.
For local testing, you can use a local server like Python's HTTP server, while for production, deploy it on a live web server.
Accessing the Application:

Open your web browser and navigate to the URL where the application is hosted. If testing locally, this will typically be something like http://127.0.0.1:8000.
Using the Application:

Upon loading the page, the application will prompt for permission to access the webcam (if applicable).
Once granted, the application will display the video feed along with real-time face detection, highlighting detected faces.
Additional Information
Performance: The face detector works in real-time on modern browsers, including mobile devices. Ensure your server is correctly serving .wasm files to avoid issues, particularly on Chrome.
Customization: The detector can be customized or integrated into broader applications, such as for security, entertainment, or accessibility.
If the model and HTML are properly set up, the final application should work seamlessly, providing a practical demonstration of real-time face detection using WebAssembly and SOD.
