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
### VetGPTTikToken
1) Libraries and Setup:
Imports: Includes tiktoken for tokenization, torch for deep learning, and numpy for numerical operations.
Device Configuration: Automatically detects GPU or CPU (device = 'cuda' if torch.cuda.is_available() else 'cpu').
Tokenization:
Tiktoken: Initializes a GPT-2 tokenizer (tiktoken.get_encoding("gpt2")) for encoding text into token sequences.
This approach ensures compatibility with GPT-based architectures.
2) Hyperparameters:
Defines key parameters:
block_size: Length of token sequences (40 tokens).
batch_size: Number of sequences in a batch (64).
n_embd: Embedding size (512).
n_head: Attention heads (8).
n_layer: Transformer layers (6).
dropout: Dropout rate for regularization (0.2).
learning_rate, max_iters, and evaluation intervals.
3) Data Preparation:
Loading Data: Reads text from a file (Final_dataset2.txt) and tokenizes it using the GPT-2 tokenizer.
Splitting Data: Divides the dataset into training (90%) and validation (10%) sets.
4) Batching:
The get_batch function prepares batches for training:
Randomly selects starting points in the dataset.
Extracts sequences (x) and their corresponding targets (y).
5) Model Architecture:
Embedding Layer: Maps tokens to dense vectors of size n_embd.
Positional Encoding: Adds positional information to embeddings.
Multi-Head Attention: Implements scaled dot-product attention.
Feed-Forward Network: Applies a two-layer fully connected network with ReLU activation.
Layer Normalization: Stabilizes training by normalizing intermediate outputs.
Stacked Transformer Layers: Combines the above components into a transformer block.
Training:

Uses backpropagation with the Adam optimizer.
Minimizes cross-entropy loss between predicted and actual tokens.
Periodically evaluates the model on validation data.
Text Generation:

Implements a generate function to produce text:
Starts with an initial context.
Iteratively predicts and appends the next token.
