# NeuralNetworkIntro

This project uses explanation from the book below:
http://neuralnetworksanddeeplearning.com/

Steps in Python for coding  on macOS:
- mkdir Project
- cd Project
- python3 -m venv venv
- pip freeze > requirements.txt
- pip install -r requirements.txt
- source venv/bin/activate

class Network(object):

    def __init__(self, sizes):
        self.num_layers = len(sizes)
        self.sizes = sizes
        self.biases = [np.random.randn(y, 1) for y in sizes[1:]]
        self.weights = [np.random.randn(y, x) 
                        for x, y in zip(sizes[:-1], sizes[1:])]

self.biases = [np.random.randn(y, 1) for y in sizes[1:]]
- This creates a list of random bias vectors
- sizes[1:] means take all layer sizes except the first (input layer)
- np.random.randn(y, 1) generates a y × 1 matrix (a column vector)

self.weights = [np.random.randn(y, x) 
                for x, y in zip(sizes[:-1], sizes[1:])]
- zip(sizes[:-1], sizes[1:]) pairs consecutive layers (input → hidden, hidden → output)
- np.random.randn(y, x) generates a y × x matrix (weights connecting layers)

Given sizes = [3, 2, 1]

3 neurons in the input layer

2 neurons in the hidden layer

1 neuron in the output layer

Biases:

One bias vector for each non-input layer:

Hidden layer (2 neurons): np.random.randn(2, 1)

Output layer (1 neuron): np.random.randn(1, 1)

Weights:

One weight matrix for each connection between layers:

Between input (3 neurons) → hidden (2 neurons): np.random.randn(2, 3)

Between hidden (2 neurons) → output (1 neuron): np.random.randn(1, 2)

