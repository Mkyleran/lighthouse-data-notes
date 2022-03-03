# W8D4 notes

## Today

NLP II

## Lecture

### Topics

- Introduction to NLP modeling
- Sentiment analysis
  - Supervised learning sentiment analysis
- Topic modeling
  - LDA (Latent-Dirichlet-Allocation)

## Core
To download data for the Sentiment Analysis walkthrough:

Follow the instructions in the [documentation](https://github.com/Kaggle/kaggle-api) to set up the Kaggle API.

When saving the credentials file to `~/.kaggle/kaggle.json` you first need to make the directory
`mkdir ~/.kaggle`

Accept the rules of the UMICH SI650 - Sentiment Classification competition [here](https://www.kaggle.com/c/si650winter11/rules). Files will not download without accepting the rules.

`kaggle competitions download -p ~/path/to/save/files -c si650winter11` omitting the -p flag save the files to the present working directory.
