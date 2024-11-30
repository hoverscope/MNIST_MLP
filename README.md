
1.Introduction:
Problem statement:
To build a machine learning model from scratch without existing machine learning libraries and choose an appropriate algorithm for the task of training it to identify Handwritten Digits from the MNIST dataset with two-fold validation and high accuracy. 

The MNIST dataset is a well-known dataset for handwritten digit classification, consisting of grayscale images of handwritten digits. For this project, each image was resized to 8x8 pixels in the provided dataset, resulting in a 64-dimensional input vector for the model. The dataset consists of images labelled with digits from 0 to 9. I used multilayer perceptron (MLP) as my chosen algorithm for this dataset and achieved a test accuracy of 98.11%.

2. Model Architecture and Two-Fold Testing:
2.1 Model Description and Architecture
The project was implemented using Python and NumPy. The chosen algorithm for this task as mentioned was a Multi-Layer Perceptron (MLP) with a single hidden layer. The model consists of 64 input neurons, representing the 64 pixels in each image of handwritten digits, and 10 output neurons, corresponding to the digits 0-9. The choice of 64 input neurons is due to the images being 8x8 pixels, with each pixel representing a feature, while the 10 output neurons map to the possible digit classes.

The model has tuneable hyper-parameters which are:
h (number of hidden neurons) 
learning_rate 
iterations or training cycles
The input layer uses leaky_ReLu for activation and softmax for the output layer. During the training and testing process, no significant issues with overfitting were observed, as the final training and testing accuracies consistently remained within a threshold of 2-3%. This indicated a well-generalized model, achieving high accuracy on both training and testing datasets.



2.2 Two-Fold Test
Two datasets, dataSet1.csv and dataSet2.csv, were provided. dataSet1.csv was solely used for training the model, while dataSet2.csv was exclusively used for testing. These datasets were loaded as pandas Data Frames and converted into X_train and Y_train for training, with the first 64 values of each row representing the features (pixels) and the last column as the label (digit). Similarly, the test data was also converted into X_test and Y_test with the same structure. This two-fold testing approach ensured that the model was evaluated on unseen data, providing a reliable measure of its generalization capability.
![image](https://github.com/user-attachments/assets/357bfbf7-ddaf-42e5-9ebf-b7da3ef1b437)

3.3 Screenshot two-fold test process


3.Initalization and Hyperparameters:
3.1 Initialization
Weights were initialized using He initialization to ensure stable gradients during training based on size of hidden layer neurons. The biases are initialized with zeros.
3.2 Hyperparameters:
The model was trained using the RMS Prop optimizer incorporating dynamic learning rate adjustments and L2 regularization for weight decay. A patience-based early stopping mechanism was employed to save the best model parameter. Hyperparameters such as learning rate and weight decay were fine-tuned during training to ensure optimal performance.
![image](https://github.com/user-attachments/assets/64522c53-f211-49f5-b1bd-869313d902fb)

 
3.3 Screenshot showing final value hyperparameters.

4. Accuracy and Results:
The model achieves a high accuracy result of 98.11% on the testing set with training iterations of 800 and an initial learning rate of 0. 009.The accuracy validation on the training set starts at a low 9.75% and reaches 100% at the end of training indicating the model is well-trained and effectively learning patterns in the data.


![image](https://github.com/user-attachments/assets/e5a039ba-1003-4d29-8555-40ae33e0f599)




    

4.1 screenshot showing result of accuracy on test data set using two-fold test
![image](https://github.com/user-attachments/assets/54bcd591-200a-4e6e-9572-e692999db6fb)


 
4.2 screenshot showing training/learning process of the model on the training dataset






5. Challenges Encountered and Conclusion:
After initially implementing the K-Nearest Neighbours (KNN) algorithm, which helped me understand the dataset, I encountered challenges in hyperparameter tuning. During the implementation of the MLP, the model plateaued at 97% accuracy without RMSprop optimization. After studying the underlying formulas, I transitioned to a Multi-Layer Perceptron (MLP) with RMSprop, which improved performance.
In conclusion, while the model showed promising results, there is still room for improvement, particularly in fine-tuning hyperparameters and exploring advanced optimization techniques. This project provided valuable insights into AI models and optimization, enhancing my understanding of machine learning.

Figures:
 ![image](https://github.com/user-attachments/assets/2aca05a9-beaa-4788-b4ec-e5f3046110b2)

Screenshot showing 4 random samples of test data being plotted and compared against model predictions.

 
Screenshot showing plotted confusion matrix for the model
![image](https://github.com/user-attachments/assets/3ad1899b-5e8c-46a7-a3cb-0f91d3fc6431)

