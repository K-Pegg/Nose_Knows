# The Nose Knows: Dog Breed Classifier
## Overview
In this project, I have used Keras and Tensorflow to develop, train, and test a convolutional neural network tailored for dog breed prediction. The application of AI in predicting dog breeds holds promise for mitigating the expenses associated with genetic testing. Leveraging machine learning techniques may uncover subtle features that humans cannot perceive. In this endeavor, I will explain the methodology for my process for classifing images of the diverse dog breed images.
## Business Problem
Rescues and animal shelters face a significant challenge in accurately identifying the breeds of dogs in their care, typically relying on the judgement of staff members and based solely on appearance. Genetic testing can provide more definitive answers, but this presents a costly solution. The reliance on subjective assessment and expensive genetic testing can contribute to inefficiencies and financial strain for both rescues and adopters. The opportunity exists to address this issue through the development of a machine learning-based diagnostic tool, capable of identifying dog breeds from images. Such a tool could alleviate the financial burden associated with genetic testing while providing rescues and potential adopters with reliable breed information. This can ultimately facilitate a more informed adoption decision for future dog owners.
## Data
- [Dog photo dataset](https://www.kaggle.com/competitions/dog-breed-identification/data) from kaggle
- 120 dog breeds
- 20,000+ photos total: fairly evenly split between training & testing sets
- 10,222 in training set, labels CSV
- 10,357 in testing set
Fortunately, there was no need for data cleaning as the labels CSV did not contain any null values. To seamlessly associate labels with the corresponding image, I added '.jpg' to the image IDs in the dataframe, ensuring a smooth mapping process. 
## Initial Model
- Training loss: 0.05
- Training Accuracy: 98.86%
- Validation loss: 18.23
- Validation Accuracy: 5.04%
- Test loss: 0
Unfortunately, accuracy evaluation was unfeasible due to the absence of labels for the testing data. In an attempt to enhance the model's performance, I experimented with training the base model using more epochs and smaller batch sizes, albeit with negligible impact. Additionally, I conducted a practical test by inputting an image of my own dog into the model. Despite my dog being a Labrador, the model incorrectly predicted him as a Bernese Mountain Dog with a probability of 100%. May we all be so confident...
## Other Models
During the refinement process, several enhacements were made the the model architecture, including the addition of an extra layer, incorporation of dropout and L2 regularization, as well as an increase in the number of nodes. Furthermore, data augmentation techniques were implemented to assist in training of the model: random flipping, rotation, contrast, and zoom. Various train-test splits were explored, with testing data in the training process.
Although accurate assessment was impeded by the absence of labels for the testing data, efforts to mitigate overfitting were successful, resulting in a real modest improvement in validation accuracy. Notably, the model achieved a training lostt of 2.74 with an accuracy of 30%, while the validation loss stood at 4.86 with a validation accuracy of 9.03%.
Subsequent iterations saw the introduction of a new categorical column for dog breeds (e.g., herding, working, sporting, non-sporting, hound, terrier, toy, and wild) . I aimed to reduce the number of classes in hopes that it would help the model have better performance. This refinement led to a notable increase in accuracy for both the training and validation data. Specifically, the model achieved a reduced training loss of 1.495 with an accuracy of 43.78%, while the validation loss decreased to 1.997 with a validation accuracy of 28.08%.
Despite these improvements, a notable misclassification occured where my Labrador (sporting) was identified as a terrier with a 100% probability, highlight the ongoing need for refinement and optimization.
## Final Model
- unsure of final model just yet
## Evaluation
Due to the absence of labels for the testing data, a comprehensive evaluation of the model's accuracy was unattainable. Furthermore, the sample of images used for testing purposes exhibited inaccuracies, showing to erratic probability distributions. In an effort to gain insights into model performance, a comparison with a pre-trained model will be introduced (at some point).
- Add comparison to pre-trained model
## Conclusion
The current model is deemed unsuitable for production deployment due to its inconsistent performance and frequent incorrect predictions. Notably, there exists a substantial disparity in accuracy between the training and validation sets, approximately 15%.
## Next Steps
The following steps are planned to refine the model and enhance its performance:
1. Generating a label CSV for the testing data to enable comprehensive evaluation
2. Implementing further tuning strategies
   - additional layers and/or nodes
   - extending training duration
   - leveraging pre-trained models to improve prediction accuracy
3. Transitioning to web app production to facilitate user-friendly interface & access
4. Incorporating mixed breeds into the model to broaden its scope and improve breed identification accuracy
