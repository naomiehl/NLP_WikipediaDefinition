## Extract type facts from a Wikipedia file

### === Purpose ===

The goal of this lab is to extract the class to which an entity belongs from Wikipedia.
For example, given the Wikipedia article about Leicester:

    Leicester is a small city in England
    
the goal is to extract:

    Leicester TAB city

### === Provided Data ===

We provide:

1. a preprocessed version of the Simple Wikipedia (`wikipedia-first.txt`), which looks like above
2. a template for your code, `extractor.py`
3. a gold standard sample (`gold-standard-sample.tsv`).


### === Task ===

Complete the `extract_type()` function so that it extracts the type of the article entity from the content.
For example, for a content of "Leicester is a beautiful English city in the UK", it should return "city".
Exclude terms that are too abstract ("member of...", "way of..."), and try to extract exactly the noun(s).
You can also skip articles (e.g. `return None`) if you are not sure or if the text does not contain any type.
In order to ensure a fair evaluation, do not use any non-standard Python libraries except `nltk` (`pip install nltk`).

Input:

April
April is the fourth month of the year with 30 days.

Output:
April TAB month


### === Development and Testing ===

We provide a certain number of gold samples for validating your model.
Finally, we calculate a F1 score using following equation:

`F1 = (1 + beta * beta) * precision * recall / (beta * beta * precision + recall)`

with `beta = 0.5`, putting more weight on precision in that way.
