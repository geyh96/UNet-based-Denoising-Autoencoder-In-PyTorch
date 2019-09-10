# UNet-based-Denoising-Autoencoder
Cleaning printed text using Denoising Autoencoder based on UNet architecture in PyTorch

## Requirements
* torch >= 0.4
* opencv-python
* numpy
* matplotlib
* tqdm

## Generating Synthetic Data
Set the number of total synthetic images to be generated **num_synthetic_imgs** and set the percentage of training data **train_percentage** in *config.py*
Then run
```
python generate_synthetic_dataset.py
```
It will generate the synthetic data in a directory named *data* (can be changed in the config.py) in the root dirctory.

## Training
Set the desired values of **lr**, **epochs** and **batch_size** in *config.py*
* ### Start Training
  In *config.py*,
  * Set **resume** to False
  ```
  python train.py
  ```
* ### Resume Training
  In *config.py*,
  * set **resume** to True and
  * set **ckpt** to the path of the model to be loaded, i.e. ckpt = 'model02.pth'
  ```
  python train.py
  ```

## Testing
Set **test** to True 
In *config.py*, set your **test_dir** which contains the noisy images that you need to denoise, and **test_bs** which is the batch size for the test set.
```
python test.py
```
Once the testing is done, the results will be saved in a directory named *results*
