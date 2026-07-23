# DH2026 Week 10 Handout

## Title

Harriet Beecher Stowe, "The Minister's Housekeeper"

## 1. Today's Theme

This week we read Stowe's "The Minister's Housekeeper" while introducing contextual text analysis with BERT/SBERT-style models. We will not try to use every app. Today we briefly introduce SBERT Text Lab and examine what sentence-level semantic search does.

## 2. What Matters This Week

### 1. BERT is a model that reads context

In static word-vector models, one word generally corresponds to one vector. In BERT-style models, words or sentences are vectorized after the surrounding context has been read. This means that the same word can be treated differently depending on the sentence in which it appears.

### 2. SBERT is a BERT-style model for comparing sentences

BERT itself is not designed as a fast sentence-search tool. SBERT turns a whole sentence into one vector, making it easier to compare the semantic closeness of sentences. Our class app, SBERT Text Lab, uses this mechanism.

### 3. Semantic search does not replace keyword search

Semantic search can find sentences that seem close in meaning even if they do not share the same words. However, the score is the model's judgment, not literary evidence itself. We use the result as an entry point for returning to the text.

## 3. Today's Questions

1. How are home, labor, religion, and marriage connected in "The Minister's Housekeeper"?
2. Is Huldy's labor represented simply as housework, or as part of communal and religious order?
3. How does Sam Lawson's vernacular narration shape the value judgments of the story?
4. How do passages found by keyword search differ from passages found by semantic search?
5. Can results from SBERT Text Lab create questions that lead us back to close reading?


## 4. What We Will Do Today

1. Share comments
2. Review the structure of the story, Sam Lawson's narration, and Huldy's position
3. Briefly review the move from word vectors to BERT/SBERT
4. If there is time, try the `Search` tab in SBERT Text Lab once
5. Return the result to a specific passage and write a short analysis note
