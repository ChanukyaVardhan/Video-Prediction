# DL Competition

## Setup environment:
```
cd ./our_OpenSTL
conda env create -f environment.yml
conda activate OpenSTL  # Or check if your env already has the requirements.
python setup.py develop # This will create 'openstl' as a package
```

## Running on the hidden set
```bash
python test_hidden.py
```
change the ```data_dir``` variable to the path of the root dir where the hidden dataset (hidden) folder exists.

```stacked_pred_hidden_heur.pt``` is the output file.

## Running on the validation set
```bash
python test_hidden.py
```
change the ```data_dir``` variable to the path of the root dir where the hidden dataset (hidden) folder exists.
change the ```split``` variable to ```val```.

```stacked_pred_hidden_heur.pt``` is the output file.


## Training SimVP 

```
cd ./our_OpenSTL
python tools/clevrer_train.py \
    --epoch 100 \
    --dataname "clevrer" \
    --data_root "../../../Dataset_Student" \
    --method "SimVP" \
    --ex_name "14000cleanvids_simvp_batch" \
    --auto_resume \
    --batch_size 1 \
    --val_batch_size 4 \
    --fp16 \
    --device "cuda" \
    --use_gpu True
```

--dataname  : to load our data

--data_root : Where Dataset_Student lives

--ex_name   : Name of the experiment. As of now, the model files will be saved in ./work_dirs/exp_name/



# DeepLabv3
## Training Deeplabv3

```bash
python train_deeplabv3.py
```
change ```data_dir``` in ```./config/segmentation_deeplabv3.yml``` to the path of the root dir where the train dataset is.

## Running deeplabv3 on the hidde set
```bash
python label_with_deeplabv3.py
```
Run with the same config file as the one mentioned in train.