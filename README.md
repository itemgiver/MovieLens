# MovieLens

![image](https://user-images.githubusercontent.com/87184009/127741772-e7dce7af-1d76-4720-a320-6a87f695c1c8.png)

## Introduction
영화 평점 데이터를 보고 rating을 예상하는 모델들을 실험하고 RMSE 값을 줄이는 방법을 고민한 연구.

Movie Rating은 0.5점 단위로 구성되어있으며 0.5점부터 5점까지의 값이 존재함. \
MovieLens 데이터는 추천시스템 연구에 자주 사용되는 데이터로 HR@10, NDCG@10, RMSE 등의 평가지표가 있음.

## Experiment Result
U를 user, M을 movie, G를 genres로 두고 각각 embedding 한 후 User Embedding Size = 64로 실험함. \
최종 rating 값 예측에서는 (sigmoid output) * 5.5로 실험한 것이 (sigmoid output)*4.5 + 0.5보다 좋은 성능을 보였음. \
Embedding의 비율을 M이 75%, G를 25%로 해서 concatenate한 movie latent vector의 성능이 가장 좋았음. \
Batch Normalization, Dropout 방식은 오히려 성능을 저하시키는 것을 확인함. \
Adam optimizer의 성능이 신기술인 RAdam보다 좋은 것을 확인함.

Matrix Factorization 알고리즘만 이용했을 때는 RMSE가 0.8이 훨씬 넘었음. \
MLP Layer와 Matrix Factorization를 섞은 NeuMF 구조를 이용하니 \
MovieLens 10M에서는 RMSE : 0.7851, MovieLens20M에서는 RMSE : 0.7841 결과가 나옴

## Conclusion
Matrix Factorization에 MLP Layer을 섞은 Neural Network 구조가 가장 좋은 성능을 보이는 것을 확인함. \
"On the Difficulty of Evaluating Baselines: A Study on Recommender Systems" 논문을 보면 \
Matrix Factorization만으로 RMSE가 0.772가 나오는데 어떻게 이게 가능한 것인지 더 연구해봐야될 필요가 있음. \
추가적으로 HR@10, NDCG@10 모델을 새로 구현하고 실험해볼 필요가 있음. \
다만 HR@10, NDCG@10은 explicit feedback을 implicit feedback을 바꾸는 검증되지 않은 방법이 이용되기 때문에 조금 더 생각해봐야될 필요가 있음.

## Benchmark
https://paperswithcode.com/sota/collaborative-filtering-on-movielens-10m?metric=RMSE \
https://paperswithcode.com/sota/collaborative-filtering-on-movielens-20m?metric=RMSE

## References
https://www.kaggle.com/smritisingh1997/movielens-10m-dataset \
https://www.kaggle.com/grouplens/movielens-20m-dataset
