# Any surprises from your domain from these data?

I did anticipate that this dataset (the set of positive integers) would be fairly irregular. Prime numbers are known for being irregular and unpredictable.

However, when reading through the literature on the topic (other people’s efforts to detect prime numbers with Machine Learning), I cam across a neural network that I had not seen before. Specifically, the neural network was Knowledge Based Cascade Correlation. The paper from Egri and Schultz showed some early promise on the topic, using this different network. A traditionally layered network may not be the correct tool for this task, and I was quite surprised to see that.

# The dataset is what you thought it was?

The dataset was what I thought it was, yes. As the number increases, the probability of it being a prime number decreases. So when the numbers get very a given number is highly unlikely to be prime.

Other than that, I think that breaking each number down into its binary components was a clean solution, but may prove to be a difficult way to encode the representation for the data. This is because there is very little that is special about base-2. In fact, some easily recognizable divisibility rules do not work in base 2, but only work in base -10. For example, all prime numbers must end in one of the following: [1,3,7,9] Detecting this is not an easy thing to do in binary.

# Have you had to adjust your approach or research questions?

After making a basic layered neural network, I found that the model was fitting itself very quickly, and refusing to get any better after even a single epoch. This indicates that this technique will not be the correct approach, I think. However, I am curious if there are certain classes of number that it is consistently misidentifying as primes, and what those numbers have in common. 

I would like to adjust my approach a bit and try the Knowledge Based Cascade Correlation technique mentioned previously. It appears that this technique will only need to add a new layer every $sqrt(n)$ iterations, which is another reason why I would like to give that technique a go.

# Is your method working?

After under sampling the dataset to handle the imbalanced classes (most numbers are not prime, in fact), I was left with a dataset that was half-prime and half-composite. With this restructured dataset and very little forethought given to the structure of the Neural Network, I was able to get an accuracy level of about 77% on the validation data. So yes, in a way, the model is working. Additionally, I found that as I add more numbers into the model, the accuracy improves. Currently, I am only looking into all the numbers up to $2 ^ {20} - 1$, which is already quite a large dataset.

# What challenges are you having?

The biggest challenge that I am facing is that when training the model, it very quickly hits an accuracy ceiling. The model quickly tops out at about 70-80% accuracy. This is concerning, because this indicates that there is very little to learn by running the model for multiple iterations, at least with the current configuration. I tried changing some hyper parameters for the model itself, but that did little to change how quickly the model appeared to learn.

This indicates that there may be some benefit with going with a Knowledge based cascade correlation model instead of a traditional network. I am nervous and excited to give that a go, as the paper mentioned previously indicates that this was a fruitful technique (although only a small dataset was used.) I look forward to trying it with my larger dataset.
