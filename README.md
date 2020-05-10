# Modulation Classification
Classifying different signals modulations into their right modulations using different baseline classifiers and a CNN model

## Dataset
DeepSig Dataset: RadioML 2016.04B
**Download Link**: opendata.deepsig.io/datasets/2016.10/RML2016.10b.tar.bz2
**Description**: 
A synthetic dataset, generated with GNU Radio [[1]](#1), consisting of 11 modulations. This is a
variable-SNR dataset with moderate LO drift, light fading, and numerous different
labeled SNR increments for use in measuring performance across different signal and
noise power scenarios.

* It has 1,200,000 samples
* Each sample is presented using two vectors each of them has 128 elements.
* The data is split into 70% for training/validation and 30% for testing.
* 5% of the training and validation dataset for validation.

## Feature Spaces
4 different features spaces are used and results are compared
* Raw time series as given (two channels)
*  First derivative in time (two channels)
*  Integral in time (two channels)
*  Combinations of 1,2 and 3. (More channels)
 
 
## Baseline Classifiers
* Logistic Regression Classifier
* Decision Tree
* Random Forest
* A fully connected dense layer:
  - Non-linear function: Relu
  - Optimizer: ADAM
  - Early stopping
 
 
 ## CNN Model
 **Architecture:**  [[2]](#2)
- Input         :  2 x 128
- Conv Relu     :  64 x (1 x 3)
- Conv Relu     :  16 x (2 x 3)
- Dense Relu    :  128
- Dense Softmax :  10
- Output        :  10

## References
<a id="1">[1]</a> 
T. O’shea, N. West. 
“Radio Machine Learning Dataset Generation with
GNU Radio”,
https://pubs.gnuradio.org/index.php/grcon/article/download/11/10/
<a id="2">[2]</a> 
T. O’Shea, J. Corgan, and T. Clancy.
“Convolutional Radio Modulation Recognition Networks”
https://arxiv.org/pdf/1602.04105.pdf
 
