# Damnation Without a Soul: The Vocabulary of Sin in Irving's "The Devil and Tom Walker" and Hawthorne's "Ethan Brand"

> **AI-use note.** This paper was researched and written entirely by a generative AI system (Claude) as an instructor-run experiment, not as a student submission. Unlike Version 1, the frequency, distribution, KWIC, HistWords, and SBERT results come from executed analyses. The close reading, framing, interpretation, and prose remain AI-generated. Supporting scripts and raw outputs are retained in the instructor's local experiment archive.

*DH2026 Final Paper (English version — based on actually executed tool experiments)*

## 1. Title and Question

Washington Irving's "The Devil and Tom Walker" (1824) and Nathaniel Hawthorne's "Ethan Brand" (1850) tell nearly the same story — a man loses his soul — in opposite registers. Tom Walker bargains with the devil, prospers as a usurer, and is finally carried off "like a child into the saddle." Ethan Brand searches the world for the Unpardonable Sin, finds it in his own heart, and burns himself in a lime-kiln, leaving a skeleton with a marble heart.

My question: **where does each story locate sin — in transactions outside the sinner, or in the body inside him — and what vocabulary does each story use to do so?** My hypothesis from close reading was that Irving externalizes sin as an economic object while Hawthorne internalizes it as a bodily organ. Three kinds of computational experiments partly confirmed this, partly corrected it, and produced one finding I did not anticipate at all: Irving narrates a damnation story from which the word *soul* is entirely absent.

## 2. Texts and Axis of Comparison

- Washington Irving, "The Devil and Tom Walker" (Week 5)
- Nathaniel Hawthorne, "Ethan Brand" (Week 7)

Axis of comparison: the vocabulary of sin and its material figures — Irving's economic cluster (*money*, *bargain*, *terms*) against Hawthorne's corporeal-industrial cluster (*heart*, *fire*, *kiln*, *marble*, *sin*).

## 3. Initial Close Reading

Reading Irving, what struck me was how comic and public Tom's damnation is. The devil is a business partner; the negotiation stalls over conditions, not over the soul; Tom's wife tries to cut her own deal and vanishes, leaving an apron containing "a heart and liver tied up in it." Tom's inner life barely exists — even his late piety is a Bible kept on the counting-house desk. Hawthorne reads like the negative image: Brand's sin has no object and cannot be traded. It is "the sin of an intellect that triumphed over the sense of brotherhood with man," and at the end it becomes literally visible as a thing — the shape of a human heart in marble, inside the burnt skeleton's ribs. My working impression: Irving turns a soul into property; Hawthorne turns a heart into stone.

## 4. Category 1: Frequency, KWIC, and Distribution

I ran a simple Python script (Colab-style, as practiced in Weeks 5–8) over the two course text files: word frequencies with a stopword list, counts of selected words, distribution across ten equal segments, and KWIC concordances.

**Frequency.** Irving (4,827 tokens): the top content words are *tom* (59), *black* (33), *man* (24), *walker* (18), *money* (15), *swamp* (14), *devil* (13). Hawthorne (6,507 tokens): *ethan* (38), *lime* (37), *man* (35), *brand* (34), *burner* (22), *fire* (21), *kiln* (20), *sin* (20), *heart* (12), *marble* (11).

Two things surprised me. First, my hypothesis about Irving's "economic vocabulary" was right in direction but wrong in detail: *gold* occurs only twice, and *soul* — the word I assumed the story was about — occurs **zero** times. The transaction runs on *money* (15) and on the devil's name in this text, which is not primarily "devil" but **"black man"** (the phrase occurs 15 times; *black* alone 33). Irving's damnation is narrated almost entirely without theological vocabulary: *soul* 0, *sin* 1, *gold* 2. Second, in Hawthorne, *sin* (20) is exactly as frequent as *kiln* (20) and nearly as frequent as *fire* (21): the moral keyword and the industrial apparatus have the same lexical weight. Hawthorne's sin belongs, statistically, to the same word-world as lime-burning.

**Distribution (10 segments).** Irving's *money* recurs across the second half — [2,0,0,2,0,0,3,4,2,2] — because the story continues past the pact into Tom's usury career; damnation is not an event but an ongoing business. Hawthorne's *sin* [1,0,4,7,0,4,1,0,2,1] and *fire* [3,1,0,5,1,2,0,5,3,1] pulse through the whole text, while *heart* clusters at two points — [0,0,5,1,0,0,0,0,4,2] — segment 3, where Brand lays "his finger on his own heart" and declares "Here!", and segments 9–10, the marble heart. The heart appears where the sin is *diagnosed* and where it is *produced as an object*: a beginning and an end of a manufacturing process.

**KWIC.** The concordances were the strongest evidence. Irving's single *sin* is a bookkeeping metaphor: Tom "seemed to think every sin entered up to their account became a credit on his own side." Of his two *heart*s, one is the literal organ in the apron; the other is the closing moral — "Let all griping money brokers lay this story to heart" — where *heart* survives only inside a commercial idiom addressed to brokers. Hawthorne's twelve *heart*s run from diagnosis ("laid his finger on his own heart. 'Here!'") through the process chart of the narrator's four verbs — the heart "had withered — had contracted — had hardened — had perished" — to Bartram's final question, "Was the fellow's heart made of marble?" Seen as a KWIC list, the four verbs read almost like a chemical procedure, the same calcination the kiln performs on marble.

