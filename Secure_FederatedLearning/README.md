# Secure Federated learning 
This notebook is an experiment which attempts to Secure Federated learning by unlearning malicious client. \
To do this, at each round of federated training, each client keeps a copy of the current version of their model after training. \
The idea is to then reuse these different versions as a starting point in each round for the training of each client, and to update the server model, and all this while excluding malicious clients. \

To compare the effect of a malicious client and its deletion, the classifier was trained according to the following 4 configurations:
1. fl_base: the base model wich is federated learning with all 10 clients are good clients (no malicious clients)
2. fl_poised: the poised model wich is federated learning with 3 malicious clients out of the 10 clients
3. fl_secured: the secured model wich is federated learning without the 3 malicious clients (so 7 good clients out of 10), trained from fl_poised backups
4. fl_retrain: the model trained from scratch with the 7 good clients


<p float="left" align="middle">
  <img src="/Secure_FederatedLearning/result_plot.png" width="99%">
</p>
