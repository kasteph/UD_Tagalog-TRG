# UD_Tagalog

UD_Tagalog is a proof of concept treebank for Tagalog. This treebank uses the [CoNLL-U format](http://universaldependencies.org/format.html).

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

- Voice annotations are from UniMorph schema:

    - AgentFoc is Agent Focus.

    - ConvFoc is Conveyed Focus.

- Person as Dual and Case as Abs for kita (absolutive dual) since it conveys from "I" to "you" in one word.

## Resources

### Dictionary

- [Tagalog Dictionary](https://www.tagalog-dictionary.com/)

### Grammar

- De Vos, Fiona. **Essential Tagalog Grammar**. *BöD*, 2011.

- Schachter, Paul and Otanes, Fe. **Tagalog Reference Grammar**. *University of California Press*, 1983.

### Papers

- Sylak-Glassman, John. **The Composition and Use of the Universal Morphological Feature
Schema (UniMorph Schema)**. *Center for Language and Speech Processing at Johns Hopkins University*, 2016. [[pdf]](http://unimorph.org/doc/Sylak-Glassman_2016_-_UniMorph_Schema_User_Guide.pdf)

- Reid, Lawrence. **Determiners, Nouns, or What? Problems in the Analysis of Some Commonly Occuring Forms in Philippine Languages**. *Oceanic Linguistics*, Vol. 41, No. 2. (Dec., 2002), pp. 295-309. [[pdf]](https://scholarspace.manoa.hawaii.edu/bitstream/10125/32989/1/A49.2002.pdf)

- Van Valin Jr., Robert. **A Summary of Role and Reference Grammar**. *University at Buffalo, The State University of New York*, 2006. [[pdf]](http://www.romanistik.uni-freiburg.de/raible/Lehre/2006/Materialien/RRGsummary.pdf)