## 5. Category 2: HistWords (eng-fiction-all_sgns)

Using the HistWords historical embeddings (English fiction corpus, decade-level SGNS vectors, as introduced in Week 9), I computed nearest neighbors for *bargain*, *sin*, *heart*, and *gold* in the 1820s, 1850s, and 1890s.

A first, practical result: the 1820s fiction vectors are too sparse to use — *bargain* and *sin* have no usable vector there, and the *heart* neighbors are noise (dialogue words like *exclaimed*, *said*). I therefore compared the 1850s and 1890s and treat the 1820s as a documented failure.

**bargain (1850s):** *make*, *offer*, *exchange*, *proposal* — squarely transactional — but also *hearty*, *merry*, *lucky*, presumably from idioms like "into the bargain." The word lives in a world of deals and of jovial talk about deals, which is precisely Irving's tone: his devil-pact is conducted in the sociable register of Yankee dealmaking ("Done!" said Tom Walker. — So they shook hands, and struck a bargain).

**sin (1850s):** *shame*, *guilt*, *folly*, *punishment*, *crime*, *innocence*, *sorrow*, *conscience*. I had expected a technical-theological neighborhood (*iniquity*, *repentance*) and predicted secularization toward 1900. The data did not cooperate: already in the 1850s *fiction* corpus, *sin* lives among **feelings** — shame, sorrow, conscience — and if anything the 1890s neighbors (*penance*, *resurrection*, *sinner*) look more ecclesiastical, not less. My correction: in fiction, as opposed to sermons, sin was already an affective word at mid-century. That reframes Hawthorne: when he attaches *sin* to a burning heart, he is not importing theology into fiction but intensifying what the novelistic use of the word already was — an emotion-adjacent term — while Irving comically drains even that affect out of it, leaving only bookkeeping.

**heart (1850s):** the neighborhood splits exactly in two — bodily (*beat*, *beating*, *bosom*, and in the 1890s *ached*, *throb*, *pulse*, *breast*) and affective-spiritual (*soul*, *darling*, *loving*, *sorrow*, *anguish*). This double neighborhood is the ambiguity Hawthorne's ending collapses: the marble heart is at once an anatomical object inside a ribcage and the emblem of a moral condition.

**gold (all decades):** *silver*, *jewels*, *lace*, *purse*, *coins*, *silk* — pure material luxury, no moral vocabulary at all. The moral charge of treasure in Irving is produced by the story, not carried by the word; connotation is not "in" the lexicon.

## 6. Category 3: SBERT Text Lab (all-MiniLM-L6-v2, sentence unit, Top K 5)

I ran five queries against the course corpus embeddings, filtered by work, following the Week 10 procedure.

**Q1: "a man agrees to give up his soul in exchange for wealth" (Irving).** The top hit (0.515) was not the pact scene but the usury career: "In this way he made money hand over hand; became a rich and mighty man, and exalted his cocked hat upon change." The rest of the top five: the devil guarding buried treasure, Tom consoling himself for his wife's loss, his reputation as "a ready moneyed man," and the land jobber begging for indulgence. The soul-exchange query retrieves the *moneylending* sentences. At first I thought the tool had failed; rereading, I think it found something true — in Irving, the diabolic exchange and ordinary finance are written in the same language, so a model that only sees semantics cannot tell them apart.

**Q2: "two men negotiate and disagree about the terms and conditions of an agreement" (Irving).** The top five mixed the pact and the business seamlessly: "The right of prior claim" (0.339), then — striking — "In proportion to the distress of the applicant was the hardness of his terms" (0.290), which is about Tom's *customers*, ranked above and beside "'Done!' said Tom Walker. — So they shook hands, and struck a bargain" (0.290). The model's confusion is Irving's satire: dealing with the devil and dealing with a Boston usurer are the same genre of sentence.

**Q3: "a man's heart turns to stone because he has cut himself off from other people" (Hawthorne).** Top hits (0.433–0.397): the "heart to heart" confrontation, Bartram's "Was the fellow's heart made of marble?", the narrator's "But where was the heart?", the kiln's blasting heat, and the "infinite absurdity of seeking throughout the world for what was the closest of all things to himself." Semantic search assembled, in one ranked list, the story's entire argument about interiority — passages spread across the text that keyword search for *stone* would never have grouped.

**Q4: the same query, cross-run on Irving.** Scores dropped (max 0.403), and rank 2 (0.369) was the apron: "Tom seized the check apron, but, woful sight! found nothing but a heart and liver tied up in it." When I ask Irving for a hardened heart, the text hands me an actual heart in an apron. The cross-run made my thesis graphic: Hawthorne answers an interiority query with interiority; Irving answers it with a literal organ as sight gag.

