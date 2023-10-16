# Fairness in Machine Learning

This notebook is an experiment which attempts to Mesure and Reduce Bias in a prediction task using [Wasserstein-2 distance](https://fr.wikipedia.org/wiki/Distance_de_Wasserstein)
To do that, we perform on the [CelebA dataset](https://mmlab.ie.cuhk.edu.hk/projects/CelebA.html), the binary classification task Smiling (or not), and we then evaluate the bias on several metrics (Accuracy, Precision, Recall) knowing the characteristic Young/not Young. The goal then is to reduce this bias (for certain metrics) by using Wasserstein-2 distance.

*In what follows, we note 
+ $x \in X$, the datum(image), 
+ $y \in Y = \\{ 0, 1 \\}$, the target characteristic {smiling (y = 1)/ not smiling (y = 0) },
+ $z \in Z = \\{0, 1\\}$ the conditional characteristic {young (z = 1) /not young (z = 0) } ,
+ $f : X \mapsto H$, the features extractor in the neural network,
+ $g : H \mapsto Y$, the classifier in the neural network

 We then define our model as the parametric function $M_{\theta} = g_{\theta_{C}} ∘ f_{\theta_{H}}(x) = g(f(x)) = g(h)$. \
 In the case of the simple model (top image), if we consider for example precision as a metric, we see a bias as: $accuracy(x | z = 1) = 0.8044 > 0.7523 = accuracy(x | z = 0)$, which means that the model has better accuracy for young people.  \
 This can be also noticed when we print the feature space H, where  $f(x|z=1) = h_{z=1}$ (Young_group) is very close to $f(x) = h$ (All_data) while $f(x|z=0) = h_{z=0}$ (Not_Young_group) is different from these two. \
 To solve this problem, the idea is to use mass transport to bring $h_{z=1}$ and $h_{z=0}$  as close as possible. 


 In the case of the fair model (bottom image), after having optimized ($W_{D}(h_{z=1}, h_{z=0}) \to 0$ ) it to bring $h_{z=1}$ and $h_{z=0}$ close to each other, we observe two things:
 1. considering the Accuracy metric (for which we train the model), we notice a reduction in the gap between $accuracy(x | z = 1)$ and $accuracy(x | z = 0)$, we go from a difference of 0.0521 to 0.0412. We also notice it visually when we print H, we see that $h_{z=1}$ and $h_{z=0}$ are more similar.
 2. moreover we also see an improvement in accuracy

<p float="left" align="middle">
  <img src="/ML_Fairness/train_result_metrics_base_model.png" width="85%">
</p>

<p float="left" align="middle">
  <img src="/ML_Fairness/train_result_metrics_fair_model.png" width="85%">
</p>

