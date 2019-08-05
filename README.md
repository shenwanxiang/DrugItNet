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

* Table 1. The distribution of CYP 450's inhibitors number in AID1851
<table  class="dataframe" align="center"> 
  <thead>   
    <tr style="text-align: justify;">   
    <th></th>  <th>active_CIDs</th>    <th>inactive_CIDs</th>      <th>Inconclusive_CIDs</th>   </tr>  
  </thead> 
  <tbody>    
   <tr>      <th>cyp2c19</th>      <td>5045</td>      <td>7133</td>      <td>4382</td>    </tr>   
   <tr>      <th>cyp2d6</th>      <td>1630</td>      <td>10824</td>      <td>4106</td>    </tr>    
   <tr>      <th>cyp3a4</th>      <td>3543</td>      <td>7381</td>      <td>5636</td>    </tr>    
   <tr>      <th>cyp1a2</th>      <td>4461</td>      <td>6966</td>      <td>5133</td>    </tr>    
   <tr>      <th>cyp2c9</th>      <td>3011</td>      <td>8344</td>      <td>5205</td>    </tr>    
   <tr>      <th>total_unique_cids</th>      <td>9149</td>      <td>14555</td>      <td>13071</td>   </tr>  
  </tbody>
</table>

---

<img src="https://raw.githubusercontent.com/shenwanxiang/DrugIt-Net/master/data/cross_inhibitors.png" alt="Markdown Monster icon" style="float: left; margin-right: 10px;" />

 * Figure 1 shows total 145 compunds are the inhibitors for all the five subtype enzymes


---

<img src="https://raw.githubusercontent.com/shenwanxiang/DrugIt-Net/master/data/cross-non-inhibitors.png" alt="Markdown Monster icon" style="float: left; margin-right: 10px;" />

 * Figure 2 shows total 2027 compunds are the non-inhibitors for all the five subtype enzymes


     
