 # Chat-with-single-PDF-book

This is a simple Streamlit app that allows users to chat with a PDF document. You can upload your PDF files, and the application will process them, allowing you to ask questions and get responses based on the content of the document.

## Features
- Upload a PDF file.
- Extract text from the PDF.
- Split text into chunks for efficient querying.
- Use OpenAI or Hugging Face models to answer questions based on the document.
- Save and manage conversation history.
- Responsive and easy-to-use interface powered by Streamlit.

## Steps to Set Up

### 1. Create a Virtual Environment

First, create a virtual environment to isolate the dependencies for this project. Run the following command in your terminal:

#### python -m venv myenv

This will create a `myenv` directory containing the virtual environment.

### 2. Activate the Virtual Environment

- **For Linux/macOS:**
source myenv/bin/activate

- **For Windows:**
.\myenv\Scripts\Activate.ps1



After activating the virtual environment, you should see `(myenv)` in your terminal prompt.

### 3. Install Dependencies

Install the required dependencies for the project by running:

pip install -r requirements.txt


This will install the necessary packages, such as `streamlit`, `langchain`, `PyPDF2`, and others.

### 4. Set Up API Keys

This project uses the **OpenAI** API and **Hugging Face** API for embedding and chat models. You need to create accounts on both platforms and generate API keys.

- **OpenAI API Key (Paid Service):**
  1. Go to [OpenAI](https://beta.openai.com/signup/) and create an account.
  2. Navigate to the [API Keys](https://platform.openai.com/account/api-keys) page.
  3. Create a new API key.
  
  **Note:** OpenAI's API is a paid service, and you will be charged based on the number of tokens used for queries. Make sure to check OpenAI's pricing page for details on costs: [OpenAI Pricing](https://openai.com/pricing).

- **Hugging Face API Key:**
  1. Go to [Hugging Face](https://huggingface.co/) and create an account.
  2. Go to your account settings and generate an API token from the [API Tokens](https://huggingface.co/settings/tokens) section.

### 5. Create a `.env` File

To securely store your API keys and other sensitive information, create a `.env` file in the root directory of the project. Add the following content to the `.env` file:

## OPENAI_API=your_openai_api_key
## HUGGINGFACEHUB_API_TOKEN=your_huggingface_api_key


Make sure to replace `your_openai_api_key` and `your_huggingface_api_key` with the actual keys you obtained in step 4.

### 6. Run the Application

Once everything is set up, you can run the Streamlit app using the following command:

## streamlit run app.py

This will start the app, and you can access it via the browser at `http://localhost:8501`. From there, you can upload PDF files and ask questions based on the content of those files.

### 7. How the Application Works

- Upload a PDF file using the sidebar.
- The application will process the file, extract text from the PDF, and split it into manageable chunks.
- After processing the PDF, you can ask questions related to the content of the document.
- The application will respond using OpenAI's GPT-3 model or a Hugging Face model, based on the API keys provided.
- All interactions (questions and answers) are stored in the session history for a conversational experience.

### Notes

- Make sure that your `.env` file is not accidentally uploaded to a public repository (e.g., by including it in `.gitignore`).
- You can switch between OpenAI and Hugging Face by commenting/uncommenting the respective code blocks in the `get_vectorstore()` and `get_conversation_chain()` functions in the `app.py` file.
- You can modify the chunk size and other parameters in the `get_text_chunks()` function depending on the size of your PDFs and the nature of the content.

## File Structure

.
├── app.py # Main Streamlit app
├── requirements.txt # Python dependencies
├── .env # API keys and sensitive information
├── htmlTemplates.py # Templates for rendering the chat interface
└── README.md # This file



## Troubleshooting

- **Missing Libraries/Modules**: If you encounter issues with missing libraries, try running:

pip install -r requirements.txt

This should install all the necessary libraries.

- **API Key Issues**: If you get errors related to the API key, make sure that you've added the keys correctly to the `.env` file and that the keys are valid.
 