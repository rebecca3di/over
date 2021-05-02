# some-beginners-toy-project

This where I will put some of my codes and notes and thoughts during my progress in machine learning.

### transfer-learning.ipynb

- It is a DaNN approach to draw information from real photos to discriminate human hand drawings.
- The toy dataset consists of 5,000 real RGB photos resized to 32 by 32 as training data. The test data are 100,000 hand scrawls, 28 by 28 in grayscale.
- I tried with a CNN and a small ResNet, accuracy was around 70%, which was not satisfying. Problems could be that training data and test data are not IID, which is a premise for conventional (basic) machine learning.
- DaNN can tackle the problem well, as the network consists of a feature extractor, a domain classifier and a label predictor. The extractor is trained to generate fatures representing training data and test data, in this case, photos and scrawls, to fool out the domain classifier, then feed the features for the label predictor, where the feed can be considered IID.
- A over 96% accuracy can be obtained.
