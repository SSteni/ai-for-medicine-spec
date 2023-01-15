# ai-for-medicine-spec
Coursera specialisation on AI for Medicine

# What is class imbalance?
The classic example is a medical dataset like this one.

There's not an equal number of examples of non-disease and disease in medical datasets. This is a reflection of the prevalence or the frequency of disease in the real-world, where we see that there are a lot more examples of normals than of mass, especially if we're looking at X-rays of a healthy population. In a medical dataset, you might see 100 times as many normal examples as mass examples.

The algorithm is optimizing its updates to get the normal examples, and not giving much relative weight to the mass examples. 

# Methods to tackle class imbalance

- Weighted Loss :
The solution to the class imbalance problem is to modify the loss function, to weight the normal and the mass classes differently. the weight we'll put on the positive class will be the number of negative examples over the total number of examples. In our case, this is six normal examples over eight total examples. The weight we'll put on the negative class will be the number of positive examples over the total number of examples, which is two over eight.

- Resampling (Undersampling, Oversampling)

# Neural Network architectures are data hungry. Most times we dont have millions of data, so how to apply these techniques when we dont have so much data?

One solution is to pre-train the network using general data. Then use the weights to train out custom data (transfer learning). Through pretraining, the netwwork will learn general features such as edges. When we transfer these features to our new network, the network can learn the new task of chest X-ray interpretation with a better starting point. This first step, is called pre-training, and the second step, is called fine-tuning. 

The early layers of the network captures low level features such as edges and the later layers capture more high-level or task-specific details.
So when we fine-tune the network on chest X-rays, instead of fine-tuning all features we've transferred, we can freeze the features learned by the shallow layers and just fine-tune the deeper layers. In practice, two of the most common design choices are one, to fine-tune all of the layers, and two, only fine-tune the later or the last layer and not fine-tune the earlier layers. This approach of pre-training and fine-tuning, is also called transfer learning and is an effective way to tackle the small dataset size challenge.
