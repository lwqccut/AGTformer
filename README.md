run environment
python --- 3.8

pytorch --- 1.11.0

torchvision --- 1.12.0

torchaudio --- 0.11.0

scanpy --- 1.8.2

scipy --- 1.6.2

numpy --- 1.19.5

leidenalg --- 0.8.10

file Description
"loss": NB-based or ZINB-based loss fuction and refer to "scDeepCluster"

"model": Containing model framwork of AttentionAE-sc and the framwork the GNN module, Attention module.

"preprocessing_h5.py" and "preprocessing_baron.py": Preprocessing fuction for different format.

"run_AttentionAE-sc.py": To perform model training and clustering analysis.

"train.py": Containing the train and clustering fuction.

"utils.py": Containing some data processing, cell-cell graph construction, and visualization utilities.

Data Source
The preprocessing of two kinds of datasets (.h5, .csv) is provided by the "preprocessing_h5.py" and "preprocessing_baron.py". Then, the corresponding ".h5ad" files are output in the "./Data/AnnData", where is the default for model input. If you want to analzye another scRNA-seq datasets, please copy your ".h5ad" files to here and set "-name" to the file name.

Other datasets: the breast cancer single-cell dataset used in our research can obtain from "GSE173634".

Usage
For applying AttentionAE-sc, the convenient way is run "run_AttentionAE-sc.py".

Please place the scRNA-seq dataset you want to analyze in the directory "./Data/AnnData", where is the default for model input. If you want to calculate the similarity between the predicted clustering resluts and the true cell labels (based on NMI or ARI score), please transmit your true labels into the "adata.obs['celltype']" and setting the argument "-celltype" to True.
