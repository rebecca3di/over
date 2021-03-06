# some-beginners-toy-project

This is where I will put some of my codes and notes and thoughts during my progress in machine learning.

You may find that sometimes the same work are carried out with Pytorch and also Paddlepaddle, and they can vary in time consumption. This can be due to projects with Pytorch are run on my laptop, equipped with a pitiful NVIDIA GeForce MX150, while the others are run on Tesla V100 provided by the owner of Paddlepaddle. Certainly different frameworks can differ in speed but I presume it should be a tiny one comparing to the huge gap of device capability.

### transfer-learning.ipynb

- It is a DaNN approach to draw information from real photos to discriminate human hand drawings.
- The toy dataset consists of 5,000 real RGB photos resized to 32 by 32 as training data. The test data are 100,000 hand scrawls, 28 by 28 in grayscale.
- I tried with a CNN and a small ResNet, accuracy was around 70% (k-fold, validation accuracy on one of the folds), which was not satisfying. Problems could be that training data and test data are not IID, which is a premise for conventional (basic) machine learning.
- DaNN can tackle the problem well. As the network consists of a feature extractor, a domain classifier and a label predictor, where the extractor is trained to generate fatures representing training data and test data, in this case, photos and scrawls, to fool out the domain classifier, then feed the features to the label predictor, when the feed now can be considered IID. The notebook demonstrates the job done by the extractor with a PCA representation.
- An over 96% accuracy on the training dataset can be obtained, however the model can still get confused by objects with less-definitive traits.
- You may obtain the dataset [here](aistudio.baidu.com/aistudio/datasetdetail/75815).

### categorization.ipynb
- It is a CNN baseline and small ResNet improvement used to categorize food photos. (Food-11)
- Training set, validation set and testing set seperately includes 9,866, 3,430 and 3,347 RGB pictures in 11 categorizations.
- Tried with several lr-schedulers, however no obvious improvement seen.
- Still improving.
- You may obtain the dataset [here](aistudio.baidu.com/aistudio/datasetdetail/76103).
