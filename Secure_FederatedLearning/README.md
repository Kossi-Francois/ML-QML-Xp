# Secure Federated learning 
This notebook is an experiment which attempts to Secure Federated learning by unlearning malicious client. \
To do this, at each round of federated training, each client keeps a copy of the current version of their model after training. \
The idea is to then reuse these different versions as a starting point in each round for the training of each client, and to update the server model, and all this while excluding malicious clients. \


<p float="left" align="middle">
  <img src="/Secure_FederatedLearning/result_plot.png" width="99%">
</p>
