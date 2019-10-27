### About the model

The model is a Multi-Layer Perceptron with 3 hidden layers. It gets 5 days' daily average temperature values as inputs and outputs a prediction for the next day. This notebook contains every information about the model, code for loading the data and train the model, but there are also saved models in the project directory.

There are two flags in this notebook to configure its behavior:

- normalization_flag : If True, the loaded data will be normalized before training and scaled back after prediction. If False, all data will remain in degrees Celsius.
- you_are_sure_about_this : If True, a new model will be trained (it may take 1-3 mins). If False, the notebook loads in a trained and saved set of weights for the model.

Hyperparameters of the model:

- input_seq_length : The length of the input sequence in days. The best performing model gets 5 days' data to predict the next day.
- num_of_neurons : A list containing the widths of the hidden layers and the output layer. The number of layers can be altered if one adds or removes a value from this list because the model is built in a for-loop running through it. The best performing model has 3 hidden layers with 10-20-8 neurons, respectively, and 1 output neuron.
- learning_rate : Learning rate parameter for the Adam optimizer. Its set to 1e-4.
- batch_size : Set to 64.
- num_of_epochs : Set to 9001 because the training uses early stopping and model checkpoint.

How to use a pretrained model?

- The configuration of the model is not saved so one should construct a model same as here. The weights can be loaded after. There are weights saved for both normalized and not normalized data.
- The model operates on daily average temperatures in degrees Celsius. 5 days' data should be presented to the models input layer to make a prediction for the following day. Predictions for days further than that can be predicted if one feeds the model's predicted temperature value back to it's input.

