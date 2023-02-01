# AI for medicine specialization
Coursera specialisation on AI for Medicine
Comprises of three sets:
- Diagnosis
- Prognosis
- Case Study

# Diagnosis

## What is class imbalance?
The classic example is a medical dataset like this one.

There's not an equal number of examples of non-disease and disease in medical datasets. This is a reflection of the prevalence or the frequency of disease in the real-world, where we see that there are a lot more examples of normals than of mass, especially if we're looking at X-rays of a healthy population. In a medical dataset, you might see 100 times as many normal examples as mass examples.

The algorithm is optimizing its updates to get the normal examples, and not giving much relative weight to the mass examples. 

## Methods to tackle class imbalance

- Weighted Loss :
The solution to the class imbalance problem is to modify the loss function, to weight the normal and the mass classes differently. the weight we'll put on the positive class will be the number of negative examples over the total number of examples. In our case, this is six normal examples over eight total examples. The weight we'll put on the negative class will be the number of positive examples over the total number of examples, which is two over eight.

- Resampling (Undersampling, Oversampling)

## Neural network architectures are data hungry. Most times we dont have millions of data, so how to apply these techniques when we don't have so much data?

1. Transfer Learning
One solution is to pre-train the network using general data. Then use the weights to train out custom data (transfer learning). Through pretraining, the netwwork will learn general features such as edges. When we transfer these features to our new network, the network can learn the new task of chest X-ray interpretation with a better starting point. This first step, is called pre-training, and the second step, is called fine-tuning. 

The early layers of the network captures low level features such as edges and the later layers capture more high-level or task-specific details.
So when we fine-tune the network on chest X-rays, instead of fine-tuning all features we've transferred, we can freeze the features learned by the shallow layers and just fine-tune the deeper layers. In practice, two of the most common design choices are one, to fine-tune all of the layers, and two, only fine-tune the later or the last layer and not fine-tune the earlier layers. This approach of pre-training and fine-tuning, is also called transfer learning and is an effective way to tackle the small dataset size challenge.

2. Data Augmentation
Tricking the network into thinking that we have more data at our disposal than we actually do.
- Translation
- Rotations
- Brightness/contrast variability
- Or a combination of all this

Two aspects to keep in mind while performing data augmentation are:
* Do augmentations reflect variations in real world?
* Do augmentations keep the label the same?

## Model Testing

Training Set - Development of models
Validation Set - Tuning and Selection of models
Test Set - Reporting of Results

Cross-validation to reduce variability in our estimate of the model performance.

3 key challenges in building these sets:
1. Patient Overlap : how we make these sets independent - results in overly optimistc test set performance because the model would have already memorized the training set features. One way to tack this problem is to keep all the images that belong to a patient should be kept in the same set (Use Patient ID).
2. Set Sampling : Test set may not always have enough number of samples with masses. One solution to this is to keep Test set with atleast x% minority class. Sometimes set to 50% (50 mass and 50 non-mass). The same sampling strategy is used in sampling the validation set, because we want the validation set to reflect the test set. And finally the remaining samples can be included in the training set.
3. Ground Truth : Consensus Voting / More definitive test

## Accuracy Metrics

1. Sensitivity and Specificity 

![alt text](https://github.com/SSteni/ai-for-medicine-spec/blob/main/Accuracy.png)

2. Accuracy

![alt text](https://github.com/SSteni/ai-for-medicine-spec/blob/main/Accuracy2.png)

3. Positive Predictive Value (PPV) and Negative Predictive Value (NPV)




