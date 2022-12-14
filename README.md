September 2022

# Live Sign Language Translator

**More details and actual code can be found in the notebook**

#### Credits:

The model is dependent on Nicholas Renotte's tutorial (https://www.youtube.com/watch?v=yqkISICHH-U) and repo (https://github.com/nicknochnack/TFODCourse). The verification and TFRecords scripts are by him as well as a few coding blocks that take into account different operating systems.

The labeling is possible because of Heartex's labelImg repo (https://github.com/heartexlabs/labelImg) which helped a lot with manually labeling the images and creating the XML files associated with each image

## Description:

This is a computer vision model which utilizes open-cv and TensorFlow object-detection to make predictions on images and a live video feed showing detected hand signs for sign language translation. The model can differentiate between 5 different vehicle types ('Hello', 'Thumbs Up', 'Thumbs Down', 'Yes', 'No').

The first thing I did when approaching this project was create a virtual environment where all packages would be isolated from the rest of the computer this helped a lot with organization. Once all of the necessary packages, dependencies, and dataset were gathered, I prepared different file paths in /TensorFlow for images. I then used my camera for image collection purposes. These images were organized into the folder system previously created. The image labeling package was then used to label all of these images manually. I then separated the images into train and test sets. After that, I set up variable paths for training purposes and ran the verification script (credited above) to make sure all packages and dependencies were in check. Lastly, before training, I adjusted the config file with the various paths. During training, I used CUDA to train the model on my NVIDIA GPU for accelerated speeds. After the model was done training I went through Tensorboard for evaluation metrics, did a test with an image, and then tested with a live feed. Finally, I froze the graph and made the model conversions to TFLite and TFJS.

## Use Case:

This can be used as...

- a means to help break the communication barrier between those who are unable to speak and those who do not know sign language
- a learning tool used to teach sign language to those who are interested  

## Demonstration

#### Video Demonstration

https://www.youtube.com/watch?v=5n3iZMe0rIs&ab_channel=HarshPatel

#### Image Demonstration

Here is the model performing on an image:

![image demo](https://github.com/harshp30/LiveSignLanguageTranslator/blob/main/images/imagedemo.png)
    
## Performance
 
Using tensorboard I was able to get a few charts displaying training and evaluation metrics as shown below.

#### Evaluation Metrics:

![eval metrics](https://github.com/harshp30/LiveSignLanguageTranslator/blob/main/images/precisioneval.png)
![eval metrics](https://github.com/harshp30/LiveSignLanguageTranslator/blob/main/images/recalleval.png)

Here is also what the model see's when looking at a sample image:

![tensorboard image](https://github.com/harshp30/LiveSignLanguageTranslator/blob/main/images/imageeval.png)
 
#### Training Metrics:

![training metrics](https://github.com/harshp30/LiveSignLanguageTranslator/blob/main/images/train.png)

## Key Learnings

I learned a lot throughout this project, everything from how to find a reliable dataset, modifying and manipulating label maps, and different conversion methods for models to later be used in a practical application.

The most significant thing I learned through the project was the importance of good datasets. I went through this project a few times and my model was not performing well at all. This taught me the importance of good datasets and in my case good image collection. Taking photos of the hand sign from different angles was vital in performance. Along with this the importance of good labeling was also significant. I had to make sure my box borders were as 'tight' as possible to the actual hand sign.

Overall I learned a lot of unique and new skills by working on this project.

## Key Challenges

As mentioned above the toughest part was the image collection and labeling. Since I had never done that before I made a few vital errors in my previous iterations of this project. After seeing how poorly the model performed I learned techniques to create a more diverse dataset, where in this case factors like lighting and angles were very important. It was a very important lesson to learn and it's something I will keep in my mind while doing similar work in the future. 

## Future Improvements and Expansion

This model still has a lot of room for importance. Since the dataset is so small and every image is just a photo of my hand, this model would perform poorly for other people. Especially when it comes to different skin tones and 'chaotic' backgrounds the model will struggle. This can be dealt with by using a much larger official dataset.
 
Another thing I can expand on in this project is having more hand signs and better signing. I struggled with some of the hand signs in image collection which influenced the model, so having someone fluent in hand sign (ASL) would be a great expansion.
