# Image Quality Classifier with Auto-Tagging.

## 📌 Overview

This project implements an **Image Quality Classification system with automatic tagging** using machine learning and computer vision techniques. The pipeline evaluates image quality and assigns interpretable tags (e.g., *blurry*, *low-light*, *overexposed*) to support downstream automation such as dataset filtering, quality monitoring, and ML data validation.

The solution is designed to be:

* **Automatable** – suitable for batch and pipeline execution
* **Modular** – separable feature extraction, inference, and tagging layers
* **Scalable** – extendable to large image datasets

---

## 🎯 Objectives

* Detect and classify image quality issues
* Auto-generate human-readable quality tags
* Reduce manual dataset inspection
* Improve training-data reliability for computer vision models

---

## 🧠 System Design

### High-Level Pipeline

```
Input Images
     ↓
Preprocessing
     ↓
Feature Extraction
     ↓
Quality Scoring / Classification
     ↓
Auto-Tag Generation
     ↓
Structured Output (CSV / JSON)
```

### Key Components

| Component          | Description                                 |
| ------------------ | ------------------------------------------- |
| Preprocessing      | Resize, normalization, grayscale conversion |
| Feature Extraction | Blur metrics, brightness, contrast, noise   |
| Classifier         | Rule-based / ML-based quality classifier    |
| Auto-Tagger        | Maps scores → semantic quality tags         |
| Output             | Persisted labels for downstream use         |

---

## 🧪 Quality Metrics Used

* **Laplacian Variance** → blur detection
* **Mean Pixel Intensity** → brightness
* **Histogram Spread** → contrast
* **Noise Estimation** → image degradation

These metrics are interpretable and reproducible, making the system suitable for production diagnostics.

---

## 📂 Project Structure

```
├── Image_Quality_Classifier_with_Auto_Tagging.ipynb
├── README.md
├── sample_images/
├── outputs/
│   ├── quality_results.csv
│   └── tagged_images.json
└── requirements.txt
```

---

## ⚙️ Installation

```bash
pip install -r requirements.txt
```

### Dependencies

* Python 3.9+
* OpenCV
* NumPy
* Pandas
* Matplotlib
* Scikit-learn (if ML-based classification is enabled)

---

## ▶️ Usage

### Run Notebook

```bash
jupyter notebook Image_Quality_Classifier_with_Auto_Tagging.ipynb
```

### Output Example

| Image      | Quality | Tags              |
| ---------- | ------- | ----------------- |
| img_01.jpg | Poor    | blurry, low_light |
| img_02.jpg | Good    | well_exposed      |

---

## 📊 Evaluation Strategy

* Threshold-based validation on known degraded images
* Visual inspection benchmarking
* Metric sensitivity testing (blur vs brightness trade-offs)

**Future evaluation extensions:**

* ROC/AUC for supervised labels
* Human agreement scoring

---

## 🚧 Limitations

* Thresholds may require tuning per dataset
* Performance depends on lighting distribution
* Not trained for aesthetic quality (technical quality only)

---

## 🔮 Future Enhancements

* CNN-based image quality assessment (IQA)
* CLIP-based semantic tagging
* Batch inference API (FastAPI)
* Integration with data validation pipelines (Great Expectations)
* Active learning for threshold calibration

---

## 🧩 Use Cases

* Dataset quality filtering before model training
* Automated CV data validation
* Image ingestion pipelines
* Monitoring real-time camera feeds

---

## 📈 Production Considerations

* Batch processing with multiprocessing
* Metric drift monitoring
* Dataset-level quality dashboards
* Threshold versioning

---

## 👤 Author

**Ayush**
Automation Engineer | AI / GenAI Enthusiast

---

## 📜 License

This project is licensed under the MIT License.

---

## ⭐ If this helped you

Consider starring the repository — it helps visibility and encourages further improvements 🚀
