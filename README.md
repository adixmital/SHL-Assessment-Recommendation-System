Approach of GenAI Assessment Recommendation system
Objective: To build an intelligent recommendation system.

Libraries Used:

•	pandas – for data handling

•	openpyxl – to read Excel files

•	sentence-transformers – for semantic text embeddings

•	torch (PyTorch) – for tensor operations and similarity calculation

Step-by-Step Approach:
1. Dataset Creation:
 - Manually built the dataset by extracting relevant information from SHL's product catalog. -Selected fields essential for modelling: 'Relevant Job Roles', 'Knowledge, Skills, Abilities', 'Test', 'Test Type', 'Time(min)', ‘Remote Testing’, ‘Adaptive/IRT Support’.
2. Data Cleaning:
 - Text from 'Relevant Job Roles' and 'Knowledge, Skills, Abilities' was converted to lowercase. - Removed special characters (newlines, bullet points, extra spaces). - Merged these two fields into a new column called 'Combined' for semantic processing.
3. Text Vectorization: - Used the pre-trained SentenceTransformer model 'all-mpnet-base-v2' to convert textual data into embeddings. This allowed semantic comparison using vector similarity instead of keyword matching.
4. Query Embedding: - User queries were cleaned in the same manner and combined. Encoded using the same transformer model to generate a query vector.
5. Similarity Computation: Calculated cosine similarity between the query embedding and all row embeddings using PyTorch. Ranked the dataset entries based on similarity scores
6. Output: - Returned most similar tests along with their Test Type, Remote Testing status, Time (in minutes).
7. Deployment: The application was deployed using Render for public access and easy scalability.

