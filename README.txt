This package contains Python code and relevant files to perform Scholar Document classification on arxiv data with 
Longformer model (Transformers). 


The directory contents are as follows:

group9_ass2_model.ipynb						- A Jupyter notebook to perform a classification task.
best_model.pkl							- A pkl file which holding the final classifier of this project.
train_data_labels.csv						- A csv file contains training data.
test_labels.csv							- A csv file stores test data. 
pred_labels.csv							- A csv file contains example results from running the program. 
from_arxiv.csv							- dataset from Kaggle arxiv, already filtered with abstracts and labels
vocab.json							- json file with vocalbulary
README								- This document.

The program was built with Python version 3.7.6 on Anacoda Jupyter Notebook. 


============================================================================
Installation - Run on Colab. This setting is run best with COLAB GPU (K80). Internet connection is a must.
SETTING for GPU (MUST): When in COLAB, click Edit, then click Notebook Setting, then under Hardware Accelerator,
change to GPU, and then save. 

There are total of 11 external libraries required to be installed. Libraries and version used in the program 
are described as follows.

	Standard Libraries to be installed are:
	* Fastai 1.0.61
	* pytorch-transformers
	* transformers - version 3.4.0
	* tensorflow - version 2.3.0
	* gc
	* datetime
	* urllib3 1.25.10
	* gensim

!pip install transformers==3.4.0
!pip install pytorch-transformers
!pip install tensorflow==2.3.0
!pip install urllib3==1.25.10
============================================================================

Running Instruction

1. Create a google drive account, upload all the implementation file into one folder
2. Ensure that all relevant files are located in the same directory as ‘group9_ass2_model.ipynb’ file. 
3. Open colab, either upload file group9_ass2_model.ipynb, or read it from the google drive
4. Run ‘group9_ass2_model.ipynb’  with Google Colaboratory.
5. By default, the final model in ‘best_model.pkl’ will be read and used as a classifier. This is to save model
   training time which could take up to 9 hours. PLEASE DO NOT RUN ALL CELLS AT ONCE. In SECTION 6, if the cell contain
   this line learn = load_learner(path,'best_model.pkl') (Second cell), please ignore and do not run the next three cells to 
   go straight to prediction. Optionally, to train a model from scratch, simply comment out the cell that contains line 
   learn = load_learner(path,'best_model.pkl') in SECTION 6, and then runall cells.

============================================================================
Input data format

1. The input for both training and test dataset are files in a directory ./data and two csv files which 
contain id and labels. Descriptions are as follows.

    train_data_labels.csv			- A csv file with id of train_id in the first column, abstract in second and corresponding gender 
             					in the thirdcolumn. 
    test_data.csv				- A csv file shares similar structure to train_data_labels.csv but has only less rows. 

    from_arxiv.csv				- A csv contains additional data from Kaggle 

3. best_model.pkl stores trained Longformers. 

The program will read all files. 

============================================================================
Output files

After model has performed classification, the predictions are exported into a csv file. 

    pred_labels.csv			- A csv file shares the same structure with that of test_data.csv 

In case, a model is ran, the best model with maximum validation accuracy will be save into a file named ‘best_model.pkl’.


   

    
     




