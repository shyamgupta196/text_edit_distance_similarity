# Analyzing Text Similarity Using Edit Distance

## Description
This method calculates the edit distance between two texts to estimate their similarity or dissimilarity. The edit distance measures how many operations — such as inserting, deleting, or substituting characters — are needed to transform one text into another. For instance, simple edit distance between "cut" and "cat" is 1, as only one substitution is needed. Similarly, simple distance between "cat" and "at" is also 1, as one deletion suffices. In its simplest form, edit distance assigns an equal cost to all operations — insertions, deletions, and substitutions. Variants of the method allow for different cost structures, making it adaptable to various applications. For example, this method can be used to compare texts like dialects of a language, definitions of similar concepts across disciplines, or even versions of the same news article from different media sources. It can also be applied to anonymize personal information by distorting text.

## Use Cases
- Identifying different mentions of entities (e.g. names like "Donald Trump", "D. Trump", and "Trump")
- Finding tweets/social media posts similar to a certain tweet, sentence, or claim.

## Input Data
The method is directly applicable to textual digital behavioral data from social media and other digital platforms. User can provide these input texts to evaluate edit distance by directly writing them in the notebook [text_edit_distance_similarity.ipynb](https://github.com/taimoorkhan-nlp/text_edit_distance_similarity/blob/main/text_edit_distance.ipynb). 

Provide two posts/strings as input directly in the notebook [text_edit_distance_similarity.ipynb](https://github.com/taimoorkhan-nlp/text_edit_distance_similarity/blob/main/text_edit_distance.ipynb) to compare.
  
For example, we want to measure the dissimilarity (edit distance) between the two tweets sharing the same news:
```
tweet1 = "Excited to share our latest research on AI and its impact on social sciences! Leveraging data for better insights"
tweet2 = "Thrilled about our new findings on how AI transforms social science research. Innovation meets impact!"
```

## Output Data
The output string has the following information

  - `Edit distance version used` from the available implementation versions.
  - `at word/character level` showing whether the method is applied at word or character level
  - `score (as integer value)` representing the edit distance or cost between the texts, usually interpreted as the minimum edits needed to transform source text to target text using the available operations and their costs.

The two sample outputs for tweet1 and tweet2 are given in the input above. First using Levenshtein edit distance at the word level while second using simple edit distance at the character level.
Levenshtein edit distance (at word level) is 26 i.e., tweet1 and tweet2 are 26 word changes apart using Levenshtein edit distance.
Simple edit distance (at character level) is 71 i.e., tweet1 and tweet2 are 71 character changes apart using simple edit distance.
```
Levenshtein edit distance (at word level): 26
simple edit distance (at character level): 71
```
## Hardware
The method runs on a cheap virtual machine provided by cloud computing company (2 x86 CPU core, 4 GB RAM, 40GB HDD). with O(k x m x n) time complexity, when the input is 2 column CSV (K=Number of rows).

## Environment Setup
The method only uses string and random packages included by default, and therefore doesn't require prior installations.

## How to Use
- run `pip install jupyter` or `conda install jupyter`, if not installed already
- run Jupyter using the command `jupyter lab` or `jupyter notebook`
- Open and execute all cells in [text_edit_distance_similarity.ipynb](https://github.com/taimoorkhan-nlp/text_edit_distance_similarity/blob/main/text_edit_distance.ipynb).
- execute the notebook cells to call all methods defined in [utils.py](https://github.com/taimoorkhan-nlp/text_edit_distance_similarity/blob/main/utils.py) on the same texts

## Technical Details
The method offers 3 edit distance variants (__Simple edit distance__, __Levenshtein edit distance__ and __Damerau-Levenshtein edit distance__) between two texts both at character and word level, and has the following operations:

- __Simple edit distance__ i.e., having insertion, deletion, and substitution operations, all having cost 1.
- [__Levenshtein edit distance__](https://www.sciencedirect.com/science/article/pii/S0010482523001142) i.e., having insertion and deletion with cost 1 and substitution with cost 2 (it is also equivalent to saying no substitution allowed)
- [__Damerau-Levenshtein edit distance__](https://www.sciencedirect.com/science/article/pii/S1319157821001828) i.e., having insertion, deletion, substitution, and transposition, all having equal cost 1.
 
The method is reproducible as it offers vanilla implementation without requiring any packages or resources to be installed. It only uses the basic (string and random) packages usually already included. It gives full control to update costs and scale as needed. Random seeds are defined to have predictable random numbers for reproducibility.
  
## Publications
1. Hossain, E., Rana, R., Higgins, N., Soar, J., Barua, P. D., Pisani, A. R., & Turner, K. (2023). Natural language processing in electronic health records in relation to healthcare decision-making: a systematic review. Computers in biology and medicine, 155, 106649.
2. Chaabi, Y., & Allah, F. A. (2022). Amazigh spell checker using the Damerau-Levenshtein algorithm and N-gram. Journal of King Saud University-Computer and Information Sciences, 34(8), 6116-6124.

## Contact Details
Taimoor Khan (<a href=mailto:taimoor.khan@gesis.org>taimoor.khan@gesis.org</a>)
