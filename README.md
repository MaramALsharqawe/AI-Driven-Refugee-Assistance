### AI-Driven Refugee Assistance

This project leverages AI to assist refugees by converting their voice recordings into text, categorizing their needs, and providing faster assistance to the UNHCR. The system supports both Arabic and English, ensuring accessibility for refugees from various regions. The AI model predicts the issues or needs expressed in voice recordings and classifies them into relevant categories. This helps in delivering the refugees' voices directly to the appropriate UNHCR units, ensuring quicker resolutions to their challenges.

#### Data Collection and Cleaning

- **Data Collection**: The project used a combination of over 5,000 social media comments and data collected directly from refugees. Additionally, voice recordings from refugees were converted into text.
- **Data Cleaning**:
  - **Preprocessing**: The text data underwent extensive cleaning, including the removal of URLs, emojis, and specific phrases. Additionally, Arabic text was normalized by standardizing different forms of characters (e.g., Alef Maksura, Teh Marbuta).
  - **Stopword Removal**: Arabic stopwords, including custom and common phrases, were removed from the dataset. This ensures that the AI model focuses on the relevant words in the text.
  - **Phrase Removal**: Phrases like religious expressions were also removed using regular expressions to avoid unnecessary bias in the classification.
  - **Normalization**: The Arabic text was normalized to remove redundant characters and ensure consistent representation across the dataset.
  - **Duplicate Removal**: Duplicate records were eliminated, and any empty or irrelevant comments were removed.
  
- **Final Dataset**: After cleaning, the dataset was reduced to 3,000 records, and each record was manually labeled into specific categories.

#### Dataset Categories

Here are the main categories from the cleaned and labeled dataset:

- General Inquiries
- Resettlement Status Inquiries
- Resettlement and Third-Country Solutions
- Health Services: Primary Health Care
- Cash Assistance
- Education Services
- Case Management: File Status Inquiries
- Cash Assistance: WFP Assistance
- Protection: Legal and Documentation Issues
- Employment Support (Authorization & Opportunities)
- Registration and Documentation
- Registration and Documentation: Renewal of Documents
- Communication with UNHCR
- Repatriation
- Cash Assistance, Resettlement
- Registration: Appointment Related
- Cash Assistance: Winterization Assistance
- Health Services: Emergency Medical Services
- Cash Assistance: Shelter and Housing
- Cash Assistance, Health Services
- Protection: UNHCR Staff Conduct
- Cash Assistance, Education
- Cash Assistance: Cash Withdrawal Issue/Iris Technical Errors
- Protection: Eviction Threats and Housing Issues
- Protection: Family Protection
- Protection: Sexual and Gender-Based Violence (SGBV)

#### Model Training

1. **Preprocessing**: The cleaned text data was preprocessed by:
   - Removing unwanted characters (such as emojis, stopwords, and special phrases).
   - Normalizing Arabic text and eliminating unnecessary duplicates.
   
2. **Tokenization**: The text data was tokenized using **AraBERT**, a pre-trained Arabic BERT model. The tokenizer prepared the data for input into the BERT model.

3. **Model Setup**: 
   - The **AraBERT** model was fine-tuned on the cleaned and preprocessed dataset.
   - The model was set up to predict 22 categories corresponding to refugee needs.

4. **Training**: 
   - The dataset was split into a training set (80%) and a testing set (20%).
   - The model was trained for 10 epochs with early stopping based on validation loss.
   - Class weights were computed to address class imbalance, ensuring the model handled underrepresented categories effectively.

5. **Evaluation**: 
   - The model achieved an accuracy of **76%** on the evaluation set, showing promising performance in classifying refugee needs.

6. **Saving the Model**: 
   - The trained model, tokenizer, and label encoder were saved to a pickle file for future use.

#### Key Features:
- **Voice-to-Text**: Converts refugee voice recordings into text for processing.
- **Multilingual Support**: Supports both Arabic and English for a wider refugee audience.
- **Fast Categorization**: Automatically categorizes needs, ensuring faster assistance.
- **Class Imbalance Handling**: Utilizes class weights to improve model performance on underrepresented categories.
- **AI for Real-Time Assistance**: Directly routes categorized needs to the relevant UNHCR units for swift action.

#### User Interface (UI) with Streamlit

To enhance accessibility, I created a simple **Streamlit-based user interface** to showcase how the model works. The UI allows users to:
1. Record voice messages (in both Arabic and English).
2. The voice is converted to text and categorized using the AI model.
3. View the predicted category of the refugee's need.



#### Demo Video

Watch the video demo of the system in action:







https://github.com/user-attachments/assets/2de81196-f75b-4f3a-b0d3-795ba51c33aa



---

This AI-driven approach aims to bridge the communication gap between refugees and humanitarian organizations, ensuring their needs are heard and addressed efficiently.


