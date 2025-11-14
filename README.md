# FaceMe AI Recognition  
Detect AI-Generated Images with Deep Learning (EfficientNetB0 + Flask API + React Frontend)

FaceMe AI Recognition is a full-stack machine learning application that detects whether an input image is **AI-generated** or **real**.  
The model is trained using **EfficientNetB0** and served through a **Flask REST API**, while the UI is built using a modern **React + Vite** frontend.

This project is designed for portfolio-grade quality and easy deployment.

---

## 🚀 Features

- 🔍 **AI vs Real Image Detection** using a fine-tuned EfficientNetB0 model  
- 🧠 **Deep Learning Backend (TensorFlow / Keras)**  
- 🌐 **REST API using Flask**  
- ⚡ **Fast Frontend using React + Vite**  
- 📤 Support drag-and-drop, paste, or upload image  
- 📈 Confidence score output (0–100%)  
- 🧩 Clean modular folder structure  
- 🛡 CORS-enabled API for local or production deployment  

---

## 🧠 Model Information

- **Architecture:** EfficientNetB0 (ImageNet pretrained)  
- **Input Size:** 224×224  
- **Output:** Binary classification (`AI Generated` or `Real Image`)  
- **Activation:** Sigmoid  
- **Training Stages:**  
  1. Frozen EfficientNetB0  
  2. Fine-tuning with low LR  

Model file:  "best_model.keras" in the "model" folder


---

## ⚙️ Backend Setup (Flask API)

### 1. Create & activate environment (recommended)

conda create -n faceme python=3.10
conda activate faceme


### 2. Install dependencies

pip install -r requirements.txt


### 3. Run Flask API

python app.py

API runs at: http://localhost:5173

---

## 🔥 API Documentation

### **POST /predict**

**Request:**  
`multipart/form-data` with field `file`

**Response example:**

```json
{
  "success": true,
  "predicted_class": 0,
  "class_name": "AI Generated",
  "confidence": 0.92,
  "confidence_percentage": "92.0%",
  "raw_prediction": 0.08
}
```

## 💻 Frontend Setup (React + Vite)

cd frontend
npm install
npm run dev

Runs at: http://localhost:5173
The frontend will call the backend automatically.

## 📸 How It Works (Flow)

1. User uploads/pastes an image
2. Frontend sends it to /predict via FormData
3. Flask preprocesses (224×224 resizing + normalization)
4. TensorFlow model predicts
5. Frontend displays result + confidence

# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.

## 📄 License

MIT License – Free to use for learning & portfolio.

## 👤 Author

Jonathan Alvios
AI Enthusiasts & Data Analyst