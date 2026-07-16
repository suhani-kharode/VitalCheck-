🩺 VitalCheck — Online Health Advisory System

A web-based Machine Learning application that predicts the risk of **Heart Disease, Diabetes, Kidney Disease, and Liver Disease** from a short clinical questionnaire. Based on your input, the system gives an instant risk estimate and advises whether a medical consultation is recommended.

The project ships with a modern, responsive UI — a gradient hero landing page, disease-specific screening pages, and a clean result screen — built on top of Flask + scikit-learn.

---

## ✨ Features

- 🔮 Disease risk prediction using pre-trained Random Forest models
- ❤️ Four independent screening modules — Heart, Diabetes, Kidney, Liver
- 🎨 Modern, mobile-responsive UI with a sticky navbar, gradient hero sections, and card-based layouts
- ✅ Instant, color-coded result page (green = low risk, red = consult a doctor)
- 🧩 Shared Jinja2 base template — one place to update the navbar/footer across all pages
- ⚡ No database required — fully self-contained, stateless predictions

---

## 🖥️ Tech Stack

| Layer        | Technology                                              |
|--------------|----------------------------------------------------------|
| Frontend     | HTML5, CSS3 (custom design system), vanilla JavaScript   |
| Backend      | Python, Flask                                             |
| ML Models    | scikit-learn `RandomForestClassifier` (pre-trained `.pkl`) |
| Icons/Fonts  | Font Awesome 6, Google Fonts (Inter)                      |

There is no database — each prediction is stateless and computed on the fly from the values submitted in the form.

---

## 🧠 Screening Modules

| Module    | Route              | Prediction Route     | Inputs                                                                                     |
|-----------|---------------------|-----------------------|----------------------------------------------------------------------------------------------|
| Heart     | `/heart`            | `/predict_heart`      | Chest pain type, resting BP, cholesterol, fasting blood sugar, resting ECG, max heart rate, exercise-induced angina |
| Diabetes  | `/diabetes`         | `/predict_diabetes`   | Age, hypertension, heart disease history, smoking history, BMI, HbA1c level, blood glucose level |
| Kidney    | `/kidney`           | `/predict_kidney`     | Blood pressure, specific gravity, albumin, blood sugar, red blood cell count, pus cell count, pus cell clumps |
| Liver     | `/liver`            | `/predict_liver`      | Total/direct bilirubin, alkaline phosphotase, ALT, AST, total proteins, albumin, albumin-globulin ratio |

Each model was trained with a `RandomForestClassifier` — see `Models/` for the training scripts and `DataSet/` for the source data used.

---

## 📁 Project Structure

```
Online-Health-Advisory-System-main/
├── app.py                      # Main Flask application (routes + prediction logic)
├── requirements.txt            # Python dependencies
├── templates/
│   ├── base.html                # Shared layout: navbar, footer, common head tags
│   ├── p.html                    # Home / landing page
│   ├── heart.html                # Heart disease screening form
│   ├── Diabetes.html             # Diabetes screening form
│   ├── Kidney.html               # Kidney disease screening form
│   ├── Liver.html                # Liver disease screening form
│   └── result.html               # Prediction result page
├── static/
│   ├── css/style.css             # Design system / all styling
│   ├── js/script.js              # Mobile nav toggle
│   └── images/                   # (optional) legacy image assets
├── Models/                     # Model training scripts
│   ├── Heart_Disease.py
│   ├── Diabetes.py
│   ├── Kidney_Disease.py
│   └── Liver_Disease.py
├── DataSet/                    # Training datasets (CSV)
├── heart.pkl                   # Trained heart disease model
├── diabetes.pkl                 # Trained diabetes model
├── kidney.pkl                   # Trained kidney disease model
└── liver.pkl                    # Trained liver disease model
```

---

## 🚀 How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/suhani-kharode/Online-Health-Advisory-System.git
   cd Online-Health-Advisory-System
   ```

2. **(Recommended) Create a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate   # on Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the Flask app**
   ```bash
   python app.py
   ```

5. **Open your browser and go to**
   ```
   http://127.0.0.1:5000/
   ```

---

## ⚠️ Disclaimer

VitalCheck provides an **informational risk estimate only** — it is **not** a medical diagnosis. Always consult a qualified physician for medical advice.

---

Complete demo on YouTube: https://www.youtube.com/watch?v=A62g2SgIL8Q
