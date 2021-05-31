This is the source code of SFCC.
# Install module and download the UCR datasets
```
pip install -r requirements.txt
```
download UCR datasets at http://www.timeseriesclassification.com  
we just provide two instance datasets `Coffee` and `Earthquaks` which are in the directory `UCRArchive_2018`.
# Train with args 
```angular2
python train.py --aug --model r --run_tag Coffee --n_group 4 --runs 3
```
which means you train the ResNet with SFCC augmentation method on Coffee dataset for 3 runs and the   
number of stratified groups is 4. You can set the args according to the `train.py`

# Augment the dataset
`dft_aug.py` is the main file to implement the SFCC method.  
You can run the file to augment the specific dataset by setting the source code in`if __name__=='__main__'`  
where the function `stratify_by_label` return the data with different classes and the
`data_aug_by_dft` receive the data from it to generate the synthetic data by SFCC.