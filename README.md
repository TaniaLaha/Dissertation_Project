# Dissertation_Project
This repository contains all details and codes of my dissertation.

### Problem Statement: 
Build an efficient Knowledge Management System (KMS) for finding out relevant research papers as per given user query.

### Objective: 
The goal of this project is to build an efficient Knowledge Management System capable of querying and retrieval to help fellow researchers with the recommendation of research papers relevant to their topic of interest.

### Solution Steps:

*	This is an NLP case study which leverages techniques like Text Extraction and Text Summarization.
*	First, the Title of any input pdf is getting extracted using packages like ‘PyPDF2’.
*	Pre-process the extracted title and store it within a variable.
*	Extract the name of each section headers from pdf using a customized scraping function which gives the details of font size and font name of each line of that pdf.
*	Determine the font size and font name information of any one section header (in our case we have considered ‘Abstract’ as our base) and use that similar attribute for finding other section headers like Introduction, Methods, Data, Conclusions etc.
*	Once all section headers are found those are formatted as per the headers of original pdf and extracted the text of each sections using the indices of section headers from pdf (For ex. Text of ‘Abstract’ is found using the indices of ‘Abstract’ and ‘Introduction’.
*	To summarize the long texts of each section we applied LSA (Latent Semantic Analysis) to get only top-5 sentences of each section and store it within a list variable.
*	After getting top ranked sentences of each section, measured the similarity score (cosine similarity) of those summaries and title with the user query such that the output score can denote how much the pdf is relevant to user requirements.
*	To compare the performance of our base model (LSA) tried to summarize the extracted texts using pre-trained LLM model (BART) and again checked the similarity score.
*	The evaluation metrics like ROUGE, METEOR were considered for each of the models (LSA and LLM) to check how good the generated summaries are as per some reference human generated summaries.
*	The outcome showed that on an average our base model is quite a good performer than pre-trained models in terms of similarity scores and evaluation metrics.

