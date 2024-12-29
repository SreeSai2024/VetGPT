# VetGPT
### gvetgptdatascraper
1) Setup: Import libraries (requests, BeautifulSoup), define the seed URL, and initialize tracking sets and an output file for scraped data.
2) URL Filtering: Use should_scrape_url to validate URLs based on domain, query parameters, and restricted categories or indices.
3) Scraping: Send HTTP GET requests, parse HTML with BeautifulSoup, extract text from <p> tags, and save it to a file.
4) Crawling: Recursively process links by checking if they are valid and unvisited, converting relative URLs to absolute ones.
5) Execution: Start with the seed URL and recursively scrape and save data, finalizing by closing the output file.
### GPT_scratchMyDataLatest
1) Data Preparation:
The script reads a dataset (Final_dataset.txt) into a variable text.
It calculates the dataset's length and generates a vocabulary of unique characters, mapping each character to an integer (stoi) and vice versa (itos).
2) Encoding and Decoding:
Functions are defined to convert text into sequences of integers (encode) and back to text (decode) for efficient numerical processing.
3) Data Splitting:
The dataset is split into training (train_data) and validation (val_data) sets, ensuring a robust training process.
4) Batching:
The get_batch function creates batches of sequences from the dataset, preparing them for input to the model.
5) Model Architecture:
Embedding: Maps token IDs to dense vector representations.
Positional Encoding: Adds positional information to token embeddings.
Multi-Head Attention: Implements attention mechanisms using query, key, and value projections.
Feed-Forward Network: Applies transformations to the input using fully connected layers and ReLU activation.
Layer Normalization: Stabilizes training by normalizing intermediate outputs.
Stacked Layers: Uses multiple layers of the above components in a sequential manner.
6) Training Process:
The model is trained using backpropagation and the Adam optimizer.
Training involves minimizing cross-entropy loss between predictions and actual targets.
Evaluation metrics (train_loss and val_loss) are calculated periodically to monitor performance.
7) Text Generation:
The generate method produces new text based on a given prompt by iteratively predicting the next token and appending it to the sequence.
