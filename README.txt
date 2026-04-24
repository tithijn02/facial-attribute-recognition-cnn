Facial Attribute Recognition - Code Breakdown

*Note-We refrained from uploading the images folder because our file size is 700 MB, while the upload limit is only 400 MB which resulted in prolonged upload times.*

Project Overview
----------------
This project implements Facial Attribute Recognition using a Convolutional Neural Network (CNN). 
The model is trained to predict facial keypoints using the CelebA dataset.

Step-by-Step Code Execution
---------------------------

1. Import Necessary Libraries
   - Import essential Python libraries including:
     - numpy, pandas (data handling)
     - PIL (image processing)
     - matplotlib (visualization)
     - tensorflow.keras (deep learning framework)

2. Define Dataset Paths and Variables
   - Specify dataset paths:
     - Keypoints CSV File: Contains facial landmark coordinates.
     - Image Directory: Contains images used for training.
   - Set image size and processing parameters.

3. Load Key Points Dataset
   - Read the CSV file containing facial key points using pandas.read_csv().
   - Limit dataset size for faster computation.

4. Load and Preprocess Images
   - Load images using PIL and resize them while maintaining aspect ratio.
   - Convert images to NumPy arrays and normalize pixel values [0,1].
   - Store processed images in a list and convert to an array.

5. Split Data into Training and Testing Sets
   - Use train_test_split() to divide images and key points:
     - 80% Training Data
     - 20% Validation Data

6. Define CNN Model
   - Create a Sequential CNN model with:
     - Conv2D layers for feature extraction
     - MaxPooling2D for downsampling
     - Dropout layers for regularization
     - Dense layers to predict key points
   - Compile the model with:
     - Loss Function: Mean Squared Error (MSE)
     - Optimizer: Adam (Learning rate = 0.001)
     - Metric: Mean Absolute Error (MAE)

7. Train the Model
   - Train the CNN model with:
     - Batch Size: 32
     - Epochs: 20
   - Monitor validation loss to track overfitting.

8. Evaluate and Visualize Model Performance
   - Evaluate the model using MAE.
   - Plot Training vs Validation Loss to check for overfitting.

Usage Instructions
------------------
1. Install Required Libraries:
   requirements.txt

2. Run the Python Script to Train the Model:
   python facial-attribute-recognition-using-cnn.py

3. Evaluate the Model using Test Images.

4. Analyze the Model Performance using Plots.
