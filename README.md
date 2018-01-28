# UD_Tagalog

UD_Tagalog is a proof of concept treebank for Tagalog. This treebank uses the [CoNLL-U format](http://universaldependencies.org/format.html).

## Part-of-Speech (POS) Tags

For UPOSTAG, adhere to the set of [universal POS tags found here](http://universaldependencies.org/u/pos/index.html).

For XPOSTAG, we are using [the tagset from the Penn Treebank](https://catalog.ldc.upenn.edu/docs/LDC99T42/tagguid1.pdf) for the most part while adding some Tagalog specifig tags:

| POS Tag | Description |
| ------- | ----------- |
| NVP    | Nominal Verb |
| AVP    | Adjectival Verb |

This is to account for the zero copula in Tagalog [Schachter, pp. 61]. This approach is copied from [BKTreebank](https://arxiv.org/pdf/1710.05519.pdf). Nouns and adjectives will still be rightly tagged as NOUN and ADJ respectively for UPOSTAG if there is no verb present in the sentence, and additionally tagged NVP and AVP respectively for XPOSTAG to convey the idea that the structure itself is the equivalent of **be**.

## Enclitics -- TODO

Schachter pp. 411. Enclitics are divided into four classes. TODO: DESCRIBE THESE 4 CLASSES.

## Adjectives

Superlatives [JJS] - [Reduplication](http://www.seasite.niu.edu/Tagalog/Grammar%20Activities/Grammar%201/Adjectives/Adjectives-fs.htm)

## Verbs

### Empty Copula

Introduce a Tagalog-specific POS tag just as the authors did in [this paper](https://arxiv.org/pdf/1710.05519.pdf).

### Focus

Focus is annotated in the MISC field according to the CoNLL-U format since it is not currently considered a [universal feature](http://universaldependencies.org/u/feat/index.html).

| Focus | Abbreviation |
|-------|--------------|
| Actor | Actor |
| Goal | Goal |
| Beneficiary | Ben |

[ source ](http://www.seasite.niu.edu/Tagalog/Grammar%20Activities/Grammar%202/Verbal%20Focus/Verbalfocus-fs.htm) | [ source ](http://www.hawaii.edu/filipino/Grammar_Topics/Grammar_2-2.html) | [ table of common verbs with their focus and aspect ](http://www.seasite.niu.edu/Tagalog/Grammar%20Activities/Grammar%202/Verbal%20Focus/Verbalfocus-fs.htm)

## Issues

- Voice dimension in Tagalog is quite complex (see [this wiki article](https://en.wikipedia.org/wiki/Austronesian_alignment)). A possible solution with annotating voice is found in the Unimorph Schema [pp. 57, 58].

- The word **ang** also possesses a lot of functions (see Reid's Determiners, Nouns, or What? paper) so annotating it is not so straightforward. Is it a root with sentences such as `schachter-otanes-0`?

- It is difficult to parse Tagalog with paradigms such as X-bar syntax (see Van Valin [pp. 1]) since it's most basic structure is considered to be a Basic Sentence consisting of two daughters: a Predicate and a Topic (see Schachter, Otanes [pp. 60]). The nucleus of such sentences are often markers such as **ang** or **ng**. When these nuclei are removed, the sentence becomes ungrammatical.

- How do I annotate XPOSTAG for particles?

- Do I mark Case feature on the particle or the noun?

- kita is ko-ka -> me-you. 

## Notes

`sent_id` format:

    [author_name]-[page_number|_]-[sentence-position-in-page]

where:

- `author_name` is the name of the author(s)

- `page_number` is the number of the page in the book or article (or an `_` otherwise)

- `sentence-position-in-page` a 0-indexed position of the sentence i.e. if there are 3 example sentences in one page, 0 would be the first example in that page.

- Person as Dual and Case as Abs for kita (absolutive dual) since it conveys from "I" to "you" in one word.

## Resources

### Dictionary

- [Tagalog Dictionary](https://www.tagalog-dictionary.com/)

- [Tagalog Lang](https://www.tagaloglang.com/)

### Grammar

- De Vos, Fiona. **Essential Tagalog Grammar**. *BöD*, 2011.

- Schachter, Paul and Otanes, Fe. **Tagalog Reference Grammar**. *University of California Press*, 1983.

### Papers

- Sylak-Glassman, John. **The Composition and Use of the Universal Morphological Feature
Schema (UniMorph Schema)**. *Center for Language and Speech Processing at Johns Hopkins University*, 2016. [[pdf]](http://unimorph.org/doc/Sylak-Glassman_2016_-_UniMorph_Schema_User_Guide.pdf)

- Reid, Lawrence. **Determiners, Nouns, or What? Problems in the Analysis of Some Commonly Occuring Forms in Philippine Languages**. *Oceanic Linguistics*, Vol. 41, No. 2. (Dec., 2002), pp. 295-309. [[pdf]](https://scholarspace.manoa.hawaii.edu/bitstream/10125/32989/1/A49.2002.pdf)

- Van Valin Jr., Robert. **A Summary of Role and Reference Grammar**. *University at Buffalo, The State University of New York*, 2006. [[pdf]](http://www.romanistik.uni-freiburg.de/raible/Lehre/2006/Materialien/RRGsummary.pdf)