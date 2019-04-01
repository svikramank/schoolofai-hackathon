# schoolofai-hackathon

## Steps:
- Unzip the data file
- First, run the notebook `psLoveDataCreation.ipynb`. This will create the data that needs to be used as input in the model. The data is saved in file `augmented_data`
- Then run the file `PSLove.ipynb`. If `augmented_data` is not found, fix path in the variable `data_path` in `PSLove.ipynb`
- The plot showing the accuracy can be seen, once all cells are run.
![Alt text](plot.png?raw=true "Accuracy and Loss")
