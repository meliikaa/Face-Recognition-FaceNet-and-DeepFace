# Face-Recognition-FaceNet-and-DeepFace


Welcome to the Face Recognition project! In this repository, you will explore the world of face recognition, drawing inspiration from FaceNet and DeepFace. Face recognition problems often fall into two categories: Face Verification (1:1 matching) and Face Recognition (1:K matching).

## Problem Statement

1. **Face Verification**: This problem aims to determine if two images belong to the same person. For example, facial recognition systems at airports use this to verify that the person carrying a passport is indeed the passport holder. This is a 1:1 matching problem.

2. **Face Recognition**: This problem goes a step further by identifying an individual among a group of known individuals. For instance, an office entrance system may recognize employees by their faces without additional identification. This is a 1:K matching problem.

The main ingredient of face recognition is the triplet loss function. In this assignment, you won't need to implement the triplet loss function, as you'll be using a pretrained model. However, understanding the triplet loss is crucial for training your own FaceNet model and similar image similarity problems.

### The Triplet Loss

In the triplet loss, training involves triplets of images (𝐴, 𝑃, 𝑁):

- A is an "Anchor" image, representing a picture of a person.
- P is a "Positive" image, showing the same person as the Anchor image.
- N is a "Negative" image, depicting a different person than the Anchor image.

The goal is to ensure that the distance between the encoding of A and P is smaller than the distance between A and N by at least a margin 𝛼. Mathematically, you aim to minimize the triplet cost defined as follows:

𝜶 = ∑𝑖=1𝑚 [∣∣𝑓(𝐴(𝑖))−𝑓(𝑃(𝑖))∣∣² - ∣∣𝑓(𝐴(𝑖))−𝑓(𝑁(𝑖))∣∣² + 𝛼]+

Where:
- (1) represents the squared distance between the Anchor and Positive images.
- (2) represents the squared distance between the Anchor and Negative images.
- 𝛼 is a margin, typically set to 0.2.

### Learning Objectives

By the end of this assignment, you will be able to:

- Differentiate between face verification and face recognition.
- Implement one-shot learning for face recognition.
- Apply the triplet loss function for learning a neural network's parameters in the context of face recognition.
- Pose face recognition as a binary classification problem.
- Map face images into 128-dimensional encodings using a pretrained model.

## Naive Face Verification

In Face Verification, you're provided with two images and must determine if they depict the same person. One simple approach is to compare the two images pixel-by-pixel. However, this method performs poorly due to variations in lighting, orientation, head position, and other factors.

## Encoding Face Images into a 128-Dimensional Vector

### Using a ConvNet to Compute Encodings

FaceNet, the model used in this assignment, takes RGB face images with dimensions of 160x160 pixels as input. The input images are originally 96x96 pixels, but they are scaled to 160x160 pixels. The output is a matrix of shape (𝑚, 128), encoding each input face image into a 128-dimensional vector. These encodings can be used for face verification and recognition.

For your convenience, an Inception network implementation has been provided. The key points to note are:

- Input images are of shape (𝑚, 𝑛𝐻, 𝑛𝑊, 𝑛𝐶) = (𝑚, 160, 160, 3).
- The output is a matrix of shape (𝑚, 128).
- Channels-last notation is used for ConvNet activations.

By completing this assignment, you will gain hands-on experience in face recognition, one-shot learning, and understanding the triplet loss function. Dive into the world of facial recognition and enjoy building your own face recognition system! If you have questions or need assistance, feel free to reach out to the project contributors or the community. Happy coding!

## Credits

All credits goes to DeepLearning.Ai for their Deep Leqaning course on coursera 

#FaceRecognition #FaceVerification #TripletLoss #DeepLearning #ComputerVision #MachineLearning #ProgrammingAssignment
