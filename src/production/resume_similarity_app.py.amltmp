import streamlit as st
import os
from analysis.fun_text_analyzer import text_analyzer
import pandas as pd
import numpy as np
from nltk.tokenize import word_tokenize
from sentence_transformers import SentenceTransformer
from nltk.corpus import stopwords
from nltk.probability import FreqDist
import nltk

nltk.download("punkt")
nltk.download("stopwords")
model = SentenceTransformer("paraphrase-MiniLM-L6-v2")

def main():
    st.set_page_config(page_title="Resume Similarity Checker", layout="centered")
    st.title("Resume Similarity Checker")
    
    st.subheader("Upload your resume and job description (Word documents only)")
    resume_file = st.file_uploader("Upload your resume", type=["docx"])
    job_description_file = st.file_uploader("Upload the job description", type=["docx"])

    if resume_file and job_description_file:
        analyzer = text_analyzer()
        cv_text = analyzer.read_word_file(resume_file)
        job_description_text = analyzer.read_word_file(job_description_file)

        cv_text_tokens = analyzer.preprocess_text(cv_text)
        job_description_text_tokens = analyzer.preprocess_text(job_description_text)
        similarity_score = analyzer.compare_texts(cv_text_tokens, job_description_text_tokens)
        cv_word_freq = analyzer.calculate_word_frequency(cv_text_tokens)
        job_description_word_freq = analyzer.calculate_word_frequency(job_description_text_tokens)

        top_n = 10
        top_job_description_words = [word for word, freq in job_description_word_freq.most_common(top_n)]

        missing_keywords = []
        for word in top_job_description_words:
            if word not in cv_word_freq:
                missing_keywords.append(word)

        st.write(f"Similarity Score: {float(similarity_score):.2f}")
        st.write(f"Missing Keywords: {', '.join(missing_keywords)}")

if __name__ == "__main__":
    main()
