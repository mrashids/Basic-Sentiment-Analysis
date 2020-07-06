# Basic-Sentiment-Analysis
Created, trained, and evaluated a Neural Network model that, after the training, was able to predict movie reviews as either positive or negative reviews - classifying the sentiment of the review text.

Dataset:
The imported dataset is easily accessible in keras. After unloading I unpacked it to populate the training set and the test set. Both the training and test set have 25,000 examples each.
When loading the dataset I set the number of words to 10,000.This means that only the most common 10,000 words from the bag of words were used and the rest were ignored.

The developers at Keras already did some pre-processing in the data and had assigned unique numeric values to each word

Decoding the Reviews:
Decode numeric representation of the examples back into text. Decoding is just for my reference so that I can read a couple of reviews and see if their labels seem to make sense.
For the decoding, I created a dictionary with key value pairs like the word index imported. Except this new dictionary had the word index values as keys and keys as values.

Padding the Examples:
The maximum length of 256 words was set for a review and 'the' as added to the reviews with fewer words to expand it's length to 256. 'the' was used as it is just an article and holds no inherent meaning.

The input features are a bag of words and the model will make the predictions based on these features. If a particular set of features is a negative review or positive review. So, as it trains, it will start to assign some “meaning” to certain words which occur often in certain types of reviews. Maybe a word like “wonderful” will influence the model into thinking that the review is more positive, maybe a word like “terrible” will influence the network into thinking that the review is more negative. So, as it trains, it will assign how much influence and what influence various words in our vocabulary will have on the output.

Word Embedding:
An embedding layer will try to find some relation between various words. We are looking to find an embedding for 10,000 words, and we are trying to learn 16 features from those words. Then, all the words are represented as these feature vectors. The embedding layer will learn a 10000 by 16 dimensional Word Embedding where each word has a feature representation of 16 values.

Creating and Training the Model: 
I used the sequential class from Keras. And I also imported a few layers were needed. We know, I needed an Embedding layer (used 16 dimension for the feature representations), needed a pooling layer which converted feature representations of 10,000 by 16 to a 16 dimension vector for each batch that was fed into a Dense layer with a rectified linear unit activation. Finally.Another dense layer with 'sigmoid' activation function to gives a binary classification output for the two classes. number of Epochs was set to 20.

Prediction and Evaluation:
We split the training set into sets; training set and validation set (20%) . Display the accuracy of our model during training for both the training and the validation set.
after predictig the classes in testing set the model came out with the accuracy of 84.175%.
