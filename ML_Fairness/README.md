# Fairness in Machine Learning

This notebook is an experiment which attempts to Mesure and Reduce Bias in a prediction task using [Wasserstein-2 distance](https://fr.wikipedia.org/wiki/Distance_de_Wasserstein)
To do that, we perform on the [CelebA dataset](https://mmlab.ie.cuhk.edu.hk/projects/CelebA.html), the binary classification task Smiling (or not), and we then evaluate the bias on several metrics (Accuracy, Precision, Recall) knowing the characteristic Young/not Young. The goal then is to reduce this bias (for certain metrics) by using Wasserstein-2 distance.

*In what follows, we note 
+ $x \in X$, the data(image), 
+ $y \in Y$, the target characteristic (smiling/not smiling),
+ $z \in Z$ the conditional characteristic (young/not young),
+ $f : X \mapsto H$, the features extractor in the neural network,
+ $g : H \mapsto Y$, the classifier in the neural network
