# FaceFit Barber Application

"FaceFit Barber" is an application designed to help users find the perfect haircut style that fits their face shape. By utilizing camera integration and AI models, this app offers personalized hairstyle recommendations and enhances the barbershop experience for both customers and barbers.

![logoApp](https://res.cloudinary.com/dkcpexm6t/image/upload/v1779770675/LogoApp_kloy1o.png)

## Main Features

* 📷 **Face Capture**: Utilizes webcam to capture and analyze the user's face shape.
* 🖼️ **Image Upload**: Allows users to upload a face image from their local device.
* 🧠 **AI Face Shape Analysis**: Processes the captured or uploaded image using an AI model to determine the user's face shape.
* ✂️ **Hairstyle Recommendations**: Suggests suitable haircuts based on the detected face shape.
* 🧭 **Interactive UI**: Provides smooth routing and a user-friendly interface.
* 📱 **Responsive Design**: Optimized for various devices, including mobile and desktop screens.
* 🌐 **Online Deployment**: Frontend and AI backend services are deployed online.

## Technologies Used

**Frontend:**

* React + Vite
* Tailwind CSS
* React Router DOM
* React Webcam
* Axios
* Vercel

**Backend:**

* JavaScript
* Node.js
* Express.js
* FastAPI
* RESTful APIs
* Hugging Face Spaces

**AI Model:**

* Python
* TensorFlow / Keras
* NumPy
* Pillow
* Google Colab
* Jupyter Notebook

**Data Science:**

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Streamlit
* Jupyter Notebook

## Project Structure

```text
FaceFit-Barber-Application/
├── FaceFit-Barber-FrontEnd/
├── FaceFit-Barber-BackEnd/
├── FaceFit-Barber-Model-AI/
├── FaceFit-Barber-Data-Science/
└── README.md
```

## Repository Scope

This main repository is used to organize all FaceFit Barber project modules. Each module has a different responsibility in the project workflow.

### 1. FaceFit-Barber-FrontEnd

The frontend repository contains the user interface of the FaceFit Barber web application.

**Scope:**

* Building the web interface using React + Vite.
* Handling page navigation using React Router DOM.
* Providing webcam-based face capture using React Webcam.
* Providing image upload functionality.
* Sending image data to the backend AI service.
* Displaying face shape analysis results.
* Displaying hairstyle recommendations.
* Deploying the frontend application using Vercel.

### 2. FaceFit-Barber-BackEnd

The backend repository contains API routing and AI service integration for the application.

**Scope:**

* Handling backend routes using Express.js.
* Receiving uploaded images from the frontend.
* Connecting the frontend with the AI model service.
* Managing local backend development.
* Providing FastAPI ML service for AI inference.
* Returning face shape prediction, confidence score, probabilities, and hairstyle recommendations.
* Deploying the AI backend service using Hugging Face Spaces.

### 3. FaceFit-Barber-Model-AI

The Model AI repository contains the AI model development process and exported model artifacts.

**Scope:**

* Building and training the face shape classification model.
* Preparing model input configuration.
* Saving class names and preprocessing configuration.
* Exporting the trained model in `.keras` and SavedModel formats.
* Storing model evaluation results such as confusion matrix and training curves.
* Documenting the model development process using Jupyter Notebook.
* Providing the model used by the backend AI service.

### 4. FaceFit-Barber-Data-Science

The Data Science repository contains dataset preparation, data analysis, and supporting visualization.

**Scope:**

* Collecting and organizing datasets.
* Filtering and cleaning face image datasets.
* Preparing datasets before and after class balancing.
* Performing exploratory data analysis.
* Creating A/B testing analysis.
* Providing dashboard visualization using Streamlit.
* Supporting the Model AI repository with cleaned and structured datasets.

## Application Flow

```text
User opens the FaceFit Barber web application
→ User captures or uploads a face image
→ Frontend sends the image to the AI backend API
→ Backend preprocesses the image
→ AI model predicts the user's face shape
→ Backend returns prediction result and hairstyle recommendations
→ Frontend displays the result to the user
```

## Supported Face Shape Classes

The AI model classifies user face images into the following face shape categories:

```text
diamond
heart
oval
round
square
```

## AI Model Overview

The AI model is built using TensorFlow/Keras and is used to classify face shape from an input image.

Input specification:

```text
224 x 224 x 3
```

Preprocessing steps:

1. Convert image to RGB format.
2. Apply center crop with a crop ratio of 0.88.
3. Resize image to 224 x 224 pixels.
4. Convert image into a `float32` array.
5. Pass the image into the trained model.

The model returns probability scores for each class. The class with the highest probability is selected as the final face shape prediction.

Example response:

```json
{
  "success": true,
  "faceShape": "Heart",
  "confidence": 0.637,
  "hairstyle": [
    "Textured Fringe",
    "Side Part",
    "Low Fade"
  ],
  "message": "Foto berhasil dianalisis"
}
```

## Deployment

### Frontend Deployment

The frontend application is deployed using Vercel.

Live Website:

https://facefit-barber.vercel.app/

Vercel is used to publish the React/Vite frontend application and connect it with the deployed AI backend service.

### AI Backend Deployment

The AI backend service is deployed using **Hugging Face Spaces**.

Production AI Backend:

```text
https://justblaisee-facefit-ml-service.hf.space
```

Main endpoint used by the frontend:

```text
https://justblaisee-facefit-ml-service.hf.space/api/faces/analyze
```

## How to Replicate

### 1. Clone the Main Repository

```bash
git clone https://github.com/raphael707/FaceFit-Barber-Application.git
cd FaceFit-Barber-Application
```

If the repository uses submodules, initialize and update them:

```bash
git submodule update --init --recursive
```

### 2. Install Backend Dependencies

```bash
cd FaceFit-Barber-BackEnd
npm install
```

### 3. Install Frontend Dependencies

```bash
cd ../FaceFit-Barber-FrontEnd
npm install
```

### 4. Install ML Service Dependencies

```bash
cd ../FaceFit-Barber-BackEnd/ml-service
pip install -r requirements.txt
```

### 5. Start the ML Service

```bash
uvicorn main:app --reload --port 8000
```

The FastAPI ML service will run at:

```text
http://127.0.0.1:8000
```

FastAPI documentation:

```text
http://127.0.0.1:8000/docs
```

### 6. Start the Backend Server

Open a new terminal:

```bash
cd FaceFit-Barber-BackEnd
npm start
```

The Express backend will run at:

```text
http://localhost:3000
```

### 7. Start the Frontend App

Open another terminal:

```bash
cd FaceFit-Barber-FrontEnd
npm run dev
```

Open the frontend URL shown in the terminal, usually:

```text
http://localhost:5173
```

## Environment Variable

For frontend integration, create a `.env` file inside the `FaceFit-Barber-FrontEnd` folder.

For production AI backend:

```env
VITE_API_URL=https://justblaisee-facefit-ml-service.hf.space
```

For local Express backend:

```env
VITE_API_URL=http://localhost:3000
```

For direct local FastAPI ML service:

```env
VITE_API_URL=http://127.0.0.1:8000
```

## Notes

* This repository acts as the main project repository.
* Frontend, backend, model AI, and data science modules are separated into their own repositories or submodules.
* Large datasets and model files may require external storage or Git LFS.
* Environment variables such as `.env` should not be committed to GitHub.
* The deployed Hugging Face Space may take longer on the first request if the service is inactive.
* Make sure each submodule is updated before committing changes to the main repository.

## Updating Submodules

To update all submodules based on the commits recorded in this main repository:

```bash
git submodule update --init --recursive
```

To update submodule references after changes are pushed inside each module:

```bash
git add FaceFit-Barber-FrontEnd FaceFit-Barber-BackEnd FaceFit-Barber-Model-AI FaceFit-Barber-Data-Science
git commit -m "Update project submodule references"
git push origin main
```

## Contributing

Feel free to fork this repository and submit a pull request.

For team collaboration, it is recommended to:

1. Create a new branch.
2. Commit changes clearly.
3. Push the branch.
4. Open a pull request.
5. Merge after review.

## License

MIT License - Use freely with attribution.

## Credits

Developed as part of a **Capstone Project** to innovate the barbershop and grooming experience through AI-based face shape analysis and personalized hairstyle recommendation.
