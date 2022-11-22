# explicit_als

This repository contains the ALS algorithm, which can be used for collaborative filtering based on "explicit feedbacks (e.g., ratings)," rather than implicit feedbacks (e.g., clicks). The model predicts whether users will rate items positively or negatively.

## Description
  - The model is basically similar to the model proposed in "Collaborative Filtering for Implicit Feedback Datasets (Hu et al., 2008)." We decompose the user-item rating matrix P (where each row indicates an user, each column indicates an item, and each element indicates a "explicit" rating by user on an item) into the dot product of two latent matrices X and Y. 
  - However, the loss function is different. In the following loss function, p_ui is a rating of user u on an item i, and c_ui is a confidence level (1 if user rated item i, 0 if user did not rate item i or missing). x_u and y_i indicate user latent factors and item latent factors (row and column of X and Y).

## Performance
