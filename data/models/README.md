Scratch Artificial Neural Network (MNIST)

A fully implemented feedforward Artificial Neural Network from scratch using NumPy, trained on the MNIST handwritten digit dataset using:

Backpropagation

Mini-batch Stochastic Gradient Descent (SGD)

Sigmoid activation function

No deep learning frameworks (TensorFlow / PyTorch) were used.

Architecture
Input Layer:      784 neurons (28x28 MNIST image)
Hidden Layer 1:   50 neurons
Hidden Layer 2:   30 neurons
Output Layer:     10 neurons (digit classes 0–9)


Model initialization:

net1 = network([784, 50, 30, 10])

 Mathematical Overview
Forward Propagation

For each layer:

𝑎
=
𝜎
(
𝑊
𝑎
+
𝑏
)
a=σ(Wa+b)

Where:

𝑊
W = weights

𝑏
b = biases

𝜎
σ = sigmoid activation

Backpropagation

Output layer error:

𝛿
=
(
𝑎
−
𝑦
)
⋅
𝜎
′
(
𝑧
)
δ=(a−y)⋅σ
′
(z)

Hidden layer error:

𝛿
𝑙
=
(
𝑊
𝑙
+
1
)
𝑇
𝛿
𝑙
+
1
⋅
𝜎
′
(
𝑧
𝑙
)
δ
l
=(W
l+1
)
T
δ
l+1
⋅σ
′
(z
l
)

Weights update rule:

𝑊
=
𝑊
−
𝜂
1
𝑚
∇
𝑊
W=W−η
m
1
	​

∇W

Where:

𝜂
η = learning rate

𝑚
m = mini-batch size

 Training Configuration
net1.sgd(training_data, 200, 10, 0.001, test_data=test_data)


Epochs: 200

Mini-batch size: 10

Learning rate: 0.001