# Type In Your Handwriting!
## Summary
Handwriting Imitation has always been a sensational topic in the AI industry. Handwriting is something that usually differentiates AI from humans as it is a special characteristic that humans have as it varies from person to person and time to time. Since this field is not much discovered and much needs to be done yet, therefore the project allows to explore the undiscovered areas and learn more and more which was the motivation behind taking this project. We have built a model that imitates the user’s handwriting and generates output to any query text provided. We have used GANs in our model to generate the handwritten text. Our model takes two inputs which are the handwriting sample and the query text which needs to be converted to the handwritten form. We had tried working on RL                                                                                            
The GANs(Generative Adversarial Networks) are models with a generator and discriminator. The generator generates fake images which the discriminator analyzes and classifies as real or fake(given that discriminator is trained on the real dataset). Based on the feedback from the discriminator, generator modifies its weights to generate better fake images. Our model was trained first of all on the widely available IAM dataset to generate the handwritten text. Later after taking the input form the user we use them to finetune the weights of our model to modify it accordingly. Thus our final model is able to generate handwritings that resemble human handwritings very much.
We have also added additional features in our model like the user can change the colour of the text and also the user can change the background page of the handwritten text. Also we have built our streamlit app that displays all the features our model has and can be used as an interface by the user to interact with the model.

| ![800 epochs](https://drive.google.com/uc?id=1NyPwf19q1UgJahzkUVUEcqOsUtTMy-m0) | ![2000 epochs](https://drive.google.com/uc?id=1PqWCDcytN_tjo7RWvgQWHL1yF_mnBcmE) |
|:--:|:--:|
| *800 epochs* | *2000 epochs* |

| ![](https://drive.google.com/uc?id=1R9YMdVOh9_G7HSKqmjG-SEjd3RXtWAr8) |
|:--:| 
| *4000 epochs* |

## Our Approaches
We were working on two different approaches at the same time initially. They were Reinforcement Learning and GANs. Their detailed description is given below:

### GAN Model
The basic architecture of our GAN model is such that we have used transformer layers in our generator to do the encoding and decoding procedure. First of all we have cnn encoded images as input to the model. As a part of preprocessing we have converted the images to grayscale format and also padded the images. Subsequently the images are converted to tensor format so that further operations can be performed on the dataset.
These images go to the transformer encoder which                                                 then this goes to the transformer decoder layer where the query text is embedded with the input text.The query text is also encoded using the OCR Network encoder.  Now this goes to the CNN decoder which converts the whole thing to an image. This image is the fake image generated by the generator which now is passed on to the discriminator which classifies it as real or fake and based on its feedback generator modifies its weights during the training. We have used two discriminators which have been taken from BigGAN model. 
Our model is being trained twice. The first time our model is being trained on the IAM Dataset. The IAM Dataset was used due to its wide availability and also due to the fact that this dataset has a variety of handwritings. These have been authored by around 500 authors. 339 of them were used for the training purpose and the rest are used for the validation purpose. The first training has been done for 10000 epochs. The optimizer that we have used is Adam optimizer. There are multiple loss functions defined. These functions are associated with Generator, Discriminator, OCR converter etc.This model is capable of generating handwritten text which resembles human handwriting very much.
| ![](https://drive.google.com/uc?id=1R9YMdVOh9_G7HSKqmjG-SEjd3RXtWAr8) |
|:--:| 
| *4000 epochs* |
