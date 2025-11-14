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

Model file:  "best_model.keras" in the "Link Model.txt" file


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

## Screenshots
<img width="1895" height="1035" alt="Screenshot 2025-11-14 163354" src="https://github.com/user-attachments/assets/e1472f30-11e7-4b38-8ad6-70814c9c1cd1" />
<img width="1900" height="1035" alt="Screenshot 2025-11-14 163414" src="https://github.com/user-attachments/assets/7228941b-3659-48ab-b734-411c1e68b7a8" />
<img width="1896" height="1040" alt="Screenshot 2025-11-14 163210" src="https://github.com/user-attachments/assets/19db47ef-b8e8-4a30-a889-54050bb07e8f" />
<img width="1894" height="1039" alt="Screenshot 2025-11-14 163235" src="https://github.com/user-attachments/assets/ea72945b-c040-458a-9449-a2e7167a7dc5" />
<img width="1886" height="1040" alt="Screenshot 2025-11-14 163328" src="https://github.com/user-attachments/assets/3c3235cd-0fb5-4ffc-863e-cafff50421a3" />
<img width="1882" height="1043" alt="Screenshot 2025-11-14 163431" src="https://github.com/user-attachments/assets/4a0d836d-389f-4964-9c26-83634e9ea074" />

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
