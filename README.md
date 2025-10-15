# Ex05 Image Carousel
## Date:15.10.2025

## AIM
To create a Image Carousel using React 

## ALGORITHM
### STEP 1 Initial Setup:
Input: A list of images to display in the carousel.

Output: A component displaying the images with navigation controls (e.g., next/previous buttons).

### Step 2 State Management:
Use a state variable (currentIndex) to track the index of the current image displayed.

The carousel starts with the first image, so initialize currentIndex to 0.

### Step 3 Navigation Controls:
Next Image: When the "Next" button is clicked, increment currentIndex.

If currentIndex is at the end of the image list (last image), loop back to the first image using modulo:
currentIndex = (currentIndex + 1) % images.length;

Previous Image: When the "Previous" button is clicked, decrement currentIndex.

If currentIndex is at the beginning (first image), loop back to the last image:
currentIndex = (currentIndex - 1 + images.length) % images.length;

### Step 4 Displaying the Image:
The currentIndex determines which image is displayed.

Using the currentIndex, display the corresponding image from the images list.

### Step 5 Auto-Rotation:
Set an interval to automatically change the image after a set amount of time (e.g., 3 seconds).

Use setInterval to call the nextImage() function at regular intervals.

Clean up the interval when the component unmounts using clearInterval to prevent memory leaks.

## PROGRAM:

## APP.JSX:
```
import React, { useState } from 'react';
import './App.css';
import juice1 from './assets/blue.jpeg';
import juice2 from './assets/green.webp';

const images = [juice1, juice2];

function App() {
  const [index, setIndex] = useState(0);

  const showPrevious = () => {
    setIndex((prevIndex) => (prevIndex === 0 ? images.length - 1 : prevIndex - 1));
  };

  const showNext = () => {
    setIndex((prevIndex) => (prevIndex === images.length - 1 ? 0 : prevIndex + 1));
  };

  return (
    <div className="app">
      <h1 className="title">Juice Carousel</h1>
      <div className="carousel">
        <img 
          src={images[index]} 
          alt={`Juice ${index + 1}`} 
          className="carousel-image" 
        />
      </div>
      <div className="buttons">
        <button onClick={showPrevious}>Previous</button>
        <button onClick={showNext}>Next</button>
      </div>
      <footer className="footer">SHYAM SUJIN U 212223040201</footer>
    </div>
  );
}

export default App;
```

## APP.CSS:

```
.app {
  text-align: center;
  margin-top: 40px;
  background-color: #1aede2;  
  width: 700px;               
  height: 700px;             
  margin-left: auto;          
  margin-right: auto;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 0 15px rgba(0,0,0,0.2);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.title {
  font-size: 2rem;
  margin-bottom: 20px;
}

.carousel {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
  width: 100%;
  max-width: 500px;
  height: auto;
  overflow: hidden;
  border-radius: 10px;
  box-shadow: 0 0 10px #a42c2c;
}


.carousel-image {
  width: 100%;
  height: auto;
  display: block;
  margin: 0 auto; 
}

.buttons {
  margin-top: 20px;
}

button {
  margin: 0 10px;
  padding: 10px 20px;
  font-size: 1rem;
  cursor: pointer;
}

.footer {
  margin-top: 30px;
  font-size: 1rem;
  color: #555;
  font-style: italic;
}
```

## OUTPUT:
<img width="1920" height="1080" alt="Screenshot (39)" src="https://github.com/user-attachments/assets/af3e1d3a-5e75-45e2-95db-c5cc599a74cd" />

<img width="1920" height="1080" alt="Screenshot (40)" src="https://github.com/user-attachments/assets/863a62cc-7290-43df-8675-218003e8f1a9" />


## RESULT:
The program for creating Image Carousel using React is executed successfully.
