# Assignment 3 - Spam Classification

## Approach
- I decided to go with a naïve Bayes algorithm as I know from my research they're accurate and relatively straightforward to grasp and implement.  
- Other options, which could have yielded similar if not marginally higher accuracy, would have been Neural Networks (NN) or Support Vector Machines (SVM).
- However these are more complex to implement, especially without using 3rd party libraries and frameworks, and they wouldn't be significantly more accurate. 

## Explaining the code
- The naïve Bayes classifier builds a model for the probability that a given message belongs to a certain class - 𝑝(𝐶=𝑐 | message).
- A new message, from the test data, is then classified based on the Bayesian maximum a posteriori estimate - 𝑐̂ =argmax 𝑝(𝐶=𝑐 | message) where 𝑐∈{0,1}.
  - That's a fancy way of saying, an email is classified as spam or ham depending on which probability is greater. 
- Under Bayes rules we can say 𝑝(𝐶=𝑐 | message)∝𝑝(message | 𝐶=𝑐)𝑝(𝐶=𝑐). The proability that a given message belongs to a certain class is proportional to:
  - The conditional probability of a message given C is true i.e. given C = ham or spam. 
  - the probability of observing each class, which is known as the prior probabilities or class priors.
 
- In the first part of the code 'estimate_log_class_priors()' we calculate the 𝑝(𝐶=𝑐) of the equation.
- This is just the proportion of emails that are classed as ham and spam respectively.
- We then calculate the natural logarithm of the proportions - so log(p(C=0)) and log(p(C=1)).
- The use of log probabilities improves numerical stability, when the probabilities are very small, because of the way in which computers approximate real numbers.


