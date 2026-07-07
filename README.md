# Diet Recommendation System using Machine Learning

A personalized, web-based health and nutrition platform that provides automated, data-driven diet plans. The system uses a highly optimized **Random Forest Classifier** to predict individual diet categories and maps them to complete daily meal menus (Breakfast, Lunch, and Dinner).


## Key Features & Novelty

Unlike standard online generic diet plans, this system introduces advanced personalization layers:
* **Automated BMI Calculation:** Instantly calculates the user's Body Mass Index (BMI) in the backend from raw height and weight inputs.
* **Budget-Level Integration:** Customizes specific daily meal recommendations according to the user's financial capacity.
* **Sleep & Lifestyle Tracking:** Includes rest hours and lifestyle habits as active variables in the recommendation logic.
* **Complete Daily Menus:** Provides full structural food items (Morning, Afternoon, Night) instead of just predicting a simple diet type or name.


## Data Engineering & Preprocessing
To ensure the model learns complex, real-world patterns, a custom, rigorous data pipeline was developed in `diet.ipynb`:

1. **Dataset Merging:** We strategically merged two distinct datasets:
   * `diet_recommendations_dataset.csv` (Clinical and medical attributes like allergies, diseases, and BMI).
   * `GYM.csv` (Fitness-focused data including workout goals and specific meal maps).
2. **Feature Enrichment:** The resulting unified dataset (`merged_diet_dataset.csv`) provided a much richer feature space. This balanced medical constraints with active fitness goals (fat burn, muscle gain).
3. **Outcome:** This data engineering phase was critical in stabilizing the model's variance, dramatically improving the model's learning capability and predictive accuracy across diverse user profiles.


## Model Performance & Results

The Machine Learning engine is built using an ensemble learning approach. It achieves high precision and shows strong generalization capabilities on unseen data:

* **Training Accuracy:** `99.7%` (0.997)
* **Testing Accuracy:** `96.5%` (0.965)

**Detailed Classification Report:**
| Target Diet Class | Precision | Recall | F1-Score | Support |
| :--- | :--- | :--- | :--- | :--- |
| **Balanced** | 1.00 | 0.87 | 0.93 | 53 |
| **Low Carb** | 0.95 | 1.00 | 0.97 | 92 |
| **Low Sodium** | 0.96 | 1.00 | 0.98 | 55 |
| *Macro Average* | *0.97* | *0.96* | *0.96* | *200* |


## Tech Stack Used

* **Frontend:** HTML5, CSS3, JavaScript (Responsive Web Dashboard Layout)
* **Backend Framework:** Python (Flask / Django)
* **Machine Learning Engine:** Scikit-Learn (Random Forest Classifier)
* **Database Management:** MySQL / MongoDB


## System Architecture & Workflow

The execution pipeline follows a streamlined decoupled structure:
1.  **User Input:** The user submits profile information (Age, Height, Weight, Sleep Hours, Budget) via the web front-end UI.
2.  **Processing Layer:** The backend calculates the BMI automatically and structures the data vector.
3.  **ML Model Inference:** The data vector is sent to the trained Random Forest Model to classify the ideal diet category.
4.  **Database Retrieval:** The backend queries the database using the predicted class to fetch matching full meal choices.
5.  **Output Display:** The complete customized morning, afternoon, and evening menu layout is presented cleanly on the web application dashboard.


## Installation & Setup Guide

To run this project locally on your system, follow these steps:

### 1. Clone the Repository
```bash
git clone https://github.com/Syeda-Ather/Diet-Recommendation-System.git
```
### 2. Move into the project
```bash
cd diet-recommendation-system
```
### 3. Install dependencies
```bash
pip install -r requirements.txt
```

## Author
Syeda Ather Fatima
