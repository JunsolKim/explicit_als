# explicit_als

This notebook presents the ALS (alternate least square) algorithm, which can be used for collaborative filtering based on "explicit feedbacks (e.g., ratings)," rather than implicit feedbacks (e.g., clicks). The model predicts whether users are likely to rate items positively or negatively.

## Description
  - The model is similar to the one proposed in "Collaborative Filtering for Implicit Feedback Datasets (Hu et al., 2008)." We decompose the user-item rating matrix P (element p ui represents a user U's rating of an item I) into the dot product of two latent matrices X and Y.
  - However, the goal is to predict the "rating," rather than the consumption. Thus, a confidence level of an item preference is defined differently. In the following loss function, p_ui is a rating of an user u on an item i, and c_ui is a confidence level (1 if user rated item i, 0 if user did not). c_ui allows the model to ignore missing values when optimizing X and Y. x_u and y_i are u-th and i-th row of X and Y, respectively.
<img width="577" alt="image" src="https://user-images.githubusercontent.com/13177827/203404778-70fb48b0-e129-489c-adb0-408574aee947.png">
  - X and Y are optimized using the ALS algorithm as follows. See Hu (2008) for details.
<img width="430" alt="image" src="https://user-images.githubusercontent.com/13177827/203404971-ae227764-6ab7-4287-a655-9664a2583803.png">

## Performance
  - We trained the model using MovieLens 1M (train:test=90:10). The correlation between predicted and observed ratings is as follows.
  - Pearson correlation: 0.519
  - MSE: 1.138


![image](https://user-images.githubusercontent.com/13177827/203416468-4ddc3d5e-0fcd-4381-bb48-d98cff1852d7.png)


## Reference
  - Hu, Y., Koren, Y., & Volinsky, C. (2008, December). Collaborative filtering for implicit feedback datasets. In 2008 Eighth IEEE international conference on data mining (pp. 263-272). IEEE. https://ieeexplore.ieee.org/abstract/document/4781121/
