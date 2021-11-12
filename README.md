# text-classifier
Jupyter notebook that classifies articles from the BBC archives into one of five categories. It uses basic text tokenizing techniques and a simple dense neural network to get accurate results.

## Dependencies
- csv: Read in a csv file.
- tensorflow: Build, compile, and train a Dense model.
- numpy: Create arrays to hold the article labels.
- matplotlib: Visualize results of model training.

## Dataset
The [dataset](http://mlg.ucd.ie/datasets/bbc.html) consists of 2225 articles from the BBC archives. They belong to five categories: business, entertainment, politics, sports, and tech. Each article is labeled and the dataset comes in csv format.

## Processing
The csv file is read into the program. A simple loop iterates through the rows of the csv, saving the labels to one list and the sentences to another. Unwanted words are removed from the list of sentences once it's complete. The dataset is split into training and validation subsets.

An instance of the Tokenizer is created and fit on the list of training sentences. The Tokenizer converts the training and validation sentences into tokens that are appropriate for model training. A second instance of the Tokenizer converts the text labels into tokens.

A simple neural network is defined and compiled. The model is trained and the results are plotted.

## Results
![image](https://user-images.githubusercontent.com/83524079/141536959-9bc5c5b1-63fa-41be-9936-c25fd7d71157.png)

The model learns quickly and continues to improve over the 30 epochs. There is no evidence of overfitting, as the training and validation accuracy increase equally after the 15 epoch mark. The validation accuracy exceeds 90% at the end of model training, which exceeds my expectations for the simple neural network.

## Future work
Future projects could try to improve the accuracy of the model but I think gains in this area would be marginal at best. A better project would use an LSTM model and feed data into the model as a time series. The model could be used to generate new text that would mimic the language of BBC articles.
