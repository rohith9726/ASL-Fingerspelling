# ASL-Fingerspelling
DS4420 Final Project


Abstract:

In this write-up, we create CNN models in order to classify images of ASL fingerspelling. Using images from the Kaggle dataset: https://www.kaggle.com/mrgeislinger/asl-rgb-depth-fingerspelling-spelling-it-out, and inspired by the workbook “Experimenting With CNNs” which used the same data, we replicate and expand the analysis in the workbook. In particular, we analyzed the effects of dropout rate on accuracy of CNN models, and witnessed the effects of using different sources of images for training and testing sets. 

Intro:

Our data set consists of 5 different people and their signings for each respective letter(excluding a couple that require a range of motion to communicate). We wanted to be able to translate sign language to English. It enables us to bridge the gap between those who rely on sign language to communicate, and those who have not been able to learn the language but either have business that requires them to know it or simply people who wish to interact with those hard of hearing without a physical aid present. We hope this will lay the foundation for interpreters that operate further off of this, perhaps that can enable translation both ways. Studies have shown that use of sign language is very beneficial for cognitive development at a young age and thus progression of technical aids in this area would be helpful.In short it’s not just the added utility of more universal communication, but also about lowering these communication barriers and perhaps benefitting from them developmentally.

Experimental setup:

The data set consists of 65,589 different images, where each image shows a hand signing one of 24 letters in ASL. We loaded the images into an array, after converting them to grayscale and resizing them to 32 by 32. These changes were made in order to improve the runtime of our CNN models. We created 4 different CNN models which only differed by dropout rates. The CNNs used maxpool and convolution layers in order to classify each image into one of 24 categories, each class representing a different ASL letter. 

The 4 models consisted of a replication of a model in the Kaggle workbook, a model with no dropout, a model with “too much” dropout, and a model with optimal dropout.

We ran each of these models two seperate times. The first was run on training data from all 5 people(A-E), as well as testing and validation(60/20/20). In the second run we split the data into training on the first 3(A-C). Next, the validation data and testing data was each assigned a person(D and E). Each model was run for 25 epochs on the training data, and then run on the testing data.
