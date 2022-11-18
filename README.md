# Data_Challenge---Help_Hematologist_out

Data challenge with a goal to find domain transfer solutions for blood-cell classification.

## Datasets

The datasets used in the challenge are from two publications: 
 - [Acevedo et al., 2020](https://doi.org/10.1016/j.dib.2020.105474): the dataset with ten types of normal peripheral blood leukocytes stained using May Grünwald-Giemsa
 - [Matek et al., 2019](https://doi.org/10.1038/s42256-019-0101-9): the dataset with eleven types of peripheral blood leukocytes (Highly underrepresented classes like atypical lymphocytes and smudge cells were left out)
 - Test dataset provided by the organisers
 
 ## Image preprocessing
 
Before the data analysis, all images were preprocessed with stain_mixup library ("Stain mix-up augmentation" strategy from [Chang et al., 2021](https://doi.org/10.1007/978-3-030-87199-4_11)). The target image was chosen from the test dataset (971.TIF).

## Dataset split

The images contained in each class of our dataset were randomly divided into a test, validation and training datasets: training dataset contained about 70% of the images, the test dataset -- 20%, the validation dataset -- 10%. 

## DatasetGenerator class



The best leap in F1 of prediction was achieved by using circle mask to focus on the signal belonged to the cell, which we need to classify.  

The model used in the study is resnet18 with pretrained weights.
