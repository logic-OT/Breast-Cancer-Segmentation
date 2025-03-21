# Breast-Cancer-Segmentation
An image segmentation procedure that uses a 4-layered U-Net Architecture to segment tumours from Ultrasound images of the breast.

![tumourbw](https://user-images.githubusercontent.com/61668807/211711623-2197f57f-8aba-4a96-a5c0-e44aae8f0ebf.png)
![maskbw](https://user-images.githubusercontent.com/61668807/211711632-2ff9d1ad-80d3-470b-b713-8cd44c17aa22.png)

<b> Note: The BREAST TUMOUR SEGMENTATION notebook above contains an idepth explanation of the proposed procedure. This the a dumped down version of the contents in the notebook </b>


## Data
- The data used in this project contains 210 images of malignant tumours, 437 images of benign tumours and 133 images of normal Ultrasounds creating a total of 780 images
- Each image in the dataset contains varying image sizes ranging from 200x150 to 300x300.
- A Ultrasound can have more than one mask depending on the number of tumours present in the image
- each Ultrasound image is saved as a jpg file instead of the usual dicom format
- The dataset is available [here](https://drive.google.com/drive/folders/1Q75Eiz0PPBLHvDZfrIvWA9zqtBuw_8W7?usp=sharing)

## Preprocessing
- The images are first resized to a dimension 224x224
- Each image is then coverted to grayscale for simplicity
- The masks are binarized. That is, each pixel is changed to either be 0 or 1
- The Ultrasounds are the normalised between 0 and 1

## Model Training
A 4-layered generic U-Net Architecture is trained to effectively segment the tumours. The various levels have fiilter sizes of 32, 64, 128, 256 respectively

## Results
- The Model achieved a training dice score of 92%
- The Model achieved a testing dice score of 74%

## Example output
![tumour](https://user-images.githubusercontent.com/61668807/211706649-5d809f94-5f25-4d3c-8c9a-d6b6e8d2b4e6.png)
![mask](https://user-images.githubusercontent.com/61668807/211706663-d321c865-ffe2-4edd-a6ba-8e73cb94dfdd.png)
![segmented](https://user-images.githubusercontent.com/61668807/211706675-690c5ada-c65b-4738-9d3a-2e6561f4093f.png)

# Key Insights
- The model is really good as identifying isolated/exposed tumours 
- The model is good at getting the shape of the the tumour but lacks the fine outlines on the prediction
-  The model fails to identify tumours partially hidden by tissue. This is evident in plot_test(11)
- The model also mistakens writings or drawings as an indication of a tumour. This is evident in plot_test (29)
- The model to generally overfits to the training images
