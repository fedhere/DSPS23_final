# DSPS23_final
Final exam for DSPS


DONT STAY STUCK!! Here are some tips and solutions for possible errors you may encounter. 

## 1 Data Acquisition

If you see this

<img width="552" alt="Screen Shot 2023-12-14 at 12 02 05 PM" src="https://github.com/fedhere/DSPS23_final/assets/1696902/840c8b79-5048-4165-80af-e07d0ec9f156">

It means your credentials are not read it or they are incorrect. Make sure you set the credentials as we did in the Titanic notebook

<img width="557" alt="Screen Shot 2023-12-14 at 12 03 14 PM" src="https://github.com/fedhere/DSPS23_final/assets/1696902/daf254cb-9b10-4015-96ab-7e44e2efa29b">

If you see this

<img width="556" alt="Screen Shot 2023-12-14 at 12 05 07 PM" src="https://github.com/fedhere/DSPS23_final/assets/1696902/bd05d20e-0a36-48f6-b7b7-a19f0242dc34">

You have not agreed to the terms of conditions. Go on the Kaggle website for this challenge and “Join the challenge” in the Data tab


If you are trying to get data from the github repo and you see this 



<img width="642" alt="Screen Shot 2023-12-12 at 2 49 52 PM" src="https://github.com/fedhere/DSPS23_final/assets/1696902/06d8989c-ded3-4b77-9256-0fd51916d18c">

remember to get the link for the _raw_ data, not the data as it appears rendered on github





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
