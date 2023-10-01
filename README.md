# Autosuggest-using-Markov-Chain-Transition-probabilities
Autosuggest using Markov Chain Transition probabilities:
  - Text-processing, N-gram generation.
  - Demonstrated that Markov Chain transition probabilities gives superior result for auto-suggestion than the N-grams probability for the given dataset.

<img width="1277" alt="Screenshot 2023-10-01 at 12 03 13 PM" src="https://github.com/Aparajita-Sengupta/Autosuggest-using-Markov-Chain-Transition-probabilities/assets/110929917/1674d83f-d05d-4aa5-abaa-1f5facf38efc">


The best model depends on the specific dataset, task, and evaluation criteria. Here are the observations and suggestion for this given task:

OBSERVATIONS:

(1) For the n-gram models, generally, higher n-gram models can capture more context but may suffer from data sparsity issues, while lower n-gram models may provide more general predictions but with less contextual accuracy.

(2) The 1-gram model assigns higher probabilities to most of the predicted words, indicating a stronger association with the input.

(3) On the other hand, the 2-gram model has lower probabilities for some of the predictions, suggesting a weaker association between the input and the predicted words. However, 2-gram model seems to predict more words that are meaningful, as opposed to the 1-gram model. Eventhough it has lesser number of outputs with high probabilities than 1-gram models, many of the outputs of 1-gram model doesn't seem to have any meaning.

(4) The 3-gram model has only one prediction with very low probability. It lacks predictive power as also there is no variability in the output (a single output). Hence, the 3-gram model is not a good model.

(5) Markov Chain model capture the transitional probabilities between words. They focus on the probability of transitioning from one word to the next. The 3-gram suggestion has a high probability but lacks variability because it has only one prediction/suggestion. This suggests that the model might struggle to generate diverse and informative 3-gram suggestions.

(6) The 1-gram and 2-gram models in Markov chain model have more variability. However, glossing over the suggestions, it seems that the 2-gram model is more suitable for the task because the meaningful suggestions like 'going', 'not' etc have higher transitional probabilities than they do in the 1-gram model.

RECOMMENDATION:

My recommendation for this task would be the Markov chain (2-gram) model, although vanilla 2-gram model performs well too and it is a simpler model. This is because Markov chains require less memory compared to n-gram models, especially when considering higher-order models. N-gram models store all observed n-grams and their frequencies, which can quickly become memory-intensive, especially with larger values of n. Markov chains, on the other hand, only need to store the transition probabilities between states, which can be more memory-efficient. Markov chains can dynamically adapt to changing contexts and input sequences. In an n-gram model, the conditional probabilities are fixed based on the training data, and any changes in the context or input sequence would require retraining the model. Markov chains, however, can be updated on the fly by adjusting the transition probabilities based on new observations or interactions. As the order of the Markov chain increases, it considers a larger context window, allowing it to model more complex patterns and dependencies. N-gram models, particularly with smaller values of n, may struggle to capture long-range dependencies effectively. Hence, MC model is more flexible than n-gram model.
POTENTIAL USE CASES:

Some examples of potential use cases: (i) Text Editors: Markov chain models can be trained on a large corpus of text to predict the most likely next word given the preceding words, offering real-time suggestions as users type. (ii) Search engines can employ autosuggest models based on Markov chains to provide query suggestions to users as they type in the search bar. (iii) Email and Messaging Platforms: By analyzing the ongoing conversation or the user's writing style, Markov chain models can generate relevant suggestions, saving time and reducing typing effort. (iv) Code Editors and IDEs: Developers often encounter repetitive coding patterns or commonly used code snippets. (v) E-commerce Platforms: Markov chains can analyze previous search queries, user browsing behavior, and purchase history to recommend relevant products and refine search queries. (vi) Social Media Platforms: Markov chain-based models can capture the dynamics of social media conversations and provide contextually appropriate suggestions.
DRAWBACKS

Drawbacks that would necessitate more complex models: Markov chains assume the Markov property, which states that the probability of transitioning to a future state depends only on the current state and not on the past states. This assumption may not hold in all cases, especially when long-term dependencies or contextual information from earlier states are important. For eg: Time series analysis (current value is often influenced by past observations), recommendation system (recommendation for a user may rely on their past behavior, browsing history, or preferences), speech recognition (accurately transcribing spoken words or phrases requires considering the acoustic and contextual information from earlier states).
<img width="175" alt="Screenshot 2023-10-01 at 12 05 14 PM" src="https://github.com/Aparajita-Sengupta/Autosuggest-using-Markov-Chain-Transition-probabilities/assets/110929917/ca89fea0-e089-43cb-817f-7b37c69bd4ae">

