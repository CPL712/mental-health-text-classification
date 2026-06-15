# Data Preprocessing

The following preprocessing steps were applied before model training.

## Common

- Removed missing values
- Converted text to lowercase
- Removed English stopwords
- Encoded labels using LabelEncoder
- Stratified train/validation/test split

## BiLSTM

- Keras Tokenizer
- Vocabulary size: 10,000
- Sequence padding (100 tokens)

## DistilBERT

- Hugging Face AutoTokenizer
- Dynamic tokenization
- Maximum sequence length: 512
