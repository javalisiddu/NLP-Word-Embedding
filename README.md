# NLP-Word-Embedding
Introduction to BOW and TFIDF

Word Embedding Techniques
***********************************************************************
Bag of words:

From the text corpus, create a set of all unique words. Let's assume there are d number of unique words. Assign a number to each unique words and then 
create word vectors.

Let's take two simple documents and convert them into a vectos of d dimensios. Remember, each word represents a dimension.

documentA = 'the man went out for a walk'
documentB = 'the children sat around the fire'

set of 11 unique words = (the, man, went, out, for, a, walk, children, sat, around, fire)
Assigned numbers      = ( 0 ,  1,    2,    3,  4,  5,  6,      7,      8,     9,    10)

		       
vector for documentA = [1, 1, 1, 1, 1, 1, 1, 0, 0, 0, 0] of size 11 dimensions.

vector for documentB = [2, 0, 0, 0, 0, 0, 0, 1, 1, 1, 1]

In these vectors, each element represents the number of times the corresponding word is repeated in the document.
In documentB, since the term 'the' is repeated twice, the frequency is mentionaed as 2 in its vector.

Binary BOW: In this case, number of times a word is repeated does not matter, If the word from a document  is present in vocabulary (Set of unique words)
, the element will be 1 else 0.
So, in this case,

vector for documentA = [1, 1, 1, 1, 1, 1, 1, 0, 0, 0, 0] of size 11 dimensions.

vector for documentB = [1, 0, 0, 0, 0, 0, 0, 1, 1, 1, 1]


***********************************************************************


Term Frequency: This summarizeshow often a term/word appears within a doucument.

TF(t) = (Number of times term t appears in a document) / (Total number of terms in the document)

Inverse document frequency: This downscales words that appear alot across the documents.
Term frequency is how common a word is, inverse document frequency (IDF) is how unique or rare a word is.

IDF(t) = log_e(Total number of documents / Number of documents with term t in it)

The IDFs are calculated  for each word in the vocabulary, assigning the lowest score to the most frequently observed word.

Example,
Consider a document containing 100 words wherein the word apple appears 5 times. The term frequency (i.e., TF) for apple is then (5 / 100) = 0.05.
Now, assume we have 10 million documents and the word apple appears in one thousand of these. Then, the inverse document frequency (i.e., IDF) is 
calculated as log(10,000,000 / 1,000) = 4.
Thus, the TF-IDF weight is the product of these quantities: 0.05 * 4 = 0.20.

documentA = 'the man went out for a walk'
documentB = 'the children sat around the fire'

Let's create TF-IDF vector for documentA and documentB.

set of unique words 

For the term 'the' in document A, term frequency is (1/7) = 0.14. 

IDF is log (2/2)=0, SO TF*IDF score for the word 'the' will be 0. Similarly, the TF*IDF vectors with size 11 dimensions are created. Refer the Word embedding code.
