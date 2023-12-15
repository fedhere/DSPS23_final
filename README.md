# DSPS23_final
Final exam for DSPS

READ THE INSTRUCTIONS IN THE EXAM NOTEBOOK WITH ATTENTION! 

https://github.com/fedhere/DSPS23_final/blob/main/DSPS2023_final.ipynb

Note the delivery modality:

- Remember to copy this notebook to your own Google Drive _before_ you start working.
- Share this notebook with Dr. Bianco and Willow to submit.
    - Press the 'Share' button in the top right.
      <img width="856" alt="Screen Shot 2023-12-15 at 6 31 24 PM" src="https://github.com/fedhere/DSPS23_final/assets/1696902/d70ed317-86fb-4396-b7f5-a7eaf1434dfd">

    - Make us editors when you share the notebook.
    - Share the notebook with our emails:
        - fbianco@udel.edu
        - fortino@udel.edu.
     <img width="503" alt="Screen Shot 2023-12-15 at 6 31 10 PM" src="https://github.com/fedhere/DSPS23_final/assets/1696902/12db2591-ff50-44d9-9dac-3cf408cd6354">

- Do _not_ push your work to GitHub. This will enable anyone to see your work. If you do this by accident, let Willow or Dr. Bianco know and we can help you remove it permanently from GitHub.


DONT STAY STUCK!! Here are some tips and solutions for possible errors you may encounter. 

## 1 Data Acquisition

If you see this

<img width="552" alt="Screen Shot 2023-12-14 at 12 02 05 PM" src="https://github.com/fedhere/DSPS23_final/assets/1696902/840c8b79-5048-4165-80af-e07d0ec9f156">

It means your credentials are not read it or they are incorrect. Make sure you set the credentials as we did in the Titanic notebook

<img width="557" alt="Screen Shot 2023-12-14 at 12 03 14 PM" src="https://github.com/fedhere/DSPS23_final/assets/1696902/daf254cb-9b10-4015-96ab-7e44e2efa29b">

If you see this

<img width="556" alt="Screen Shot 2023-12-14 at 12 05 07 PM" src="https://github.com/fedhere/DSPS23_final/assets/1696902/bd05d20e-0a36-48f6-b7b7-a19f0242dc34">

You have not agreed to the terms of conditions. Go on the Kaggle website for this challenge and “Join the challenge” in the Data tab


Remember to put the data into your drive you will have to make a folder called DSPS23_final (use the command `!mkdir`) and move to that folder after creation with the command `cd DSPS23_final` or `cd /content/drive/MyDrive/DSPS23_final` depending on where you are

**The data is large** : if at any points your code is too slow to do whatever you are trying to do on all the data or it takes too much memory consider _subsampling_



## 2.4 Suggestion on how to merge (task 2 Data Cleaning and Preparation)
 - First, merge the `structures` dataframe into the `train` dataframe by matching the columns `molecule_name` and `atom_index_0` from `train.csv`, to the columns `molecule_name` and `atom_index` from `structures.csv`.
    - Next, _again_ merge the `structures` dataframe intto the (now augmented) `train` dataframe by matching the columns `molecule_name` and `atom_index_1` from `train.csv`, to the columns `molecule_name` and `atom_index` from `structures.csv`.

Merging Pandas DataFrame objects can be quite difficult. See the documentation [here](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.merge.html). To merge two DataFrame objects, `df1` and `df2`, the basic usage is as follows where `df1_column1` and `df1_column2` from `df1` are being matched to `df2_column1` and `df2_column2` from `df2`.

    df_merged = df1.merge(
        df2,
        left_on=[df1_column1, df1_column2],
        right_on=[df2_column1, df2_column2],
    )

***

## 2.5 One Hot Encoding: 
See it implemented in the autoencoders notebook [here](https://github.com/fedhere/DSPS_FBianco/blob/main/ClassDemos/DSPS2023_autoencoders_8dec23_solns.ipynb). That implementation used the Keras function `to_categorical` but we also used `pd.get_dummies` (see its documentation [here](https://pandas.pydata.org/docs/reference/api/pandas.get_dummies.html)).

## 4 Modeling

This is a lot of data! While you are experimenting you probably want to use only a subset of the data, like I suggested above for the visualizations. Before you submit, be sure to run your model on the entire dataset.
