
# Description
Dialogue systems are widely used in applications ranging from technical support services to language learning tools and entertainment. In the field of dialogue systems, multi-turn dialogue response generation is one of the main challenges. This repository tries to finetune the model with the DailyDialog dataset and evaluate the model's performance with perplexity, BLEU and ROUGE. 

## Data parsing
I will parse the data to the text format with the parsing script from [this repository](https://github.com/Sanghoon94/DailyDialogue-Parser).

## Date preprocessing 
For the experiment, the following code will convert the dataset to every response row containing eight previous responses as a context since the dataset has an average of eight turn conversations. Furthermore, we will add a special token 'EOS' between responses to let the model know the end of each response in a string.

## Evaluation
Before the evaluation, we will preprocess the reference response as the dataset contains some invalid punctuation, like sentences with extra whitespace. 

- Perplexity:  11.436

- BLEU

|   | Cumulative BLEU | Individual BLEU |
|---|-----------------|-----------------|
| 1 | 0.0158          | 0.0158          |
| 3 | 0.0696          | 0.1194          |
| 4 | 0.0705          | 0.0920          |

- Rouge

|   | Rouge |
|---|-------|
| 1 | 0.141 |
| 2 | 0.032 |
| L | 0.131 |
