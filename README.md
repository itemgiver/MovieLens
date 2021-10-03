# MovieLens

![image](https://user-images.githubusercontent.com/87184009/127741772-e7dce7af-1d76-4720-a320-6a87f695c1c8.png)

## Introduction

MovieLens data can be used in recommendation system research. It has millions of real-world ratings. \
Movie ratings are made on a 5-star scale, with half-star increments (0.5 stars - 5.0 stars). \
In this project, we will find out good preprocessing steps and models using evaluation metrics such as HR@10, NDCG@10, and RMSE.

## Recommender-System-Study

논문들과 DEVIEW, Search Colloquium 영상들을 보며 Recommender System을 공부함. \
Graph Convolutional Neural Networks in Recommender Systems에 흥미를 가지게 됨.

## Experiment Result
최종 rating 값 예측에서는 (sigmoid output) * 5.5로 실험한 것이 가장 좋은 성능을 보임 \
L2 regularization이 효과가 있는 것을 확인함 \
Batch Normalization, Dropout 방식은 오히려 성능을 저하시키는 것을 확인함. \
Adam optimizer의 성능이 RAdam optimizer보다 좋은 것을 확인함 \
Matrix Factorization, MLP layer을 섞은 wide-and-deep 모델이 성능이 좋은 것을 확인함

## Training



## Result

Test RMSE = 0.7677

Difference between the actual value and the predicted value Histogram\
![image](https://user-images.githubusercontent.com/87184009/135738882-dd9aa3f7-549a-4858-bd20-ba4c83c17d36.png)

## Conclusion
구현한 모델의 성능이 MovieLens 10M에서는 RMSE : 0.7677를 얻으며 \
다른 모든 RMSE 0.77x 대의 논문들보다 좋은 성능을 보이는 것을 확인함.

## Further Research
"On the Difficulty of Evaluating Baselines: A Study on Recommender Systems" 논문을 보면 \
Matrix Factorization만으로 RMSE가 0.772가 나오는데 어떻게 이게 가능한 것인지 더 연구해봐야될 필요가 있음. \
추가적으로 HR@10, NDCG@10 모델을 새로 구현하고 실험해볼 필요가 있음. \
다만 HR@10, NDCG@10은 explicit feedback을 implicit feedback을 바꾸는 검증되지 않은 방법이 이용되기 때문에 조금 더 생각해봐야될 필요가 있음.

## Benchmark
https://paperswithcode.com/sota/collaborative-filtering-on-movielens-10m?metric=RMSE \
https://paperswithcode.com/sota/collaborative-filtering-on-movielens-20m?metric=RMSE

## References
https://grouplens.org/datasets/movielens/
