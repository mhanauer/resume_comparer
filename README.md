

# Resume Similarity Checker
This Python application is a tool to compare a resume to a job description and provides insights into how well a resume matches a job description. It calculates a similarity score, identifies missing keywords, and can be very helpful in optimizing a resume according to a particular job role.

# Requirements
Python 3.6 and above
Streamlit
NLTK
Sentence-transformers
Pandas
Numpy

# Functionality
The application uses Natural Language Processing techniques such as tokenization and frequency distribution to analyze the content. The SentenceTransformer model "paraphrase-MiniLM-L6-v2" is used to compare the semantic similarity between the text of the resume and the job description.

The primary functions of the application include:

Reading and pre-processing the text from the uploaded Word documents.
Tokenizing the text, removing stop words, and converting to lower case.
Comparing the semantic similarity between the resume and job description.
Calculating word frequencies.
Identifying missing keywords in the resume that are common in the job description.
The results are presented as a similarity score and a list of missing keywords.

# Limitations
Please note that the application only accepts Word documents (.docx). Also, while the application can help identify missing keywords, the final judgment on resume optimization should be based on a comprehensive understanding of the job requirements, not solely on the keywords.

# Future Work
Acceptance of other file formats like PDFs for resume and job description.
More sophisticated analysis of the document such as named entity recognition or topic modeling.
Integration of a recommendation system to suggest ways to improve the resume.
Contributions
Feel free to submit a pull request if you want to contribute to this project. All contributions are welcome.

# License
This project is licensed under the terms of the Noodle Corp license.
