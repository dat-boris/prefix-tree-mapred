prefix-tree-mapred - Mapreduce implmentation of generating PrefixSpan
------------------

Given a sequence, a PrefixSpan (Prefix-projected Sequential Pattern mining) is a list that allows you to quickly identify a list of objects which contains a particular order of sequence.

> Open invitation to hack: you are welcome clone this repo and implement


### Example PrefixSpan

From https://github.com/zhhailon/prefixspan

Format of input data:

      3 1 3 4 5
      2 3 1
      3 4 4 3
      1 3 4 5
      2 4 1 
      6 5 3 

Format of results:
 
      itemsets
      ( ids ) freq
      itemsets
      ( ids ) freq
      itemsets
      ( ids ) freq
      ... 

Here is an example: 
 
      1 
      ( 0 1 3 4 ) : 4
      1 3 
      ( 0 3 ) : 2
      1 3 4 
      ( 0 3 ) : 2
      1 3 4 5 
      ( 0 3 ) : 2
      1 3 5 
      ( 0 3 ) : 2
      1 4 
      ( 0 3 ) : 2
      ... 


Anonymised Test data
--------------------

The test data is avaliable at

    sequence.gz

It contains a list of:

object name|item-id|time

Which is a list of hash of original data of set of sequence.

## Input parameter

The algorithm takes the following paremater

* _minPrefixLength_ - minimal lenght of prefix generated
* _maxExampleCount_ - maximum number of Examples to include
* _minCount_ - minimum number of count for the objects

Expected output
---------------

We expect a final list of output of:

prefix|exampleitem|count



Bouns: Parallel generation of K-ary tree
---------------------------------------

Constructing a K-ary tree out of paths.  For each next steps, construct a graph of where things are listening.

http://en.wikipedia.org/wiki/K-ary_tree



References
----------

A known description of MR implementation of the algorithm is availale at: PDF on distributed prefixspan algorithm - http://bbs.chinacloud.cn/attachment.aspx?attachmentid=5128

For K-ary tree, there's a possible reference implementation at:

http://dl.acm.org/citation.cfm?id=523549.822923



##Useful Mr. Job resources

* https://github.com/Yelp/mrjob

* http://aimotion.blogspot.ca/2012/08/introduction-to-recommendations-with.html


##Other research resources

A non-mapreduce algorithm: K-ary tree - http://stackoverflow.com/questions/1005551/construct-a-tree-structure-from-list-of-string-paths

### Prefix span related

* Introduction to prefixSpan - http://webdocs.cs.ualberta.ca/~zaiane/courses/cmput695-04/slides/PrefixSpan-Wojciech.pdf
* Example prefix span project - https://code.google.com/p/prefixspan/
* PDF on distributed prefixspan algorithm - http://bbs.chinacloud.cn/attachment.aspx?attachmentid=5128
* Other implmentation of Prefix span algorithm - https://github.com/gauravsc/PrefixTree-Map-Reduce using mahour


### Other map reduce examples

* N-gram generation -  Computing n-Gram Statistics in MapReduce -  https://www.mpi-inf.mpg.de/~kberberi/publications/2013-edbt2013.pdf
* Example Graph tarversal algorithm in MapReduce - http://www.johnandcailin.com/blog/cailin/breadth-first-graph-search-using-iterative-map-reduce-algorithm



