# PHSX815_Week11

This repository includes a neural network tutorial using Keras (jupyter notebook). The following libraries are required to run this notebook:
- `matplotlib`
- `numpy`
- `sklearn`
- `pandas`
- `tensorflow`

Optionally, you can use the `seaborn` visualization package.


## Changes Made (also written in notebook)
### Making Changes
Some changes to make: 
- Test/train fraction of initial dataset. Currently 90% train, 10% test. If we decrease the train fraction, we may get worse performance on our categorization of our test data.
    - Results: The performance of the model didn't actually seem to change that much decreasing the train/test fraction down to 50/50. However, as expected, the histograms of test/training labels ended up basically perfectly overlapping because the number of samples ended up the same. If the fraction goes to 90% test, 10% train, we start to see worse performance, with ~45% accuracy vs ~51% accuracy in the 90% train, 10% test case, and the wine scores are skewed worse by about a point.
    
    
- Number of Layers: Adding 3 extra hidden layers: should more severely overfit our dataset.
    - Validation loss pretty clearly diverges from training loss around epoch 15, and actually increases until epoch 100.
    

- Validation split: 
    - Changing the validation split to larger and larger values tends to make the model overfit more and more, as evidenced by the quick divergence of the training and validation losses. As the model just continues to fit the same dataset, though, the performance doesn't change that much.
    

- \# Epochs: More epochs should overfit the data more, fewer should underfit (or more appropriately fit?)
	- 200 epochs definitely overfits the data. 50 epochs seems like it doesn't overfit the data, but given the (small) test dataset it seems sort of hard to tell whether this gives some qualitatively different fit. It gives ~50% accuracy though.


- Batch size: smaller batch sizes should take longer, should be less accurate
    - batch size of 10 definitely takes longer, but is not clear that the fitting accuracy is any worse than keeping the batch size at 100