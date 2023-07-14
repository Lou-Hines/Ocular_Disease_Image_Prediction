# Ocular_Disease_Image_Prediction
# Ocular Disease Prediction with CNNs
By Lou Hines
July 14, 2023

## Optimizing Models to Predict Ocular Disease
Artificial Intelligence shines brightly in the medical profession, with recent technologies creating advanced mRNA vaccines, predicting diabetes well ahead of traditional techniques, and catching missed heart attack diagnoses. In this spirit, we optimized models using OCT retinal scans to detect CNV (Inflammatory Choroidal Neovascularization), a degenerative ocular disorder commonly resulting in blindness, using a subset of data from Cell. Especially given SARS-CoV-2, early and quick detection of virally-induced disorders is vital for effective treatment.

The role of viruses and persistent inflammation in disease is proving to be a game-changer in the field of medicine, with CNV being of particular interest due to the role of viruses in its pathogenicity and disease progression. 

## Data Overview
We utilized OCT retinal scans and used these to develop a model that can predict CNV, an ocular disease. EDA was conducted on these images to understand the features that would be critical in prediction. The features focused on included:

- Contrast: Measures the local intensity variations in an image.
- Dissimilarity: Measures the difference or diversity in pixel intensities between neighboring pixels.
- Homogeneity: Quantifies the similarity or uniformity of pixel intensities within an image.
- Energy: Measures the overall uniformity or smoothness of an image texture.
- Correlation: Measures the linear dependency between pixel intensities in an image.

## Methods
Our primary model was a fairly vanilla Convolutional Neural Network (CNN) with standard filters, kernel sizes, and sequences. We utilized the Adam optimizer, and used softmax and categorical cross-entropy for our output layer and loss function, respectively. 

Other models tried included: 

- CNN without MaxPool: Replaced MaxPool with striding, as per the Springenberg et al paper, which achieved strong results but not an overall improvement compared to our more vanilla model.
- VGG16: Extremely time-intensive, but literature (if not our early results) seems promising. It uses pre-trained datasets.
- CNN with increased filters: Doubled filter sizes in input and hidden layers in different models. Did not see improvement.
- CNN with increased learning rate: Adjusted from default .001 to .01. This resulted in a major drop-off in scores.
- CNN without downsampling or striding (1 Epoch): Achieved strong results (average test accuracy of 98.5% over 100 evaluations) but was too time-consuming and we needed more epochs to feel confident in our outcome.

## Results & Recommendations
Our models performed well on the task, and we believe that the use of such models can save time and resources in the medical field. Accurate diagnoses can be made quickly, allowing medical professionals to see more patients and begin treatment faster. 

For future work, we plan to further experiment with VGG16, visualize activation layers for better model understanding, optimize for image noise, and run more epochs to improve false negatives.

## Contact Info
For any questions or further discussion, feel free to reach out:
- Lou Hines, Data Scientist
- Email: lou.m.hines@gmail.com
- [LinkedIn](https://www.linkedin.com/in/lou-hines-data-scientist/) 

## Repository Navigation
- [Data Source](https://www.cell.com/)
- [Final notebook](https://github.com/Lou-Hines/Ocular_Disease_Prediction.ipynb)
- [Presentation](https://github.com/Lou-Hines/Ocular_Disease_Prediction/presentation.pdf)
