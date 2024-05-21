# js-mediaDevices-BOM
This repository contains an example of how to access media devices (camera and microphone) using JavaScript. The code demonstrates the use of the navigator.mediaDevices.getUserMedia API to capture video and audio streams from the user's device and display the video stream in a &lt;video> element.


Code Explanation
The following JavaScript code checks for support of the navigator.mediaDevices.getUserMedia API, and if supported, it requests access to the user's camera and microphone. If the request is successful, the video stream is displayed in a video element. Otherwise, an error message is logged to the console.  


if (navigator.mediaDevices && navigator.mediaDevices.getUserMedia) {
    navigator.mediaDevices
        .getUserMedia({ video: true, audio: true })
        .then((MediaStream) => {
            const videoElement = document.getElementById("video");
            videoElement.srcObject = MediaStream;
        })
        .catch((error) => {
            console.error("Error accessing Media devices:", error.message);
        });
} else {
    console.log("getUserMedia is not supported in this browser");
}


How to Use
HTML Setup:
Ensure you have a video element in your HTML where the video stream will be displayed:

<video id="video" autoplay></video>


JavaScript Implementation:
Include the provided JavaScript code in your script file or within a <script> tag in your HTML file.

Browser Compatibility:
This code requires a browser that supports the navigator.mediaDevices.getUserMedia API. Most modern browsers support this API. If the browser does not support it, a message will be logged to the console.

Features
Access to Media Devices: The code requests access to both video and audio from the user's device.
Error Handling: If there is an error accessing the media devices, an error message is logged to the console.
Browser Support Check: The code includes a check to ensure the getUserMedia API is supported in the user's browser.
Example


Here is a complete example including both HTML and JavaScript:


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Media Devices Access</title>
</head>
<body>
    <video id="video" autoplay></video>
    <script>
        if (navigator.mediaDevices && navigator.mediaDevices.getUserMedia) {
            navigator.mediaDevices
                .getUserMedia({ video: true, audio: true })
                .then((MediaStream) => {
                    const videoElement = document.getElementById("video");
                    videoElement.srcObject = MediaStream;
                })
                .catch((error) => {
                    console.error("Error accessing Media devices:", error.message);
                });
        } else {
            console.log("getUserMedia is not supported in this browser");
        }
    </script>
</body>
</html>
