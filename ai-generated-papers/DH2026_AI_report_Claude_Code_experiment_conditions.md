# DH2026 AI Final Paper Experiment: Conditions Memo

This memo records the conditions under which two AI-generated final papers were produced with Claude Code. The experiment asks what changes when an AI moves from describing plausible tool results to executing the underlying analyses.

## 1. Date

Both versions were produced on July 10, 2026, during the same working session.

## 2. AI System

- Model recorded for the experiment: **Claude Fable 5** (`claude-fable-5`, Anthropic)
- Reasoning effort: **medium**
- Environment: **Claude Code**, with file access and Python execution available
- Recorded knowledge cutoff: January 2026

The instructor supplied the prompts but did not contribute to the close reading, interpretation, or prose of either paper.

## 3. Shared Assignment and Materials

Both versions were asked to follow the [Final Paper Assignment](../course-materials/assignments/DH2026_final_paper_prompt_en.html) and could consult the course syllabus, weekly handouts, and research-methods handouts.

Both compare:

- Washington Irving, “The Devil and Tom Walker” (1824)
- Nathaniel Hawthorne, “Ethan Brand” (1850)

The two papers share the same comparative question about the externalization and internalization of sin so that their analytical claims can be compared directly.

## 4. Version 1: No Tools Executed

[Version 1](DH2026_AI_report_Claude_Code_v1_no_tools_simulated_EN.html) was generated from the course materials without access to the course text files or analytical tools. The AI relied on its trained knowledge of the public-domain works.

No frequency analysis, KWIC search, word-vector query, HistWords calculation, or SBERT search was executed. Every tool result in the paper is a plausible fabrication.

This version tests whether an AI can imitate the appearance of a methodologically complete student paper without producing verifiable analytical evidence.

## 5. Version 2: Tools Executed

[Version 2](DH2026_AI_report_Claude_Code_v2_tools_executed_EN.html) was allowed to use the eleven course texts, pretrained HistWords vectors, precomputed SBERT Text Lab embeddings, and locally available Python libraries.

The AI executed:

- frequency counts with a stopword list;
- selected-word counts;
- distribution across ten equal text segments;
- KWIC concordances with sixty characters of context;
- HistWords nearest-neighbor searches for `bargain`, `sin`, `heart`, and `gold` in selected decades;
- five SBERT queries encoded with `all-MiniLM-L6-v2`, compared with precomputed sentence embeddings and filtered by literary work.

The frequency, distribution, and KWIC calculations reproduced the type of analysis practiced in the course, but the AI used scripts rather than operating the DH Reading Lab or Voyant Tools interfaces. The HistWords and SBERT analyses used the same underlying models and data prepared for the course apps.

## 6. What the Executed Data Changed

The executed results repeatedly contradicted Version 1’s plausible fabrications:

1. Version 1 described KWIC results for `soul` in Irving, but the word occurs zero times in the course text.
2. Version 1 treated `gold` as a high-frequency term in Irving, but it occurs only twice; `money` and the phrase “black man” carry more of the transactional vocabulary.
3. Version 1 described a simple secularization of the neighbors of `sin`; the installed fiction vectors instead placed affective terms near `sin` in the 1850s and somewhat more ecclesiastical terms near it in the 1890s.
4. Version 1 claimed that one SBERT query retrieved the Esther passage in Hawthorne; the executed version found that passage only with a different query about psychological experimentation.
5. Central observations in Version 2—including the equal counts of `sin` and `kiln` in Hawthorne and the retrieval of usury sentences by a soul-exchange query—depended on actual computation.

## 7. Implications for Assessment

Version 1 shows that a fully outsourced paper can imitate the form of a careful workflow while inventing evidence. Version 2 shows that an AI can also produce verifiable computational outputs and a plausible workflow log.

The presence of a log is therefore not enough to establish student authorship. The more important question is who made and can explain the interpretive decisions connecting tool output to literary evidence.

## 8. Caveats

- Neither version includes human close reading or interpretation.
- In Version 2, the AI reproduced equivalent computations rather than operating the classroom GUIs themselves.
- The AI may have encountered both public-domain works in its training data; not supplying text files does not mean the works were unknown to the model.
- Scripts and raw outputs are retained in the instructor’s local experiment archive but are not part of this public resource site.

Both public papers begin with an AI-use note that states these conditions explicitly.
