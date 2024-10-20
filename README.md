# Flipcart-Grid-Robotics-Challenge-


Dataset Links:- 
1. fresh-and-stale-images-of-fruits-and-vegetables: https://www.kaggle.com/datasets/raghavrpotdar/fresh-and-stale-images-of-fruits-and-vegetables
2. fruit-and-vegetable-image-recognition: https://www.kaggle.com/datasets/kritikseth/fruit-and-vegetable-image-recognition



#**Introduction:**

# **1. Grocer Lens:** Product Attribute Extraction
Objective: To extract product details like weight, height, volume, and other relevant specifications from grocery product images.

Dataset Collection: The dataset was sourced from e-commerce platforms (Flipkart and Amazon) and includes the following key fields:

Image URL: Direct link to the product image.
Entity Name: Attribute to be extracted (e.g., weight, volume).
Group ID: Unique identifier grouping similar entities for classification.
Image Processing & Augmentation: Images were enhanced using rotation (0°, 90°, 180°, 270°) and contrast adjustments to improve text extraction. Text is extracted using EasyOCR, followed by regex-based unit extraction and correction of OCR misinterpretations.

# Workflow:

Text extraction using EasyOCR.
Unit extraction and conversion using regex.
Parallel processing with ThreadPoolExecutor for efficiency.
Fuzzy matching and Logistic Regression were used to train a model for matching extracted data with expected values.
Evaluation:

A Logistic Regression model was trained, achieving high accuracy through cross-validation.
Visualizations using scatter plots were employed to compare predicted vs. actual values.


# **2. FruitVeggieVision:** Fruit and Vegetable Classification
Objective: To classify images of fruits and vegetables and predict their specific type.

Dataset Collection: The dataset, sourced from Kaggle, contains images categorized into different classes (e.g., apple, banana, carrot). It was divided into training, validation, and test sets to ensure model generalization.

Data Augmentation: Real-time augmentation techniques such as rescaling, rotation, flipping, zooming, and brightness adjustments were applied to increase data variability and enhance model robustness.

Model Architecture: A CNN-based model was built using the following layers:

Rescaling, Convolutional, and MaxPooling layers for feature extraction.
Dropout layers to reduce overfitting.
Dense layers to predict class probabilities.
Model Training:

The model was compiled with the Adam optimizer and trained on 30 epochs, achieving a final accuracy of 97%.
A classification report showed strong precision and recall across classes, though slight misclassifications were observed between similar classes like corn and sweetcorn.
Evaluation:

A confusion matrix was used to identify class-specific misclassifications.
The model demonstrated effective learning, with both training and validation accuracy increasing over time.



# **3. FreshTrack Vision:** Freshness Detection
Objective: To classify fruits and vegetables as fresh or stale based on images.

Dataset Collection: The dataset contains images of six fresh and six stale categories (e.g., fresh apple, stale apple) from the Kaggle fresh-and-stale images dataset.

Data Augmentation: The dataset was augmented using random transformations, including rotation, width/height shifts, shear, and zoom, enhancing model generalization.

Model Architecture: A CNN-based model with Conv2D and MaxPooling layers was constructed to extract features, followed by a fully connected layer and dropout to avoid overfitting. The output layer used softmax activation to predict 12 categories.

Model Evaluation:

Training Accuracy: 91.88% across all categories.
Freshness Accuracy: 94.66%, with a strong ability to differentiate fresh vs. stale items.
Model Performance:

Training loss decreased consistently over time, while accuracy improved steadily.
The model performed well in distinguishing between fresh and stale categories.
