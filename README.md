# Tumor_Detection
Experiments with several machine learning models for tumor classification.
<br>Used two brain MRI datasets founded on Kaggle.
<br>
<br>The first dataset you can find it <a href="https://www.kaggle.com/navoneel/brain-mri-images-for-brain-tumor-detection">here</a>
<br>The second dataset <a href="https://www.kaggle.com/simeondee/brain-tumor-images-dataset">here</a>

<br><b>About the data:</b>
<br>The first dataset contains 155 positive and 98 negative examples, resulting in 253 example images.The folder yes contains 155 Brain MRI Images that are tumorous and the folder no contains 98 Brain MRI Images that are non-tumorous.
<br>
<br>The second dataset contains 100 positive and 100 negative examples, resulting in 200 example images. The dataset is seperate by test,train and validation and each folder has a hemmorhage_data and non_hemmorhage_data 

# Data Preprocessing
For every image, the following preprocessing steps were applied:
<br>
<br>1. Resize to 250,250,3 (image_width, image_height,channels) because images in the two datasets come in different sizes.
<br>2. Convert image from RGB to grayscale.
<br>3. Use Hog for feature extraction.
<br>
<br>After the preprocessing we use either Principal component analysis (PCA) for feature reduction or chi-squared (chi-2) for feature selection. Also the is a option to use only the hog features.

# Machine Learning Models
Experiments with SVM, Linear-SVM, Random Forest,Logistic Regression using  5-fold cross validation. 

# Metrics
Accuracy, Precision, Recall, Fmeasure, Specificity
# The goal
The goal is try to make the recall equal to 1 . So the FN must be equal to 0. This way the classifier always will spot images that are tumorous

<table>
  <col>
  <colgroup span="2"></colgroup>
  <colgroup span="2"></colgroup>
  <tr>
    <td rowspan="2"></td>
    <th colspan="2" scope="colgroup">Predicted Label</th>
  </tr>
  <tr>
    <th scope="col">No</th>
    <th scope="col">Yes</th>
  </tr>
  <tr>
    <th scope="row">No</th>
    <td>TN</td>
    <td>FP</td>
  </tr>
  <tr>
    <th scope="row">Yes</th>
    <td>FN=0</td>
    <td>TP</td>
  </tr>
