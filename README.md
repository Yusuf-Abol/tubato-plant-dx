# **Tubato Plant Dx** 🌱

AI-powered plant disease detection system for identifying leaf diseases from images using deep learning.

---

## **📌 Overview**

Tubato Plant Dx is an end-to-end machine learning project that:

* Loads and preprocesses plant leaf images
* Trains deep learning models (CNN / transfer learning) to classify diseases
* Evaluates performance with standard metrics
* Deploys as a **REST API** using FastAPI for real-world usage

This project is designed with **clear structure** for experimentation and deployment, making it easy to reproduce results and scale.

---

## **📂 Project Structure**

```
tubato_plant_dx/
│
├── data/                  # Datasets (raw, processed, external)
├── notebooks/             # Exploratory Data Analysis & prototyping
├── src/                   # Core code (data, features, models, utils)
├── experiments/           # Saved runs with configs, logs, and checkpoints
├── deployment/            # API, Docker, and serving scripts
├── configs/               # Hyperparameters and settings
├── tests/                 # Unit tests
├── requirements.txt       # Dependencies
├── README.md              # Project documentation
└── .gitignore
```

---

## **⚙️ Installation**

1. **Clone the repo**

```bash
git clone https://github.com/<your-username>/tubato_plant_dx.git
cd tubato_plant_dx
```

2. **Create a virtual environment & activate it**

```bash
python -m venv .venv
source .venv/bin/activate   # Mac/Linux
.venv\Scripts\activate      # Windows
```

3. **Install dependencies**

```bash
pip install -r requirements.txt
```

---

## **📊 Dataset**

Place your dataset in the `data/raw/` folder.
For example:

```
data/raw/
    ├── healthy_001.jpg
    ├── healthy_002.jpg
    ├── diseased_001.jpg
    └── ...
```

---

## **🚀 Training a Model**

1. **Preprocess data**

```bash
python src/data/data_loader.py
```

*(Adjust script to save processed images into `data/processed/`)*

2. **Train model**

```bash
python src/models/train.py
```

The trained model will be saved to `experiments/exp_xxx/model.pth`.

---

## **🧪 Evaluating the Model**

Run evaluation metrics:

```bash
python src/evaluation/metrics.py
```

---

## **🌐 Deploying the API**

1. **Run FastAPI locally**

```bash
uvicorn deployment.api.app:app --reload
```

2. **Test with cURL or Postman**

```bash
curl -X POST "http://127.0.0.1:8000/predict" \
     -F "file=@path_to_leaf_image.jpg"
```

---

## **📦 Docker Deployment**

1. **Build the image**

```bash
docker build -t tubato-plant-dx .
```

2. **Run container**

```bash
docker run -p 8000:8000 tubato-plant-dx
```

---

## **📈 Roadmap**

* [ ] Improve preprocessing pipeline
* [ ] Integrate transfer learning (ResNet, EfficientNet)
* [ ] Add mobile/web interface for farmers
* [ ] Deploy to cloud (AWS/GCP/Azure)

---

## **🤝 Contributing**

Pull requests are welcome! For major changes, please open an issue first to discuss.

---

## **📜 License**

[MIT License](LICENSE)
