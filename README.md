**Kaggle-Feedback-ELL-2023-Competion**

The Kaggle competion can be found using the following link:
https://www.kaggle.com/competitions/feedback-prize-english-language-learning

The goal of this Kaggle competition was to assess the language proficiency of 8th-12th grade English Language Learners (ELLs). It utilized a dataset of essays written by ELLs (students). The challenge required to pay attention on the proficiency of language by assessing 6 different aspects of a language in terms of cohesion, syntax, vocabulary, phraseology, grammar, and conventions. This challenge can be effectively treated as a multi-variate regression problem. The competition uses the average of the MCRMSE (mean column-wise root mean squared error) of the six targets mentioned earlier as the evaluation indicator. 

For the challenge, I used various BERT models including debert-v3-base, debert-v3-large, debert-v2-xlarge, debert-v2-xxlarge to encode the given text. Among these models, debert-v3-large was the best pre-trained encoding model. After getting the encoding vector, the vector was given as input to a multi-layer neural network MLP, the corresponding output of which was the scoring vector with dimension 6. In addition, the problem was also transformed into a classification problem for modeling. A linear transformation was performed on the output result (between 0-1) to obtain a score of 1-5.

For the challenge two different deep learning frameworks- Pytorch and Tensorflow were used. As mentioned above MCRMSE was the loss function, Adam was the optimizer for model training, and Optuna was used for model parameter tuning. 

In the end, eight model results were received. Through the offline verification score, the model fusion weight was determined using the linear weighted average method. The model ranked 155 and received qualified for a bronze medal. 

Step-by-step guide on how to obtain the model results for the competition:
 
(1) Download the dataset to the Kaggle-Comp-ELL-2023/input folder (Dataset download address: https://www.kaggle.com/competitions/feedback-prize-english-language-learning/data)

(2) Run the bert-based regression model in Kaggle-Comp-ELL-2023/code/fb3_deberta_base_train.ipynb (Different BERT models such as bert-v3-base, bert-v3-large, bert-v2-xlarge, or bert-v2-xxlarge can be used for training)

(3) Then run the bert-based classification model in Kaggle-Comp-ELL-2023/code/fb3_deberta_base_clf.ipynb, and save the trained weights to the input/debertclassification path

(4) Finally, run the infer-code in Kaggle-Comp-ELL-2023/code/fb3_infer.ipynb. If you don't want to train the inferred weight, you can download it directly using the following links: 

[0911-deberta-v3-base](https://www.kaggle.com/datasets/kojimar/0911-deberta-v3-base)

[0911-deberta-v3-large](https://www.kaggle.com/datasets/kojimar/0911-deberta-v3-large)

[0911-deberta-v2-xlarge](https://www.kaggle.com/datasets/kojimar/0911-deberta-v2-xlarge)

[0913-deberta-v3-base-fgm](https://www.kaggle.com/datasets/kojimar/0913-deberta-v3-base-fgm)

[0914-deberta-v3-large-fgm](https://www.kaggle.com/datasets/kojimar/0914-deberta-v3-large-fgm)

[0919-deberta-v2-xlarge](https://www.kaggle.com/datasets/kojimar/0919-deberta-v2-xlarge)

[0919-deberta-v2-xlarge-mnli](https://www.kaggle.com/datasets/kojimar/0919-deberta-v2-xlarge-mnli)

[0925-deberta-v3-large-unscale][0919-deberta-v2-xlarge-mnli](https://www.kaggle.com/datasets/kojimar/0925-deberta-v3-large-unscale)

[0926-deberta-v3-large-unscale](https://www.kaggle.com/datasets/kojimar/0926-deberta-v3-large-unscale)

[0927-deberta-v3-large-unscale](https://www.kaggle.com/datasets/kojimar/0927-deberta-v3-large-unscale)
