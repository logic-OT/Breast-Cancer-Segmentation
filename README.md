# Breast-Cancer-Segmentation
An image segmentation procedure that uses a 4-layered U-Net Architecture to segment tumours from CT-Scan images of the breast.

![tumour](https://user-images.githubusercontent.com/61668807/211706649-5d809f94-5f25-4d3c-8c9a-d6b6e8d2b4e6.png)
![mask](https://user-images.githubusercontent.com/61668807/211706663-d321c865-ffe2-4edd-a6ba-8e73cb94dfdd.png)
![segmented](https://user-images.githubusercontent.com/61668807/211706675-690c5ada-c65b-4738-9d3a-2e6561f4093f.png)

<b> Note: The ... notebook above contains an idepth explanation of the stated procedure. This the a dumped down version of the contents in the notebook </b>

## Data
- The data used in this project contains .. images of malignant tumours, .. images of benign tumours and .. images of normal CT-Scans creating a total of 780 images
- Each image in the dataset contains varying image sizes ranging from 200x150 to 300x300.
- A CT-Scan can have more than one mask depending on the number of tumours present in the image
- each CT-Scan image is saved as a jpg file instead of the usual dicom format

## Preprocessing
- The images are first resized to a dimension 224x224
- Each image is then coverted to grayscale for simplicity
- The masks are binarized. That is, each pixel is changed to either be 0 or 1
- The CT-Scans are the normalised between 0 and 1

## Model Training
A 4-layered generic U-Net Architecture is trained to effectively segment the tumours. The various levels have fiilter sizes of 32, 64, 128, 256 respectively

## Results

## Example output
