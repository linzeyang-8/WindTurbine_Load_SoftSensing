# WindTurbine_Load_SoftSensing
This warehouse corresponds to the core resources of the paper Transferable Soft Sensing Method for Wind Turbine Structural Loads Driven by Measurable Multi-dimensional Time Series Data for reviewers to quickly reproduce the experimental results, including code, data set, pre-trained model and key result diagram.

1.Repository Structure
1_codes/   # 6 core experimental scripts (rename.txt to .py to run)
   Ⅰ. GVAM-RN_dimensionality_reduction.txt  # Trained GVAM-RN dimensionality reduction model 
   Ⅱ. 5-DR-methods-for-Estimation.txt        # 5MW data: Comparison of 5 dimensionality reduction methods (GVAM-RN/VAM-RN/etc.)
   Ⅲ. Comparison_of_5MW_noisy_test_set.txt      # 5MW noisy data: Load estimation robustness verification (10%/20% noise)
   Ⅳ. ITP-MAML-1.5MW-Data_Quantification.txt  # 1.5MW target turbine: Data quantity quantification (20/30/50/70 samples) ITP-MAML_generates_pth.txt          
   Ⅴ. ITP-MAML_generates_pth.txt  # ITP-MAML  #training: Generate optimal θ*.pth parameters
   Ⅵ. 4_Transfer_Comparisons-1.5MW.txt    # 1.5MW data: Comparison of 4 transfer learning methods (ITP-MAML/MAML/etc.)

2_Datasets/  #Contains the original data sets required for the experiment: specifically, there are target variables of 5MW training set and test set, 5MW noise test set and original test set, 1.5 MW original data sets with different training samples and corresponding target variables, 10 groups of test sets and corresponding target variables

3_Dimensionality_reduction_file/  # Contains the dimensionality reduction data set required for the experiment: This file mainly includes the 1.5 MW dimensionality reduction training set and dimensionality reduction test set with different training samples, as well as the 5MW noise dimensionality reduction test set and the original dimensionality reduction test set.

4_Model_weights/  # Pretrained .pth weights (load directly for inference)
  ├─ feature_extractor.pth    # Optimal Weight and Bias of GVAM-RN Dimensionality Reduction Model
  ├─ scalers.pkl   # It is a Python serialization file. Its core function is to save the standardizer parameters used in the data standardization process to ensure that the preprocessing logic of all data sets is completely consistent. 
  ├─ ITP-MAML.pth  # Optimal initialization parameters of ITP-MAML meta-learning framework
  ├─ MAML.pth  # Optimal initialization parameters of MAML meta-learning framework
  ├─ DANN.pth   # Optimal initialization parameters of DANN 

5_others/   # Includes the training set and test set after dimensionality reduction of five dimensionality reduction methods


2. Environment Configuration
2.1 Hardware Requirements
CPU: Intel i9-14900HX / RAM: 32GB / GPU: NVIDIA GeForce RTX 4060 
Operating System: Microsoft Windows 11 (AMD64)
2.2 Dependent Library Versions
Library	Version
Python	3.10.8
pandas	2.2.3
numpy	2.1.3
matplotlib	3.9.2
catboost	1.2.8
scikit-learn	1.6.1
torch	2.4.0
tabulate	0.9.0


3. Notes
Scripts default to reading paths within the repository (e.g., .\Codes_and_datasets\Dimensionality_reduction_file\OP1.5MW_encoded_50_Train.xlsx). If you move files, update the file_path variable in the code accordingly.
Pretrained models can be loaded directly .
Complete training logs and data preprocessing details will be added after the paper is formally accepted.


5. Contact Information
Corresponding Author: Qi Yao (qiyao@jnu.edu.cn)Repository Maintainer: Zeyang Lin (linzeyang@stu2024.jnu.edu.cn)
