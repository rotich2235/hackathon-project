# hackathon-project
**Project Title: Photo Art Transformation Web App
Objective:**
Allow users to upload their photos and apply various filters/effects to create artistic renditions of those photos directly in the browser using HTML, CSS, and JavaScript.

**Key Features:**

**1. Photo Upload:**
Users can upload images from their local system using an <input> element.
**2. Apply Artistic Filters:**
Implement a few basic artistic effects like grayscale, sepia, blur, or even a pixelated effect.
You can achieve this using the <canvas> element in HTML5 along with CSS filters.
**3. Download and Share:**
After applying an effect, users can download their artwork or share it on social media.
**4. Interactive UI:**
Buttons or sliders to dynamically change the filter effects applied to the photo.
**5. Responsive Layout:**
Ensure the app is responsive, so it works well on both desktops and mobile devices.

Tech Stack:

Frontend:

HTML, CSS, and JavaScript

Use <canvas> for image manipulation

CSS for styling and creating a modern look

**Detailed Steps to Build the Project:**
**1. HTML Structure:**
We will create a basic structure to upload the image, display the photo, and apply filters.

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Photo Art Transformation</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="container">
    <h1>Photo Art Transformation</h1>
    <input type="file" id="imageUpload" accept="image/*" />
    <canvas id="canvas"></canvas>
    <div class="controls">
      <button onclick="applyGrayscale()">Grayscale</button>
      <button onclick="applySepia()">Sepia</button>
      <button onclick="applyBlur()">Blur</button>
      <button onclick="applyPixelate()">Pixelate</button>
      <button onclick="downloadImage()">Download</button>
    </div>
  </div>

  <script src="script.js"></script>
</body>
</html>


**2. CSS Styling:**
Make sure the page looks clean and organized.

body {
  font-family: Arial, sans-serif;
  background-color: #f0f0f0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
}

.container {
  text-align: center;
}

canvas {
  margin-top: 20px;
  max-width: 100%;
  border: 1px solid #ccc;
}

.controls button {
  margin: 5px;
  padding: 10px;
  background-color: #008CBA;
  color: white;
  border: none;
  cursor: pointer;
}

.controls button:hover {
  background-color: #005f75;
}

**3. JavaScript Functionality:**

In this file, we will use JavaScript to handle image uploading, applying filters, and downloading the final image.

let canvas = document.getElementById('canvas');
let ctx = canvas.getContext('2d');
let imageElement = new Image();

// Handle image upload
document.getElementById('imageUpload').addEventListener('change', function(event) {
  const file = event.target.files[0];
  const reader = new FileReader();
  
  reader.onload = function(e) {
    imageElement.src = e.target.result;
  };

  reader.readAsDataURL(file);
});

// Draw the image on the canvas
imageElement.onload = function() {
  canvas.width = imageElement.width;
  canvas.height = imageElement.height;
  ctx.drawImage(imageElement, 0, 0);
};

// Apply grayscale filter
function applyGrayscale() {
  ctx.drawImage(imageElement, 0, 0);
  ctx.filter = 'grayscale(100%)';
  ctx.drawImage(imageElement, 0, 0);
}

// Apply sepia filter
function applySepia() {
  ctx.drawImage(imageElement, 0, 0);
  ctx.filter = 'sepia(100%)';
  ctx.drawImage(imageElement, 0, 0);
}

// Apply blur effect
function applyBlur() {
  ctx.drawImage(imageElement, 0, 0);
  ctx.filter = 'blur(5px)';
  ctx.drawImage(imageElement, 0, 0);
}

// Apply pixelate effect
function applyPixelate() {
  ctx.drawImage(imageElement, 0, 0);
  ctx.filter = 'pixelate(10px)';
  ctx.drawImage(imageElement, 0, 0);
}

// Function to download the image
function downloadImage() {
  const link = document.createElement('a');
  link.download = 'transformed-image.png';
  link.href = canvas.toDataURL();
  link.click();
}

**4. Testing and Improvement:**
Once the basic structure has been set up:
Test the functionality by uploading an image and applying filters.
Enhance the app by adding more filters or an adjustable intensity for each effect.
You could also use WebAssembly for more intensive image processing tasks if needed in the future.

Enhancements :
**1. Custom Art Filters:**
Implement more advanced filters like sketching or painting effects using a JavaScript library or pre-built algorithms.
2. Slider Controls for Intensity:
Allow users to control the intensity of the effects using sliders (for example, blur strength or grayscale percentage).
3. Mobile Support:
Make sure the app is responsive and works on mobile by adding CSS media queries or using frameworks like Bootstrap.
4. Photo Collage:
Extend the project by allowing users to combine multiple photos into a collage and apply the filters to the entire collage.
5. Add Social Media Sharing:
Integrate buttons for users to share their creations on social media platforms like Twitter or Instagram.

**Conclusion:**

This project is simple enough for a hackathon while showcasing the combination of creativity and technical skills. It utilizes the HTML5 <canvas> element, along with basic CSS and JavaScript, to offer users a fun way to turn their regular photos into unique digital artwork!
