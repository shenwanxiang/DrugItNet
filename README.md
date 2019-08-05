# DrugIt-Net


#### 1) Three Channels Inputs：Physicochemical, Structurally topological, Pharmacodynamic vectors
This is a 2D convolutional neural network architecture. 
The first layer consists of a fully connected layer, which inputs three channels of `molecular fingerprints`, `molecular descriptors`, and `2d molecular pharmacophores`. 
The second layer is convolution layer, but it is different from image processing in ResNet, the three channels are going to be done by reduce_max insteads of reduce_sum


#### 2) Fully Connected layer is commit to learn the pre-convolution matrix

A Fully connected layer helps to recombine features(descriptors) of the same type. After that a CNN architecture can be conducted
The three channels will be trained separately in the first few layers, after that it will be stacked, and a new convolution operation will be performed. Hopefully the fc layer can be trained to learn the features combination


#### 3）In this Multi-label task, a multi-task learning method will be performed

[Cytochrome P450](https://en.wikipedia.org/wiki/Cytochrome_P450) is a big fammily with many members. CYPs are the major enzymes involved in drug metabolism, accounting for about 75% of the total metabolism. So many compunds or drugs are the substrates of different CYP fammily members at the same time. Take a paper here: ['Prediction of Human Cytochrome P450 Inhibition Using a Multitask Deep Autoencoder Neural Network.'](https://www.ncbi.nlm.nih.gov/pubmed/29775322). I am going to use the dataset in this paper, namely the assay id in PubChem is [AID 1851](https://pubchem.ncbi.nlm.nih.gov/bioassay/1851#section=Data-Table)
