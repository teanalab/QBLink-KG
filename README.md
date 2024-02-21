# QBLink-KG
QBLink-KG is a modified version of QBLink, which is a high-quality benchmark for evaluating conversational understanding of Wikipedia content.

QBLink consists of sequences of up to three hand-crafted queries, with responses being single-named entities that match the titles of Wikipedia articles.

For the QBLink-KG, the English subset of the DBpedia snapshot from September 2021 was used as the target Knowledge Graph. QBLink answers provided as the titles of Wikipedia infoboxes can be easily mapped to DBpedia entity URIs - if the corresponding entities are present in DBpedia - since DBpedia is constructed through the extraction of information from Wikipedia infoboxes.

QBLink, in its original format, is not directly applicable for Conversational Entity Retrieval from a Knowledge Graph (CER-KG) because knowledge graphs contain considerably less information than Wikipedia. A named entity serving as an answer to a QBLink query may not be present as an entity in DBpedia. To modify QBLink for CER over DBpedia, we implemented two filtering steps: 1) we removed all queries for which the wiki_page field is empty, or the answer cannot be mapped to a DBpedia entity or does not match to a Wikipedia page. 2) For the evaluation of a model with specific techniques for entity linking and candidate selection, we excluded queries with answers that do not belong to the set of candidate entities derived using that model.

To give more details about QBLink-KG, please read our research paper:

Zamiri, Mona, et al. "Benchmark and Neural Architecture for Conversational Entity Retrieval from a Knowledge Graph", The Web Conference 2024.
