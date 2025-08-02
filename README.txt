
Facial Feature Detection - Final Project
-----------------------------------------

This solution detects THREE facial features from an uploaded image:

1. Gender Classification        → Male / Female  
2. Glasses Detection           → Glasses / No Glasses  
3. Shirt Color Classification  → Black, Blue, White, Red, Green


 ## Folder Structure:

.
├── models/
│   ├── gender_model.h5
│   ├── glasses_model.h5
│   └── shirt_color_model.h5
├── images/
│   └── testing/
│       └── sample_image.jpg
├── run_all.ipynb       <-- Notebook to run predictions
├── run_all.py          <-- (Optional) Script version
├── README.txt
└── requirements.txt    <-- (if applicable)


How to Run the Notebook:

1. Open `run_all.ipynb` in Jupyter Notebook or Google Colab.
2. Make sure the 3 model files are present in the `models/` folder.
3. Replace the image path in the last cell with your test image path:
   Example:
     predict_all("images/testing/sample_image.jpg")
4. Run all cells.
5. The image will be displayed with predictions:
     - Gender
     - Glasses
     - Shirt Color

How It Works:

- All models were trained separately using TensorFlow/Keras.
- Image is read using OpenCV, resized to (224x224), and normalized.
- The pre-trained models are loaded using `load_model()`.
- Output is decoded using `np.argmax(prediction)`.
- Results are printed and shown on the image using Matplotlib.


Troubleshooting:

- If you get a shape error, make sure all models were trained on (224, 224, 3) images.
- If shirt color returns "Unknown", the predicted index may be outside the defined list.
  Make sure the list in code matches your shirt model's training labels.

Example Output:

Gender: Female  
Glasses: Glasses  
Shirt Color: Blue
