# Eye_for_Blind
## Problem statement: 
        In this capstone project, we need to create a deep learning model which can explain the contents of an image in the form of speech through caption generation with an attention mechanism on Flickr8K dataset. This kind of model is a use-case for blind people so that they can understand any image with the help of speech. The caption generated through a CNN-RNN model will be converted to speech using a text to speech library. 

This problem statement is an application of both deep learning and natural language processing. The features of an image will be extracted by a CNN-based encoder and this will be decoded by an RNN model.

The project is an extended application of Show, Attend and Tell: Neural Image Caption Generation with Visual Attention paper (i.e. https://arxiv.org/pdf/1502.03044.pdf)


## Summary Report

### Data Understanding:
- The project began with importing a dataset containing images and corresponding captions.
- Extensive data understanding and exploration were conducted.
- Both images and text in the dataset were visualized, providing insights into the data.
- A DataFrame was created to consolidate image paths and captions.
- A comprehensive list containing all captions and image paths was generated.
- The top 30 occurring words in the captions were visualized, aiding in data analysis.
### Loading Pretrained InceptionV3 Weights:
- To conserve memory resources, pretrained ImageNet weights of the InceptionNet V3 model were loaded.
- The features of the images were extracted using the last layer of the pretrained model.
- A custom function reshaped the output to (batch_size, 8*8, 2048) for efficient processing.
### Dataset Creation:
The dataset was split into training and testing sets using an 80-20 ratio, with a random state of 42.
A mapping function was created to associate image paths with their respective features.
The dataset was built, ensuring proper shuffling and batching.
Image shapes in the dataset were standardized to (batch_size, 8*8, 2048), and caption shapes were adjusted to (batch_size, max_len).
### Model Building:
Model parameters were configured, setting the stage for further development.
An Encoder, Attention model, and Decoder were meticulously constructed.
The Encoder-Decoder architecture included Teacher Forcing, improving model training.
### Model Training & Optimization:
An optimizer and loss object were defined to optimize the training process.
A checkpoint path was established to save model checkpoints.
Training and testing step functions were implemented to ensure efficient model training.
A loss function for the test dataset was created to assess model performance.
### Model Evaluation:
- Evaluation functions were designed for both greedy search and beam search approaches.
- The model's performance was evaluated on a sample dataset using the BLEU score, a metric that measures the quality of generated captions.
### Conclusion:
The "Eye for Blind" project successfully addressed the challenge of generating descriptive captions for images, making visual content accessible to visually impaired individuals. By implementing an Encoder-Decoder architecture with attention, pretrained InceptionNet V3 weights, and rigorous model training and evaluation, the project aimed to provide an innovative solution for enhancing the accessibility of digital content for the blind community.

