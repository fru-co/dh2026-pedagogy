# Vector Models for Literary Research

## From Exact Matches to Semantic Relationships

Exact word searches and vector models answer different questions. An N-gram, concordance, or keyword search begins with repeated strings: the same word, spelling, phrase, or quotation. A vector model represents words or passages as lists of numbers and compares their positions in a vector space.

Use exact search when wording and frequency matter. Use vectors when you want to explore related words, similar contexts, or patterns that may not share the same vocabulary. Neither method is inherently better; the research question determines which one is useful.

## 1. Core Concepts

- **Vector:** a list of numbers representing a word or text.
- **Vector space:** the coordinate-like space in which those representations are compared.
- **Cosine similarity:** a measure of how closely two vectors point in the same direction.
- **Training corpus:** the collection of texts from which a model learns its relationships.

A nearby word is not necessarily a dictionary synonym. It is a word that tended to appear in similar contexts in the model's training corpus. Results therefore reflect the corpus, period, genre, preprocessing choices, and model design.

## 2. Static Word-Vector Models

Static models assign one vector to each word. The vector does not change from sentence to sentence, so different senses of a word such as `bank` are combined into one representation.

| Model | Basic idea | Useful feature |
| --- | --- | --- |
| Word2Vec | Learns a word from the words that surround it | Efficiently models local contextual relationships |
| GloVe | Learns from corpus-wide word co-occurrence statistics | Provides accessible pretrained models for exploration |
| fastText | Represents a word partly through character N-grams | Helps with rare words and morphological variation |
| HistWords | Provides decade-specific word vectors | Supports the study of historical semantic change |

The principle behind all four is distributional: words used in similar contexts tend to receive similar representations.

## 3. Word Vector Explorer

**Word Vector Explorer** introduces static word vectors through pretrained models such as `glove-wiki-gigaword-50`. In the app, you can examine:

- **Nearby Words:** words closest to a target word.
- **Word-Pair Similarity:** the relative proximity of two words.
- **Model Comparison:** changes produced by different corpora or dimensions.
- **Vector Arithmetic:** exploratory combinations such as `king + woman - man`.

When reading the output, first look for groups of related words. Then check the model and training corpus. Finally, test the pattern against dictionary definitions, concordance lines, and passages from the literary text.

## 4. HistWords Explorer

**HistWords Explorer** adds time and corpus selection to word-vector analysis. Instead of treating a word as historically stable, it allows you to compare its nearest neighbors or its similarity to another word across decades.

Possible questions include:

- Which words are near `moral` in different decades?
- Does the relationship between `moral` and `religious` change over time?
- Do general English and fiction corpora produce different neighborhoods?

A changing neighborhood may suggest a shift in usage, but it does not demonstrate semantic change by itself. Corpus composition, word frequency, OCR quality, and model alignment may also affect the result.

## 5. A Research Workflow

1. Begin with a word, passage, or interpretive question from the literary text.
2. Use frequency and concordance tools to establish exact usage.
3. Use Word Vector Explorer or HistWords Explorer to identify related words or changing relationships.
4. Record the model, corpus, decade, target word, and comparison settings.
5. Select a small number of patterns worth investigating.
6. Return to dated examples, historical dictionaries, corpus contexts, and the literary text.
7. Distinguish the model's output from your interpretation of that output.

## 6. How to Report a Result

Avoid writing, “The model proves that these words have the same meaning.” A more accurate formulation is:

> In the `_____` model or corpus, `_____` appeared near `_____` during `_____`. This pattern suggests `_____`, but examples from `_____` show that `_____`.

Record enough information for another reader to reproduce the search:

- target word or word pair;
- model and training corpus;
- decade or date range, when applicable;
- number of neighbors or similarity measure;
- relevant output and passages checked afterward;
- limitations or alternative explanations.

## 7. Main Cautions

- Similarity is a model-generated relationship, not a fact about language.
- A high score does not explain why two words or passages are related.
- Static models combine multiple senses into one word vector.
- Models inherit omissions and biases from their training corpora.
- Quantitative patterns are starting points for interpretation, not conclusions.

## References

- Tomas Mikolov et al. 2013. [“Efficient Estimation of Word Representations in Vector Space.”](https://arxiv.org/abs/1301.3781)
- Jeffrey Pennington, Richard Socher, and Christopher Manning. 2014. [“GloVe: Global Vectors for Word Representation.”](https://aclanthology.org/D14-1162/) [GloVe project page.](https://nlp.stanford.edu/projects/glove/)
- William L. Hamilton, Jure Leskovec, and Dan Jurafsky. 2016. [“Diachronic Word Embeddings Reveal Statistical Laws of Semantic Change.”](https://aclanthology.org/P16-1141/) [HistWords project page.](https://nlp.stanford.edu/projects/histwords/)
