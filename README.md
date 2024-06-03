# Context-Based QA from Multiple PDF Files using Gemini💁

## Project Overview

Welcome to the **"GeminiProPDFQA"** project. This application leverages advanced AI and natural language processing techniques to provide a seamless and interactive way to extract information from multiple PDF documents. By utilizing Google's Generative AI and FAISS (Facebook AI Similarity Search), this tool allows users to upload multiple PDF files, process their content, and interactively query the information contained within them.

## Features

### 1. Multi-PDF Support
- **Upload Multiple Files:** Users can upload several PDF documents simultaneously. This is particularly useful for comprehensive document analysis or research that spans multiple sources.
- **Efficient Text Extraction:** The application uses PyPDF2 to extract text from each uploaded PDF, ensuring that all readable content is gathered for analysis.

### 2. Advanced Text Processing
- **Recursive Text Splitting:** The extracted text is divided into manageable chunks using RecursiveCharacterTextSplitter. This ensures that the content is processed efficiently and that large documents do not overwhelm the system.
- **Customizable Chunk Size:** The chunk size and overlap can be adjusted to optimize the balance between context comprehension and processing efficiency.

### 3. Embedding and Vectorization
- **Google Generative AI Embeddings:** The application leverages the `GoogleGenerativeAIEmbeddings` model to convert text chunks into high-dimensional vectors. This transformation is crucial for the similarity search and subsequent question-answering tasks.
- **FAISS Indexing:** FAISS is used to create a local vector store, enabling fast and accurate similarity searches. The index is saved locally, ensuring quick access and retrieval of relevant text chunks.

### 4. Interactive Question Answering
- **Conversational AI Model:** A conversational chain is established using the `ChatGoogleGenerativeAI` model and a custom prompt template. This model is fine-tuned to provide detailed and accurate answers based on the context provided by the PDF documents.
- **Context-Aware Responses:** The AI ensures that answers are derived from the uploaded documents. If the information is not available in the context, it explicitly states so, avoiding any misleading responses.

### 5. Streamlit Integration
- **User-Friendly Interface:** The entire application is built on Streamlit, offering an intuitive and interactive web interface. Users can easily upload files, ask questions, and receive responses in a streamlined manner.
- **Sidebar Menu:** The sidebar provides a convenient way to manage file uploads and initiate the processing of documents. 

## How It Works

1. **Upload PDF Files:** Users start by uploading the PDF documents they wish to analyze.
2. **Process Documents:** Upon clicking the "Submit & Process" button, the application extracts text from the PDFs, splits the text into chunks, and generates vector embeddings.
3. **Ask Questions:** Users can input their queries related to the content of the uploaded PDFs. The AI model searches for relevant information in the vector store and provides a detailed answer based on the context.
4. **Receive Responses:** The responses are displayed in the main interface, providing clear and contextually accurate information based on the user's question.

## Installation and Setup

To run this project locally, follow these steps:

1. **Clone the Repository:**
    ```bash
    git clone https://github.com/ahmed-arifgala/GeminiProPDFQA.git
    cd GeminiProPDFQA
    ```

2. **Create a Virtual Environment:**
    ```bash
    conda create -p venv python==3.10
    conda activate venv/
    ```

3. **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4. **Set Up Environment Variables:**
    Create a `.env` file in the root directory and add your Google API key:
    ```env
    GOOGLE_API_KEY=your_google_api_key_here
    ```

5. **Run the Application:**
    ```bash
    streamlit run app.py
    ```

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes. Ensure that your contributions align with the project goals and follow the existing code style.

