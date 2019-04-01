# schoolofai-hackathon

## Approach:
We chose the Challenge No.4 - psLove challenge where the idea was to build an end to end pipeline to predict start date of an upcoming period for a female user to help her analyze the fertile window, predict symptoms and correlation. 

## Idea:
We divided the problem into two stages - Stage 1 & Stage 2:
  **Stage 1**
  We found out the data that was provided to was highly garbled and needed a lot of cleaning and pre-processing. 
  We undertook major steps to make sure the data is good for the model to ingest. 
  A major step in our pre-processing stage was **Data Augmentation** where we divided large sequence data of women into      smaller chunks to augment the data and have a good distribution. 
  
  **Stage 2**
  Here we did the encoding of the data and fed it into a Seq2Seq Attention Model to predict the next period cycle along with the probability of symptoms on each day in the cycle. 
  
## Future Work
- We understand that here we are dealing with a specific case where we want the model to be personalized for each of our user and hence want the model to overfit (in a better way). 
- We propose a multi-step training process where we maintain a **global model** which is trained to generalize on all the data the company (psLove). 
- Once we get a decent performance on the global model, we share that model with each of our user **local model** to finetune with the sequence data that each user has or feeds in to the model, thus leading to a **online learning process**. 



## Steps:
- Unzip the data file
- First, run the notebook `psLoveDataCreation.ipynb`. This will create the data that needs to be used as input in the model. The data is saved in file `augmented_data`
- Then run the file `PSLove.ipynb`. If `augmented_data` is not found, fix path in the variable `data_path` in `PSLove.ipynb`
- The plot showing the accuracy can be seen, once all cells are run.
![Alt text](plot.png?raw=true "Accuracy and Loss")
