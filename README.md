This project implements a Deep Learning pipeline using TensorFlow and Keras and CNN to classify soil images into four distinct categories and recommend suitable crops based on the identified soil type.

Key Implementation Steps:

Data Loading & Preprocessing: Loaded a dataset of 1,737 soil images spanning 4 classes (Alluvial_Soil, Black_Soil, Red_Soil, and Yellow_Soil) using image_dataset_from_directory. Prepared and standardized the input dimensions to (224 \times 224)(224 \times 224) with VGG16-specific preprocessing applied.
Data Augmentation: Integrated standard augmentations (RandomFlip and RandomRotation) directly into the Keras preprocessing pipeline to prevent overfitting and improve model generalization.
Transfer Learning with VGG16: Leveraged a pre-trained VGG16 backbone initialized with ImageNet weights. Fine-tuned the network by keeping the deeper layers trainable while freezing the earlier feature extraction layers.
Model Architecture: Built a sequential classifier appending a custom head (Flatten, Dense layer with ReLU, Dropout for regularization, and a final Softmax output layer) onto VGG16.
Training & Evaluation: Trained the model using the Adam optimizer and Sparse Categorical Crossentropy loss, achieving an outstanding evaluation accuracy of ~99.39% on the validation split.
Interactive Inference: Integrated an interactive image upload option. When a user uploads a new soil image, the model predicts the soil class, visualizes the prediction confidence with a bar chart, and automatically recommends optimal crops for that soil type (e.g., recommending Maize, Groundnut, and Rice for Yellow Soil).
