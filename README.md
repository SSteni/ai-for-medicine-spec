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
