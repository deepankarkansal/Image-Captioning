# Image-Captioning

To understand code please refer my Medium blog for this repo.

Dataset used is confidential, provided by my institute. So please use your own dataset.

*Brief description of dataset*

We analyzed the dataset and found that for each image, five captions were provided. So we created the mappings for each caption to the image for training the models right. 

We use the load_image() function for loading the images and resizing them to 244*244 shape. Then we create the batches of size 32 for feeding to the model. Using Keras preprocessing, we preprocess the captions, and also give the <start>  and <end> tags. 

The final dataset is created, which contains an image and its caption’s embedding mapping. Firstly we extract the features from the VGG16 model and then pass them to the encoder. 

The output of the encoder is given to the decoder. For the predictions, the hidden state of the decoder is passed to the model. 

For the evaluation of the predicted captions, we use the BLEU metric, BLEU-1, BLEU-2, BLEU-3, and BLEU-4. BLEU metric is used for matching predictions to the actual captions. BLEU-1, BLEU-2, BLEU-3, and BLEU-4 calculate the individual Cumulative  N-gram score by assigning weights. For example for BLEU-1, weights are (1,0,0,0) for BLEU-2 weights are (0.5,0.5,0,0) and so on. 

METEOR, which evaluates on a word to word basis assigns the score between o to 1, is also used for the evaluation of captions.

Helper Functions:

mapping_fun() : For loading the image array based from image name.
plot_attention() : For plotting the attention using attention weights, for evaluation.
Clean_Tagging() :For tagging the captions with <start> and <end>
convert_to_DataFrame() : For storing the cleaned captions with image names in the DataFrame.
pad_sequences() : For padding the data
train_step() : For training the model
train_data(): For training on the encoder decoder architecture
BLEU(): For BLEU 1-4 scores.
METEOR(): For METEOR score.
