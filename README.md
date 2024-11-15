# Collaboration across STEM and Liberal Arts:AI design concept and technology that supports digital humanities[2]

## **Introduction -- Building a RAG for China News Using ChatGPT API**
This project demonstrates how to build a Retrieval-Augmented Generation (RAG) model using the **China News** dataset from Kaggle and the OpenAI ChatGPT API. The RAG model integrates retrieval capabilities with a generative AI model to provide context-aware and accurate responses based on a large dataset of Chinese news articles.

## **Project Overview**

- **Objective**: To create a system that retrieves relevant information from a dataset of Chinese news and generates contextually relevant responses using ChatGPT.
- **Dataset**: [China News Dataset from Kaggle](https://www.kaggle.com/) (uploaded as `chinese_news.csv`).
- **Technologies Used**:
  - Python
  - ChatGPT API (OpenAI)
  - FAISS (Facebook AI Similarity Search) for retrieval
  - pandas, scikit-learn, and other data processing libraries


## How to Get the ChatGPT API Key

### 1. Create an OpenAI Account
Go to the [OpenAI website](https://beta.openai.com/signup/) and sign up for an account. If you already have one, log in.

### 2. Generate an API Key
1. After logging in, go to your **API Keys** section in the dashboard.
2. Click **Create new secret key** to generate a new API key.
3. Copy the key and save it somewhere safe. You won’t be able to see it again.



## **How to get the dataset**
Kaggle is the famous platform which is offering machine learning compititions and opensource datasets
Note that if you want to use Kaggle, you must have an account but one can easily log in using one's Google or Fakebook or Yahoo account
We need to install Kaggle API (Application Programming Interface) first:

```
! pip install kaggle
```
On the Kaggle home page in your browser, click on the icon in the upper right corner and select "Account" from the menu bar to go to the account management page. In the "API" section, select "Create New API Token" to download the kaggle.json file to your computer. **After uploading that json file to colab by clicking on the folder symbol in the leftmost tab**, run the following cell.

```
import kaggle
from kaggle.api.kaggle_api_extended import KaggleApi
api = KaggleApi()
api.authenticate()
api.model_list_cli()
```
we can download datasets by using following command
```
! kaggle datasets download <name-of-dataset>
```


## **Dataset Details**

[Download the CSV file](DH\extracted_data\chinese_news.csv)

The dataset contains Chinese news articles and their metadata. Key columns include:

1. **Date**: The date of the news article.
2. **tag**: The type of the news article (chinese).
3. **Headline**: The Headline of the news (chinese).
4. **Content**: The main content of the news article (chinese).

## **Architecture**

1. **Data Preprocessing**:
   - Clean and tokenize the dataset.
   - Vectorize the content using sentence embeddings (e.g., SBERT or OpenAI embeddings).

2. **Indexing**:
   - Use FAISS to index the vectorized content for efficient retrieval.

3. **Retrieval**:
   - Given a user query, retrieve the top-k relevant articles using FAISS.

4. **Generation**:
   - Use the ChatGPT API to generate responses based on the retrieved content.

5. **Integration**:
   - Combine the retrieved content and ChatGPT's generative capabilities to produce a coherent, context-aware response.


## **Usage Example**

1. Start the app and enter a query (e.g., "中国的经济政策最近有什么变化？").
2. The system retrieves relevant news articles and uses ChatGPT to generate a comprehensive response.

## **Authors and Acknowledgment**

Project Title was created by **[Your Name](https://github.com/username)**.

Additional contributors include:

- **[Contributor Name](https://github.com/contributor-name)**
- **[Another Contributor](https://github.com/another-contributor)**

Thank you to all the contributors for their hard work and dedication to the project.


## **log**
2024/10/18
1. Create a dh repository in your GitHub account. **ok**
2. Create a readme file in your repository. You can refer to the following article for the content of the readme file. **ok**
3. Prepare your readme text. **ok**
4. Share your repository. **ok**
5. What is your domain or theme of your RAG system? **renewable energy (wind power, solar power...)**
6. Which library or framework are you going to use? **ChatGPT, kaggle database**
7. Did you set an API KEY as a preparation? **yes**
8. Discuss the design and planning of the system. **kaggle APIを利用して、データを取得して、GPTにインプットして、可視化したり、解析したりするつもり**
9.  What kind of data format are you going to use? **CSV**
10. What is the problem you want to solve?
11. Discuss the design and planning of the system including the above points.
12. As a summary, you will briefly present the above points.

## **Contact**

If you have any questions or comments about Project, please contact **[Shuai Wang](wang.s.e232@m.isct.ac.jp)**.

## **Conclusion**

This project successfully demonstrates the potential of a Retrieval-Augmented Generation (RAG) model to enhance language understanding and response quality by combining the strengths of information retrieval and generative AI. By leveraging the China News dataset, we were able to create a system that retrieves relevant news articles based on user queries and generates coherent, context-aware responses using the ChatGPT API.

The RAG approach enhances the reliability and accuracy of generative responses, particularly in domain-specific applications like news, where accurate and contextual information is crucial. Through indexing with FAISS and generating responses with ChatGPT, this project provides a scalable and adaptable framework that can be further customized and extended to other datasets and languages.

--- 
