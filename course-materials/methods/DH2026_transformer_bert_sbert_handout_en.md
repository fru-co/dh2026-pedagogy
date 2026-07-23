# Transformers, BERT, SBERT, and Historical BERT

## From Static Words to Contextual Passages

Static word-vector models such as Word2Vec and GloVe assign one vector to each word. This is useful for comparing vocabulary, but it combines different senses into a single representation. The word `bank`, for example, receives the same vector whether it refers to money or a river.

Contextual models build a representation after reading the surrounding passage. The same word can therefore receive different vectors in different sentences. This shift—from a fixed word representation to a context-dependent one—is central to BERT and later language models.

## 1. The Transformer

The **Transformer** is a neural-network architecture introduced in 2017. Its central mechanism, **attention**, estimates how strongly each token should relate to other tokens in its context.

In “The animal did not cross the street because it was tired,” interpreting `it` requires a relationship with `animal`, not simply the closest noun. Attention helps the model represent such contextual relationships. It also allows many tokens to be processed in parallel during training.

Transformers provide the underlying architecture for BERT, GPT, and many contemporary large language models.

## 2. BERT

**BERT** stands for *Bidirectional Encoder Representations from Transformers*. It learns from both the left and right context of a token. During pretraining, BERT repeatedly predicts words hidden by a `[MASK]` token:

> The `[MASK]` sat on the mat.

Recovering a likely word requires patterns of grammar and meaning learned from the training corpus. BERT can consequently give `bank` different contextual representations in “river bank” and “bank loan.”

BERT is a model architecture, not the name of one classroom app. Different training corpora and tasks produce variants designed for different purposes.

## 3. Historical BERT

A **Historical BERT** model is trained on historical texts. This matters because a model trained primarily on contemporary language may interpret nineteenth-century vocabulary, spelling, genre, religion, politics, and morality through modern patterns.

Historical models do not remove the problem of bias. Their outputs still depend on the period, region, genre, OCR quality, and selection of their training data. The model is not a neutral reader; its corpus shapes what it can recognize.

**Historical BERT Explorer** supports two kinds of classroom comparison:

- comparing masked-word predictions from modern and historical models;
- comparing contextual vectors for a target word across a collection of passages.

For example, students can collect passages containing `enthusiasm`, extract a contextual representation for that word in each passage, and read examples that the model places near or far from one another. The app organizes examples already gathered from texts, dictionaries, or corpora; it does not replace the work of finding and reading those examples.

Models discussed in class include Living with Machines BERT (1760–1900), MacBERTh (1450–1950), and modern BERT as a point of comparison.

## 4. SBERT

Standard BERT was not designed for efficient semantic searching across thousands of sentences. **Sentence-BERT (SBERT)** adapts BERT so that each sentence can be encoded independently as one vector. Once the vectors are stored, sentence similarity can be compared efficiently with cosine similarity.

**SBERT Text Lab** uses this method to search the eleven course readings, divided into approximately 2,600 sentences. The course texts are vectorized in advance; the reader's query is vectorized when it is submitted.

The default model, `all-MiniLM-L6-v2`, is a compact general-purpose sentence-transformer model that produces 384-dimensional vectors. It is useful for teaching and rapid comparison, but it was not designed specifically for nineteenth-century American literature. Archaic spelling, dialect, and historically specific meanings may therefore be represented unevenly.

## 5. What the Two Classroom Tools Compare

| Tool | Unit represented | Main classroom question |
| --- | --- | --- |
| Historical BERT Explorer | A target word in a particular context | How does a word's contextual use vary across passages or models? |
| SBERT Text Lab | A sentence or short passage | Which passages are semantically similar to a query? |

Historical BERT focuses on a word within its context. SBERT focuses on sentence-level similarity. The two outputs are related but not interchangeable.

## 6. The Larger Sequence

```text
exact strings
  N-grams, frequency, concordance
        ↓
static word vectors
  Word2Vec, GloVe, HistWords
        ↓
Transformer
  attention across a context
        ↓
contextual word representations
  BERT and Historical BERT
        ↓
sentence representations
  SBERT and semantic search
```

This sequence does not mean that newer methods replace older ones. Exact search, static vectors, contextual word models, and sentence embeddings answer different questions.

## 7. A Research Workflow

1. Begin with a passage or question from the literary text.
2. Decide whether you need exact wording, related vocabulary, a word in context, or similar passages.
3. Record the tool, model, corpus, query, and settings.
4. Treat rankings, clusters, and similarity scores as leads rather than evidence by themselves.
5. Read the retrieved passages closely and compare them with dictionary or corpus evidence.
6. Explain what the model may be responding to and what it may be missing.

## 8. Main Cautions

- A similarity score is the model's judgment, not a linguistic or literary fact.
- Different models produce different vector spaces, rankings, and scores.
- Masked-word predictions and clusters reveal model tendencies, not authorial intention.
- Models inherit gaps and biases from their training data.
- Semantic similarity and critical significance are not the same thing.
- The final interpretation must return to the text and its historical context.

## References

- Ashish Vaswani et al. 2017. [“Attention Is All You Need.”](https://arxiv.org/abs/1706.03762)
- Jacob Devlin et al. 2019. [“BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding.”](https://aclanthology.org/N19-1423/)
- Nils Reimers and Iryna Gurevych. 2019. [“Sentence-BERT: Sentence Embeddings Using Siamese BERT-Networks.”](https://aclanthology.org/D19-1410/)
- Kasra Hosseini et al. 2021. [“Neural Language Models for Nineteenth-Century English.”](https://openhumanitiesdata.metajnl.com/articles/10.5334/johd.48)
- Enrique Manjavacas Arevalo and Lauren Fonteyn. 2021. [“MacBERTh: Development and Evaluation of a Historically Pre-trained Language Model for English (1450–1950).”](https://aclanthology.org/2021.nlp4dh-1.4/)
- Sentence Transformers. [`all-MiniLM-L6-v2` model card](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2).
