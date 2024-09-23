# GraphQLRestBench
This repository contains the GraphQLRestBench dataset, which is a derivative of the [RestBench](https://github.com/Yifan-Song793/RestGPT/tree/main/datasets) dataset created by Yifan Song et al. 

## Data Characteristics

The GraphQLRestBench dataset consists of sequences of pythonic function calls for each sample of a subset of the RestBench dataset along with the GraphQL schema of the original APIs.
Each sample of GraphQLRestBench is a json which contains the following keys:
- **domain**: Either `spotify` or `tmdb`
- **function_specs**: A list of the the function signatures for all functions used in the sample. Each fucntion signature is a dictionary consisting of the name of the function, the description of the function, and the parameters of the function along with their types and descriptions.
- **GraphQL_schema**: The merged GraphQL schema for all the functions in the sample
- **utterance**: The user utterance
- **input**: A convenient string representation of the input to an LLM, consisting of the `function_specs`, `GraphQL_schema` and `utterance`.
- **output**: The expected sequence of pythonic function calls with appropriate arguments.

## Data Organization
The dataset in jsonlines format can be found in the `jsonlines_data` folder.
The data is divided into 3 parts:
- train set (`train.jsonl`)
- validation set (`valid.jsonl`)
- test set (`test.jsonl`)

For convenience, the test set has been split into two parts:
- samples from Spotify data (`test_spotify.jsonl`)
- samples from TMDB data (`test_tmdb.jsonl`)

 
