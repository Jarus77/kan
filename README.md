Efficient Implementation of Kolmogorov-Arnold Network (KAN)
This repository contains an optimized implementation of the Kolmogorov-Arnold Network (KAN), designed to enhance performance and interpretability.

Key Enhancements
1. Reformulated Activation Functions
The original KAN implementation expanded intermediate variables extensively for different activation functions. We improved efficiency by recognizing that these functions are linear combinations of fixed B-spline basis functions. This reformulation reduces memory overhead and simplifies computations to straightforward matrix multiplications, supporting both forward and backward passes seamlessly.

2. Sparsification and Regularization
Interpretability in KAN hinges on sparsification techniques. Unlike the original method, which used L1 regularization on input samples, our implementation opts for L1 regularization on weights. This choice aligns with standard neural network practices, ensuring computational efficiency while preserving interpretability.

3. Adjustable Activation Function Scales
In addition to learnable B-spline activation functions, our implementation introduces the enable_standalone_scale_spline option (default: True). Enabling this option includes learnable scales for each activation function. Disabling it enhances model efficiency but may impact performance, prompting ongoing experimentation to optimize results.

Updates and Improvements
Latest Update (2024-05-04)
Following feedback regarding initialization issues with base_weight parameters on MNIST, we adopted kaiming_uniform_ initialization for both base_weight and spline_scaler matrices. Initial results on MNIST show significant performance improvements (from ~20% to ~97%), highlighting potential benefits for broader applications.

Usage
To utilize this optimized KAN implementation, follow these steps:

Clone the repository:

bash
Copy code
git clone https://github.com/your-username/kan-implementation.git
cd kan-implementation
Install dependencies as needed. For example:

Copy code
pip install -r requirements.txt
Explore the codebase, experiment with different configurations, and contribute to ongoing optimizations.

Contributing
Contributions to enhance efficiency, interpretability, and performance are welcome. Please fork the repository and submit pull requests with improvements.

License
This project is licensed under the MIT License - see the LICENSE file for details.

Acknowledgments
Thanks to @xiaol for insights that led to significant performance improvements on MNIST.
Original research and implementation details can be found here.
