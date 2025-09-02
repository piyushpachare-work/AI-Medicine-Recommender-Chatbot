AI Healthcare Medicine Recommender
A user-friendly desktop application that leverages Natural Language Processing (NLP) to recommend over-the-counter medicines based on user-provided symptoms. This tool is designed to be a simple, proof-of-concept healthcare assistant.

Disclaimer: This application is for informational purposes only and is not a substitute for professional medical advice, diagnosis, or treatment. Always seek the advice of your physician or other qualified health provider with any questions you may have regarding a medical condition.

📋 Table of Contents
Key Features

How It Works

Technology Stack

Setup & Installation

How to Use

Dataset

Future Improvements

✨ Key Features
Dual Symptom Input: Users can either type their symptoms in natural language (e.g., "I have a cough and a high fever") or select them from a comprehensive checklist.

NLP-Powered Symptom Extraction: Utilizes the spaCy library to parse free-text input and accurately identify relevant medical symptoms.

Simple & Intuitive GUI: Built with Python's native Tkinter library, making it lightweight and easy to use without complex dependencies.

Customizable Medical Dataset: The knowledge base is a simple CSV file (mediiii.csv), which can be easily expanded with more symptoms, conditions, and medicines.

⚙️ How It Works
The application operates through a straightforward workflow:

User Input: The user chooses their preferred method to input symptoms on the home screen.

Symptom Processing:

For Free Text: The input string is processed by the spaCy NLP model. The model tokenizes the text and identifies words that match the symptoms listed in the mediiii.csv dataset.

For Checkbox Selection: The application directly uses the list of selected symptoms.

Data Matching: The extracted symptoms are used to query the Pandas DataFrame (loaded from mediiii.csv). The application filters the dataset to find rows where the symptom column matches the user's symptoms.

Recommendation Display: The medicine and dosage from the first matching row in the dataset are retrieved and displayed to the user in a pop-up message box.

Note: The current logic recommends the first medicine it finds that matches one of the user's symptoms. It does not yet cross-reference multiple symptoms or utilize the age_group and weight_group columns for more advanced filtering.

🛠️ Technology Stack
Language: Python 3

GUI: Tkinter

NLP: spaCy (en_core_web_sm model)

Data Manipulation: Pandas

🚀 Setup & Installation
Follow these steps to get the application running on your local machine.

Prerequisites
Python 3.6 or newer

pip (Python package installer)

Installation Steps
Clone the repository:

git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
cd your-repo-name

Install the required Python libraries:

pip install pandas spacy

Download the spaCy NLP model:
This model is necessary for the application to understand and process text.

python -m spacy download en_core_web_sm

Ensure the dataset is present:
Make sure the mediiii.csv file is in the same root directory as maincode.py.

📖 How to Use
Run the application:
Open your terminal or command prompt, navigate to the project directory, and run the following command:

python maincode.py

Homepage:
You will be greeted with a homepage offering two choices:

Enter Symptoms: Allows you to type your symptoms in a text box.

Select Symptoms: Presents a list of all available symptoms with checkboxes.

Get Recommendation:

After entering or selecting your symptoms, click the Submit or Show Recommendation button.

A message box will appear with the recommended medicine and dosage.

📊 Dataset
The mediiii.csv file is the core knowledge base of this application. It should contain the following columns:

symptom: The medical symptom (e.g., cough, fever).

age_group: The target age for the medicine (e.g., adult, child).

weight_group: The target weight group (e.g., normal, overweight).

medicine: The name of the recommended medicine.

dosage: The recommended dosage for the medicine (e.g., 500mg, 10ml).

You can easily extend the application's capabilities by adding new rows to this CSV file.

🔮 Future Improvements
This project has a solid foundation, but there are many ways it could be enhanced:

Advanced Recommendation Logic: Update the algorithm to use the age_group and weight_group columns for more precise recommendations.

Multi-Symptom Handling: Implement a scoring system to recommend medicines that treat multiple user symptoms simultaneously.

UI/UX Enhancements: Improve the visual design and user experience of the application.

Error Handling: Add more robust error handling for cases where no symptoms are recognized or no medicine is found.

Database Integration: Migrate the dataset from a CSV file to a more scalable database solution like SQLite.
