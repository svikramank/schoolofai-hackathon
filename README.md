# SolaceAI - We help you stay prepared!

Full Presentation here - https://docs.google.com/presentation/d/1wmOoF_9GTYdhgDAV2UDR1bzNEdjPP_bK4WcK6O1-K_M/edit?usp=sharing

## Problem & Motivation:
With SolaceAI we plan to make women better prepared for their upcoming period rather than being surprised by it. We believe that the past data from previous cycles faced by women can be leveraged to predict their next period and help them plan better for the day and the possible symptoms that could occur.

## Approach:
We chose the Challenge No.4 - psLove challenge where the idea was to build an end to end pipeline to predict start date of an upcoming period for a female user to help her analyze the fertile window, predict symptoms and correlation. 

## Idea:
We divided the training of model into two stages - Stage 1 & Stage 2:
![Alt text](4.png?raw=true "Multi-step learning")

  **Stage 0**
  We found out the data that was provided to was highly garbled and needed a lot of cleaning and pre-processing. 
  We undertook major steps to make sure the data is good for the model to ingest. 
  ![Alt text](5.png?raw=true "Data Pre-processing")
  
  We divided the training of model into two stages - Stage 1 & Stage 2:
  
  A major step in our pre-processing stage was **Data Augmentation** where we divided large sequence data of women into      smaller chunks to augment the data and have a good distribution. 
  ![Alt text](1.png?raw=true "Centralized Model")
  
  **Stage 1 & 2 **
  Here we did the encoding of the data and fed it into a Seq2Seq Attention Model to predict the next period cycle along with the probability of symptoms on each day in the cycle. 
  ![Alt text](3.png?raw=true "Personalized Learning - Lifelong online training process")
  
## Future Work
- We understand that here we are dealing with a specific case where we want the model to be personalized for each of our user and hence want the model to overfit (in a better way). 
- We propose a multi-step training process where we maintain a **global model** which is trained to generalize on all the data the company (psLove). 
- Once we get a decent performance on the global model, we share that model with each of our user **local model** to finetune with the sequence data that each user has or feeds in to the model, thus leading to a **online learning process**. 
![Alt text](6.png?raw=true "Federated Learning")


## To reproduce the results, Follow these steps:
- Unzip the data file
- First, run the notebook `psLoveDataCreation.ipynb`. This will create the data that needs to be used as input in the model. The data is saved in file `augmented_data`
- Then run the file `PSLove.ipynb`. If `augmented_data` is not found, fix path in the variable `data_path` in `PSLove.ipynb`
- The plot showing the accuracy can be seen, once all cells are run.
![Alt text](plot.png?raw=true "Accuracy and Loss")


## Contact Information
Vikramank Singh - vikramank@berkeley.edu
Rahul Nangia - rahul_nangia@berkeley.edu 
