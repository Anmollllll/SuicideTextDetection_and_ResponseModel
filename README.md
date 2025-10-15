# Suicide Risk Detection & Support Chatbot
*A compassionate AI companion for mental health crisis support.*

---

##  Overview
This project addresses the critical need for immediate, empathetic support for individuals experiencing suicidal thoughts or mental health crises.  
It combines a fine-tuned BERT model for detecting suicidal ideation in text with a Google Gemini-powered chatbot designed to provide warm, non-judgmental, and stabilizing responses.  
The goal is to offer a safe, accessible initial point of contact for those in distress, guiding them towards professional help and encouraging safety.

---

## Features

###  Suicide Ideation Detection Model
Leverages a fine-tuned BERT model to analyze user-inputted text (e.g., social media posts, personal notes) and predict the likelihood of suicidal content.

###  Empathetic Chatbot
If suicidal ideation is detected, an AI chatbot (powered by Google's Gemini-2.5-flash) immediately engages with the user, offering:

- **Soothe and Stabilize:** Gentle, calming language and grounding techniques.  
- **Trust Building:** Non-judgmental, warm, and accepting communication.  
- **Crisis Understanding:** Open-ended questions to gently explore the situation.  
- **Coping Collaboration:** Help in identifying strengths and actionable steps.  
- **Safety Encouragement:** Gentle nudges towards safety and professional support, including direct links to global crisis hotlines.

###  Interactive Streamlit UI
A user-friendly web interface for text analysis, chatbot interaction, and chat history management.

###  Chat History
All interactions with the chatbot are saved, allowing users to revisit past conversations or continue them later.

###  Robust Text Preprocessing
Includes thorough cleaning steps to handle noisy, real-world text data, ensuring better model performance.

---

##  Model Details & Performance
The core of the suicide ideation detection is a BERT-based sequence classification model.

###  Dataset
The model was trained on the **Suicidal Ideation Detection Reddit Dataset** from [data.mendeley.com](https://data.mendeley.com).  
This dataset consists of Reddit posts labeled for suicidal content, providing a rich source for training our detection model.

###  Data Preprocessing & Cleaning
Before training, the raw text data underwent several crucial preprocessing steps to improve model robustness:
- Removal of HTML tags, URLs, emails, phone numbers.  
- Normalization of unicode characters and excessive punctuation.  
- Conversion to lowercase and removal of excessive whitespace.  
- Handling of repeated words and control characters.  
- Analysis using **TextQualityAnalyzer** to ensure clean and usable data.

###  Training & Evaluation
The BERT model (`bert-base-uncased`) was fine-tuned for 3 epochs on the cleaned dataset.  
The training was performed with a batch size of 8, learning rate of 2e-5, and weight decay of 0.01.

| Epoch | Accuracy | Precision | Recall | F1-Score |
|:------:|:---------:|:----------:|:--------:|:---------:|
| 1 | 0.9519 | 0.9339 | 0.9676 | 0.9505 |
| 2 | 0.9575 | 0.9592 | 0.9514 | 0.9553 |
| 3 | 0.9596 | 0.9574 | 0.9581 | 0.9577 |

The model achieved its best performance in **Epoch 3**, with an impressive **F1-Score of 0.9577**.  
This demonstrates a strong capability in accurately identifying suicidal ideation while maintaining a balance between precision and recall.

---

##  License
This project is licensed under the **MIT License** - see the [LICENSE](./LICENSE) file for details.

---

##  Important Disclaimer
This chatbot is designed to provide immediate emotional support and guidance toward resources.  
It is **NOT a substitute** for professional mental health care, diagnosis, or treatment.  
The model's predictions are based on patterns learned from data and may not always be accurate.  
Always prioritize human judgment and professional help in real-life crisis situations.

##  Acknowledgements
Special thanks to:
- **Reddit dataset contributors** for enabling open research.  
- **Google Gemini API** for its advanced conversational capabilities.  
- The global mental health community advocating for accessible and empathetic care.
- https://www.frontiersin.org/journals/psychiatry/articles/10.3389/fpsyt.2025.1634714/full.

---
