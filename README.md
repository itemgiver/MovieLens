# MovieLens

## Introduction
User와 Item을 보고 rating을 예상하는 프로그램

## Experiment
U를 user, M을 movie, G를 genres로 두고 각각 embedding 한 후 User Embedding Size = 64로 실험함.

## Result
Matrix Factorization 알고리즘은 RMSE가 0.8이 훨씬 넘었음.
MLP Layer와 Matrix Factorization를 섞은 NeuMF 구조를 이용하니 MovieLens 10M에서는 RMSE : 0.7877, MovieLens20M에서는 RMSE : 0.7841 결과가 나옴

## Benchmark
https://paperswithcode.com/sota/collaborative-filtering-on-movielens-10m?metric=RMSE
https://paperswithcode.com/sota/collaborative-filtering-on-movielens-20m?metric=RMSE

## References
https://www.kaggle.com/smritisingh1997/movielens-10m-dataset
https://www.kaggle.com/grouplens/movielens-20m-dataset
