# neuralnetwork-performance-analysis
This study explores how hidden layers, neurons, and regularization impact neural network model performance using two datasets.

The goal of this project was to analyze how hidden layers, neurons, and regularization affect neural network model performance. Two datasets of varying sizes were used for four experiments. First, models with fixed architecture were trained on increasing data sizes to evaluate accuracy gains from more data. Next, proportional increases in hidden neurons versus sample sizes were compared to determine which impacts performance more. Then, hidden layers were added to a model with fixed neuron numbers to assess if extra layers increase performance. Finally, L1, L2 regularization, and Dropout layers were applied to evaluate their effects on the performance of a fixed model.

Datasets:
2 datasets were used: CIFAR-10 and a small MNIST subset.
CIFAR-10 consists of 60,000 32x32 color images of objects belonging to 10 classes. The dataset was split into 50,000 training images and 10,000 test images. The data were normalized to the 0-1 range and the labels were one-hot encoded into 10 classes. The MNIST subset consists of 2,500 samples with 784 features and 1 output for 10 classes. The dataset was shuffled, normalized, and split into a training set of 2,000 samples and a test set of 500 samples.
The model and training parameters were kept as consistent as possible to evaluate the effects of the model architecture on different datasets. In all experiments, learning rate was fixed at 0.001, epoch number was 10, and the batch size was 64.

Methodologies:
Part 1:
Two dataset was divided into six subsets with [500, 1000, 5000, 12,500, 25,000, 50,000] for CIFAR-10 and [62, 120, 250, 500, 1000, 2000] for sub-MNIST to evaluate how model performance changes accross data set sizes. For both datasets, a neural network with 1 hidden layer of 20 neurons and an output layer of 10 neurons was used. The same model and training parameters were used for all experiments, only changing the size of training data to see how the sample sizes affect the accuracy.

Part 2:
The same subsets of CIFAR-10 and MNIST subset were used to analyze the effect of decaying neuron numbers on increasing sample sizes. The model in the experiment had only 1 hidden layer, and it was tested with multiple neuron numbers. As the amount of training data doubled, the number of neurons in the hidden layer was halved, starting from 160 neurons down to 5 neurons.

Part 3:
CIFAR-10 training set (50,000 samples) and MNIST subset (2,000 samples) were used to train three models with 20 total neurons but different hidden layer configurations. The first model had 1 hidden layer. The second model had 2 hidden layers. The third model had 4 hidden layers. The same training parameters were used for all models to isolate the effect of depth.

Part 4:
CIFAR-10 and MNIST were used to train four models with 1 hidden layer of 20 neurons. Different regularization techniques were applied to evaluate their effects. The first model had no regularization. The second and third model used L1 and L2 regularization with a strength of 0.001, respectively. The fourth model used Dropout with a 0.5 dropout ratio. Applying regularization helps prevent overfitting by constraining the model. Comparing the performance of models with and without regularization shows how much each technique improves generalization.

