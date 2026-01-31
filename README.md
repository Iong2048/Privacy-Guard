
# PrivacyGuard – Automated PII Redaction using AI

PrivacyGuard is an **AI-based system for automatic detection and redaction of Personally Identifiable Information (PII)** from high-resolution document images such as Aadhaar cards, ID documents, and certificates.
The system combines **computer vision, OCR, and natural language understanding** to accurately identify and securely redact sensitive personal data in real-world, noisy documents.

---

## 🔍 Problem Overview

With the rapid growth of digital documentation, exposure and misuse of **PII** (names, addresses, Aadhaar numbers, dates of birth, etc.) has become a serious privacy risk.
Traditional redaction methods—manual masking or rule-based approaches—fail to scale and perform poorly on **multilingual, low-quality, and unstructured documents**.

PrivacyGuard addresses this gap using a **hybrid AI pipeline** that is accurate, efficient, and suitable for privacy-critical domains.

---

## 💡 Solution Approach

PrivacyGuard uses a **multi-stage redaction pipeline**:

1. **Image Preprocessing**

   * Noise removal, contrast enhancement, skew and rotation correction using OpenCV
   * Improves OCR accuracy on high-resolution and degraded scans

2. **Visual PII Detection (Computer Vision)**

   * Fine-tuned **YOLOv5, YOLOv8, and YOLOv11** models
   * Detects visual PII such as ID numbers, photos, signatures, and document regions
   * Trained end-to-end on a custom PII dataset

3. **Textual PII Detection (OCR + NER)**

   * Hybrid OCR pipeline combining deep-learning OCR and Tesseract
   * Transformer-based **Named Entity Recognition (NER)** for names, addresses
   * Rule-based methods for structured identifiers (Aadhaar number, DOB)

4. **Secure Redaction**

   * Sensitive regions are permanently masked or blurred
   * Layout and document readability are preserved

---

## 🧠 Models Used

* **YOLOv5** – Best overall balance of precision, recall, and localization accuracy
* **YOLOv8** – Efficient, anchor-free detection suitable for lightweight deployments
* **YOLOv11** – Context-aware detection using Vision Mamba and graph-based reasoning

YOLOv5 consistently delivered the most reliable performance across training, validation, and testing.

---

## 📊 Dataset & Training

* **Custom PII Dataset** (5,000 document images)

  * Train: 4,000
  * Validation: 400
  * Test: 600
* Document formats: PDF, JPEG, PNG
* Optimizer: Adam
* Learning rate: 0.001
* Epochs: 100

---

## 📈 Evaluation Metrics

Models were evaluated using:

* Precision
* Recall
* F1-Score
* mAP@0.5
* mAP@0.5:0.95
* Inference speed (FPS)

### Key Results

* **YOLOv5 achieved the highest precision (~99.5%) and mAP@0.5 (~97.7%)**
* Strong generalization across unseen test data
* Robust detection even in noisy, multilingual documents

---

## 🛡 Responsible AI Principles

PrivacyGuard is designed with **Responsible AI** at its core:

* **Fairness:** Diverse document samples reduce bias
* **Privacy:** Minimal data processing with secure access controls
* **Transparency:** Audit trails of detected and redacted entities
* **Robustness:** Multi-layer pipeline ensures reliability
* **Human-in-the-loop:** Manual override to prevent over-redaction

---

## 🚀 Applications

* Government document processing (Aadhaar, certificates)
* Banking and financial services
* Healthcare records
* Compliance with **GDPR, HIPAA**, and privacy regulations

---

## 🛠 Tech Stack

* **Computer Vision:** YOLOv5, YOLOv8, YOLOv11, OpenCV
* **NLP:** OCR, NER, Contextual validation
* **Frameworks:** PyTorch
* **Tools:** VS Code, Git, GitHub

---

## 📄 Publication

**Automated Redaction of PII using AI and Computer Vision**
Publication No: **202541076252** — Intellectual Property India

---

## 📌 Summary

PrivacyGuard demonstrates that **hybrid AI pipelines** combining vision and language models can deliver **accurate, scalable, and explainable PII redaction**.
The system is suitable for real-world deployment in privacy-critical environments and contributes meaningfully to **data protection and responsible AI research**.


