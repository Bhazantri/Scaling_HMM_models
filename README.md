# Scaling_HMM_models
scaling HMMs to large state spaces on parallel  hardware, and shows that this approach results in  accuracy gains compared to other HMM models.
Scaling Hidden Markov Language Models
Justin T. Chiu and Alexander Rush
EMNLP 2020

which trains HMMs with large state spaces for language modeling.

Dependencies
TVM 0.7.dev1. This has a dependency on LLVM.
Pytorch 1.5
Torchtext 0.6.0
Wandb 0.10.1
Brown Clusters
The HMMs in this repository rely on Brown Clusters. We include the Brown Clusters necessary for runnings the HMMs in the clusters directory. To rebuild the clusters, follow these instructions:

Clone the Brown Cluster repo from github.com/percyliang/brown-cluster and install it locally following the directions in the repo.

Export l_cluster to the path of the brown-cluster/wcluster command, installed in the previous step.

export l_cluster=/path/to/brown-cluster/wcluster
Preprocess the data by flattening the data. The flattened data is only used for producing the Brown Clusters.
python scripts/preprocess_datasets.py
Run the Brown Cluster script to obtain clusters for PTB and WikiText-2.
bash scripts/brown_cluster.sh lm128
bash scripts/brown_cluster.sh w2flm128
Very Large HMM (VL-HMM)
Penn Treebank
To train a 32k state HMM on PTB, run

source scripts/hmm_commands.sh && run_ptb
An example run can be found here.

WikiText-2
To train a 32k state HMM on WikiText-2, run

source scripts/hmm_commands.sh && run_w2
An example run can be found here.