**Q5: "he used another human being as the subject of a psychological experiment and destroyed her" (Hawthorne).** Rank 1 (0.467): Brand as "a cold observer, looking on mankind as the subject of his experiment"; rank 3 (0.396): the Esther sentence — the girl "whom, with such cold and remorseless purpose, Ethan Brand had made the subject of a psychological experiment." I had skimmed Esther on first reading. The retrieval sent me back to the one passage where Brand's supposedly inward sin has a named victim — internalized sin turns out to be *extracted from other people*.

**What SBERT flattened:** tone. The similarity scores treat Irving's comic sentences and Hawthorne's solemn ones as equally "close" to my queries, and all Irving scores were low in absolute terms (mostly under 0.45). Irony is precisely what the cosine does not measure.

## 7. Comparing the Three Methods and Returning to the Texts

The counting experiments produced the finding I value most: **Irving tells a damnation story with no *soul*, one *sin* (as bookkeeping), and two *heart*s (a sight gag and a brokers' idiom)** — the theological lexicon is not subordinated but deleted, replaced by *money* and a racialized "black man" who forecloses on Tom like a creditor. HistWords showed that this deletion is a choice, not a period norm: in the same fiction corpus, *sin* was already saturated with feeling (*shame*, *sorrow*, *conscience*) — the affective register Hawthorne amplifies and Irving refuses. And SBERT demonstrated the two economies directly: queries about souls and negotiations retrieve Irving's usury sentences (circulation), while queries about hardened hearts and experiments retrieve Hawthorne's kiln and Esther (production).

My revised claim: the contrast is not outside/inside but **two economies of sin**. In Irving, sin circulates — it moves like money between parties, is entered in accounts, and ends in foreclosure; that is why the story needs no *soul*, only *terms*. In Hawthorne, sin is manufactured — accumulated inside a man by consuming other people (Esther), processed in an industrial furnace whose vocabulary (*lime*, *kiln*, *burner*) is as frequent as the sin itself, and delivered at the end as product: marble, "burnt into perfect, snow-white lime" around a heart that would not convert.

## 8. Limits, Failures, and Next Steps

The 1820s HistWords vectors were unusable — precisely the decade of Irving's story — so my historical comparison starts a generation late. My frequency observations rest on two short texts and one segmentation (ten equal parts); a different split would change the curves. The SBERT scores were low in absolute terms for Irving (under 0.52 everywhere), and rankings shifted when I rephrased queries, so I treated ranked lists as pointers, not measurements. And one variable I could not isolate: Irving's "black man" is a racialized figure, and the frequency of *black* (33) belongs to a history of representing the devil — and of representing Blackness — that none of my three tools can analyze; it needs historical scholarship, not embeddings. If I continued, I would add Poe's "The Man of the Crowd" (sin with neither transaction nor confession) and test whether "circulation vs. production" survives a story where sin never becomes an object at all.

## 9. Workflow Log

| Method | Tool | What I searched | Conditions | Main result | Passage revisited |
| --- | --- | --- | --- | --- | --- |
| Frequency | Python script (Colab-style), course text files | top content words; counts of gold, money, soul, sin, heart, fire, marble | 2 texts, stopword list, tokens: Irving 4,827 / Hawthorne 6,507 | Irving: money 15, soul 0, sin 1, gold 2, "black man" 15. Hawthorne: sin 20 = kiln 20 ≈ fire 21, heart 12, marble 11 | Irving's counting-house piety; Hawthorne's kiln descriptions |
| Distribution | same script | money, devil, sin, fire, heart across 10 segments | 10 equal token segments | Irving money recurs through 2nd half [2,0,0,2,0,0,3,4,2,2]; Hawthorne heart clusters at seg 3 and 9–10 [0,0,5,1,0,0,0,0,4,2] | "laid his finger on his own heart" scene; marble-heart ending |
| KWIC | same script (60-char concordance) | heart, sin, bargain, "black man" (Irving); heart, marble (Hawthorne) | all occurrences | Irving's one sin = accounting metaphor; hearts = apron + brokers' idiom. Hawthorne: "withered — contracted — hardened — perished" | apron scene; four-verbs passage |
| Word vectors (historical) | HistWords eng-fiction-all_sgns (decade SGNS) | bargain, sin, heart, gold | 1820s / 1850s / 1890s, top 12 neighbors, cosine | 1820s unusable (sparse). 1850s: sin → shame, guilt, sorrow, conscience (affective, not technical-theological); bargain → make, offer, exchange + merry, lucky; heart split bodily/affective; gold → pure luxury goods | Irving's "Done!" handshake; Hawthorne's burning heart |
| Transformer | SBERT Text Lab embeddings (all-MiniLM-L6-v2), sentence unit, Top K 5, work filter | Q1 soul-for-wealth; Q2 negotiation of terms; Q3 heart-to-stone; Q4 = Q3 cross-run on Irving; Q5 psychological experiment | cosine on precomputed normalized embeddings | Q1 retrieves usury career (0.515) not pact; Q2 ranks usury "terms" beside the devil's bargain; Q3 assembles interiority passages; Q4 returns the apron heart (0.369); Q5 finds Esther (0.396) without keywords | usury passages; Esther passage; apron scene |
