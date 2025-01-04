Cell 1:
Mounting Google Drive so we can access files and store new ones

Cell 2/3:
cleaning the files from finqa. only keeping "pre_text" , "post_text","table","filename" attributes

Cell 4:
installing llama-index

Cell 5:
converting the files into Document objects. these Document objects get stored in documents list

Cell 6:
not important. just seeing if the documents list is loaded correctly with data

Cell 7:
Installing Qdrant Vector storage as well as huggingface embeddings. watch some youtube videos about vector database and text embedding

Cell 8:
installing libraries for embedding and vector store

Cell 9:
not important. just checking if the documents list is still good

Cell 10:
making a client for the Qdrant vector store. read about Qdrant

Cell 11:
Initialising the embedding model. we are using sentence-transformers/all-MiniLM-L6-v2 

Cell 12:
Indexing. Adding the Document objects in documents list to the vector store. this is the backbone of RAG and takes the longest to compute

Cell 13:
importing retriever for vector store

Cell 14:
installing groq. groq is a platform that hosts llms which we can use for free. we tried huggingface because it had a model that was finetuned for our usecase but we could not impliment it in time.

Cell 15:
we initialise the llm we are using. in this case its llama3-8b-8192. this model is hosted on groq and to use it we need to use the API. then we initialise the retriever which will take the best 5 matching documents. these will match the question we've asked. the run() function takes each Document (in this context it is known as a node) and concatenates the text and the metadata. the metadata is the table in the files. this text and metadata becomes context for the llm. using the prompt template it takes the question which is passed as an argument and the context which we've just created and gives the answer that we've asked for.

Cell 16:
prompt. this is used to give the llm a template to answer the questions

Cell 17:
running the retiever. it retieves the best 5 matching Document objects in the vector store. it returns the context and the final answer.

Cell 18:
remounting google drive. not neccesary but allows us to run either the finqa or the pdf part without running the other.

Cell 19:
importing pdfplumber and converting each sentance in the pdf into a document. the Document has data of the text of the sentence and metadata of the sentences page number and sentence number

Cell 20:
checking if the documents loaded correctly

Cell 21:
langchain text splitter. this doesnt do anything i forgot to remove it.

Cell 22:
new client for Qdrant vector store

Cell 23:
embedding and indexing

Cell 24:
again using llama 3 hosted on groq to read the documents fetched by retiever and give answer.

Cell 25:
prompt

Cell 26:
running the retiever function and getting output
