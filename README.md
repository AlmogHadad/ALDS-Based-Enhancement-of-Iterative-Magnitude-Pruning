# ALDS-Based-Enhancement-of-Iterative-Magnitude-Pruning

Authors:
  - Meir Goldberg
  - Almog Hadad
  
A Novel Approach for Neural Network Compression.
Using ALDS compression to improve IMP compression Maintain accuracy.

## Automatic Layer-wise Decomposition Selector (ALDS):
    
  Per layer compression:
  
   - Weight tensor is folded into a matrix
      
   - Uses an SVD to compress the weights
      
  Global compression:
  
   - Ensure global compression rate across all layers
      
   - Maintain model accuracy
      
   - Demonstrated to achieve accurate compression of over 60% on known neural networks

## Iterative Magnitude Pruning (IMP):

  - Based on the lottery ticket hypothesis:
A dense randomly initialized feed-forward network contains subnetworks (known as winning tickets) that when trained in isolation reach a test accuracy comparable to the original network in a similar number of iterations.

Identify the winning ticket:
  
  - Train the network
  
  - Prune the smallest magnitude weights
  
  - Winning tickets can be less than 10-20% the size of the full network

## Generic Compression Procedure:
  ![image](https://user-images.githubusercontent.com/77130590/236485759-8efd245d-bd53-49a8-9fa7-dad52b859255.png)

## Our Compression Procedure:
![image](https://user-images.githubusercontent.com/77130590/236485977-b27bd873-1ebe-4100-9ccd-3f412783e4ee.png)

## Our Model that we tested:

  - 6 convolutional layers
  
  - 3 FC layers

  -Using CIFAR-10 as our dataset

## Defining the ALDS Compression Rate:

  - Run compression with a fixed value

  - Reset the net

  - Repeat
  
  ![image](https://user-images.githubusercontent.com/77130590/236486700-a9a0e4e5-aaaf-4c87-8c0e-1aaa6c06b878.png)
  
## Results:
![image](https://user-images.githubusercontent.com/77130590/236487023-8032249c-a505-40b2-9d0a-17cf8ecd0581.png)

## Results Analysis:

Real understanding of the results – further analysis requires more resources
Our assumption:
	
  - ALDS reduced the values of insignificant parameters
	
  - Maybe also increased the values of significant parameters
  
  - This assisted IMP in pruning the more insignificant parameters
	
  - also likely: ALDS prevented IMP from removing entire layers



