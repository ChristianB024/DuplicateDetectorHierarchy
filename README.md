# DuplicateDetectorHierarchy

This is the replication repository to generate the same results as they are presented in the Bachelor Thesis - [Detecting Duplicate Stack Overflow Questions Exploiting the Textual Information, and a Semantic-based Tag Hierarchy](https://repository.tudelft.nl/islandora/object/uuid%3A1f30c556-00b7-4da3-812d-65c902f2d2e2)
## How to use it
1. Clone the repository
2. - We recommend to create a Python environment for running the project. This step can also be omitted if you want to run the project without a specific environment. As an example, you can see the command for creating a `conda` environment.
    ```bash
    conda create --name NAME
    ```
    - For this package we used `Python 3.8.2`.
3. Install the required packages using the command.
    ```bash
    pip install -r requirements.txt
    ```
4. Change the directory to the implementation using the command.
    ```bash
    cd ./implementation
    ```
5. For running the experiments you can use the following command. All the results will be shown as json files in the `./evaluations`. Moreover, for each model we will show the scores using the tags and different hierarchies.
    ```bash
    python cli.py run_experiments --rank_em X --model_type Y
    ```
    - Possible values X for `--rank_em` are `1`, `2`, `3`. 
    - Possible values y for `--model_type` are `GNB`, `DT`, `KNN`, `SVM`, `LR`, `all`. 


## Explanation for running the experiments:
- We use the top 3 rank emebeddings generated by the Doc2Vec model. Fro simplicity, we already add the embeddings files for the top 3 ranking models to use.Thus, `rank_em` parameter takes as values 1, 2 or 3, depeding on the model you want to use.
- For the textul information score, our best ML-based models used in the study for final results can be utilozed by passing the following values in the `model_type`:
    - Gaussian Naive Bayes using the `GNB` value
    - Decision Tree using the `DT` value
    - K-Nearest Neighbor using the `KNN` value
    - Support Vector Machine using the `SVM` value
    - Gaussian Naive Bayes using the `LR` value
    - All the above models using the `all` value