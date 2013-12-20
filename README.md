README

Text analysis: Counting lemmata use
======================================================== 

This script will perform a text analysis by identifying lemmata used throughout the text, count their frequency and indicate their position.

A possible application is the analysis of word use in a poetic corpus, where each word will be related to its lemma ("am" -> "be" or "bore" -> "bear) before being counted and located. 

The R markdown code will output an html document with: 
- Frequency of each lemma found in the corpus. 
- Verse where the lemma was found (preceded by code for collection and the number of document and verse where the lemma was found)

The code requires the following input text files: 
1 - A lexicon with at least two tab delimited columns, the first listing the inflected forms and the second the corresponding lemma. For Italian, a lexicon can be found at http://sslmit.unibo.it/morphit
2- A corpus containing the text to analyse. Ideally the corpus should be input as one separated text file for each individual document (e.g. one file for each poem). In my case I split a text file containing multiple poems by separating each with "@" and then passing the command 
awk '{ if ($0 == "@") {n++;close(filename)} else {filename = sprintf("part%02d.txt", n); print >filename; }}' onefile_text.txt
