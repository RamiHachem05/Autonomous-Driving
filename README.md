Weather-Robust-and-Explainable-Object-Detection-for-Autonomous-Driving

📄 Overview
Autonomous driving systems depend strongly on reliable perception; however, modern object detectors (e.g., YOLOv8) often experience significant performance degradation in adverse weather scenarios such as heavy rain, fog, and nighttime conditions. In addition, most existing methods operate as black-box models, providing limited interpretability—an issue that is especially problematic for safety-critical autonomous systems.
This project proposes a Unified Weather-Robust XAI Framework that simultaneously addresses robustness and transparency. Unlike conventional pipelines that handle these aspects independently, the proposed architecture jointly optimizes three essential dimensions:

Adverse Weather Adaptation: achieved through curriculum-based learning.

Uncertainty Quantification: capturing both data uncertainty (Aleatoric) and model uncertainty (Epistemic).

Real-Time Explainability: integrating class-conditioned saliency maps directly within the inference process.

🚀 Key Features

Curriculum-Based Adaptation: Implements a progressive training scheme that transitions from clear-weather data to synthetic weather augmentations, and ultimately to real-world adverse datasets (DAWN, ACDC, CADC).

Dual-Uncertainty Estimation: Combines Aleatoric and Epistemic uncertainty into a single unified Risk Score, enabling the system to differentiate between reliable detections and uncertain or hazardous scenarios.

Embedded XAI: Produces real-time Grad-CAM visual explanations during inference, providing justification for each detection and ensuring attention is placed on meaningful vehicle features (e.g., chassis, wheels) rather than irrelevant background regions.

Weather-Aware Preprocessing: Applies illumination correction, de-raining techniques, and contrast normalization to enhance degraded inputs.

📊 Performance

Accuracy: Reached 74.2% mAP under severe weather conditions (Rain/Fog).

Improvement: Surpassed baseline object detectors by more than 12%.

Real-Time: Achieves 29 FPS on NVIDIA Jetson AGX Xavier with a low inference latency of 33 ms, meeting real-time deployment requirements.

🛠️ Architecture
The framework is composed of three tightly coupled modules:

Weather-Aware Preprocessing Module (MW): Normalizes and enhances weather-degraded inputs.

Uncertainty-Aware Detection Module (MU): Outputs bounding boxes along with corresponding risk scores.

Explainability Generation Module (ME): Generates spatial explanation maps for interpretability.

📚 Datasets Used

DAWN: A diverse dataset focused on adverse weather conditions.

ACDC: An adverse conditions dataset with correspondence annotations.

CADC: Canadian Adverse Driving Conditions dataset.
