# Forest Fire Detection Using CNN & Edge IoT Prototype

An academic computer vision and embedded system prototype developed in **October 2022** to detect forest fires from image data and trigger remote hardware alerts.

🔗 **[View Notebook & Execution Logs on Kaggle](https://www.kaggle.com/code/akankshabhavsar/forest-fire-detection-using-cnn)**  
📂 **Dataset:** [Wildfire Detection Image Data (Kaggle)](https://www.kaggle.com/datasets/brsdincer/wildfire-detection-image-data)

---

### 1. Computer Vision Pipeline (CNN)
* **Data Preprocessing:** Loaded **1,900 labeled images** (1,832 training / 68 testing) across two classes (`fire: 0`, `nofire: 1`) using Keras `ImageDataGenerator`, rescaling pixel values (`1/255`) and resizing inputs to `150x150` RGB.
* **Model Architecture:** Built a Sequential Convolutional Neural Network (`TensorFlow/Keras`) with 4 `Conv2D` + `MaxPool2D` feature extraction layers, followed by `Flatten`, a 512-unit `Dense` (`relu`) layer, and a binary `sigmoid` output layer.
* **Training & Results:** Compiled with `adam` optimizer and `binary_crossentropy` loss over 10 epochs, achieving **97.27% training accuracy** and **95.59% validation accuracy**.

### 2. Edge Hardware Prototype Architecture
* **Detection Unit:** Raspberry Pi interfaced with a servo-mounted thermal/IR camera to capture and verify suspected fire zones.
* **Communication & Scalability:** Designed for short-range alert transmission via **XBee** modules to a central monitoring node, with scalability to **LoRaWAN** sensor networks for wide-area forest coverage.

### 3. Key Takeaways & Future Improvements
* **Dataset Balance & Quality:** The small validation split (68 images) and challenging background lighting (e.g., orange sunsets) caused noticeable variance in validation loss curves, highlighting the importance of balanced, high-quality labeled data.
* **Transfer Learning:** Replacing custom CNN training with a lightweight pre-trained model (e.g., MobileNet) would significantly reduce training time and optimize inference for Raspberry Pi edge deployment.

---
**Tech Stack:** `Python` · `TensorFlow` · `Keras` · `OpenCV (cv2)` · `NumPy` · `Matplotlib` · `Raspberry Pi`
