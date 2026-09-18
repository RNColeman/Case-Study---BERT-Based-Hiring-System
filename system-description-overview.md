System Overview

Purpose
Automate resume screening to reduce manual workload and improve consistency. 

Architecture Summary 
Transformer encoder architecture
12 layers (BERT-based)
768 hidden size
12 attention leads 
~ 110M parameters 

Inputs
*Candidate Resumes 
*Job Descriptions
Optional data- years of experience, skills, technical requirements 

Output
*Relevance scores 
*Ranked candidate lists
*Shortlist recommendations

Model Type
Tokenization
BERT encoder (Bidirectional Encoder Representations from Transformers) fine-tuned for text classification.
Classification head


Explanation of model - the model takes the text, understands its meaning using deep contextual embeddings, and outputs as labels (e.g. "qualified" or "not qualified"). It does this by reading text bidirectionally, building a deep semantic representation, and then mapping that representation to classification decision. 

BERT is a Transformer-based language model that learns the meaning of text by reading it in both directions at once (left>right, right<left). When you fine tune BERT for text classification, you train it to map text > label.

The model reads "all at once" using attention to understand how each word relates to every other word.

The model converts text into embeddings. Every word becomes a "vector" - numerical representation capturing meaning, tone, and relationships.
The embeddings encode: 
syntax
Semantics
Word relationships
Sentence meaning

The model produces a special "CLS" embedding. For classification tasks, BERT uses the CLS token - a special token added to the beginning of the text. BERT outputs a single vector for this token that represents the entire input text. This vector is what the classifier uses to make decisions. 

Fine-tuning adds a small neural network on top of BERT. this layer learns to map BERT's understanding of the text to a specific category. It teaches BERT the task.
Examples:
Resume > Qualified or Not Qualified 

BERT outputs a probability distribution 
For each label, BERT produces a probability. 
LABEL            PROBABILITY
Qualified        0.82
Not Qualified    0.18
* The highest probability becomes the prediction



