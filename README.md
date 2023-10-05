# Q_&_A_with_Multiple_PDFs
Q & A with multiple pdf App is a Python application that allows users to upload multiple PDF documents, ask questions about them and use natural language model to generate accurate answers based on the content of those documents.

 1. Imports:
   - It starts by importing various libraries, including Streamlit (`streamlit`), dotenv (`load_dotenv`), PyPDF2 (`PdfReader`), and several components from the Langchain         library. It also imports HTML templates and specific modules like `css`, `bot_template`, and `user_template`.

2. PDF Text Extraction:
   - The `get_pdf_text` function extracts text from the uploaded PDF documents using the PyPDF2 library.

3. Text Chunking:
   - The `get_text_chunks` function splits the extracted text into smaller chunks, presumably for efficient processing. It uses the Langchain library's                
     `CharacterTextSplitter` for this purpose.

4. Vector Store Creation:
   - The `get_vectorstore` function creates a vector store from the text chunks using Langchain's `OpenAIEmbeddings` and `FAISS` vector store. This could be used for 
     semantic search and retrieval.

5. Conversational Chain Setup:
   - The `get_conversation_chain` function sets up a conversational chain using Langchain's `ChatOpenAI` or `HuggingFaceHub` models. This chain appears to handle user 
     questions and generate responses based on the document content.

6. User Interaction:
   - The `handle_userinput` function takes a user's question as input, uses the conversation chain to generate responses, and displays the conversation history between the 
     user and the chatbot in the Streamlit interface.

7. Streamlit Setup:
   - The `main` function sets up the Streamlit application. It configures the page title, icon, and adds a header.

8. User Interface:
   - Users can input questions related to the uploaded PDF documents.
   - They can upload multiple PDFs using the file uploader in the sidebar.
   - When the "Process" button is clicked, the code processes the PDFs, extracts text, creates a vector store, and sets up the conversation chain.

9. Running the App:
   - The app is launched when the script is run as the main module (`if __name__ == '__main__': main()`).
