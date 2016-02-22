The custom synthesis trees, one for each collection. The latest versions contain the following files (earlier synth runs may have different file names):

Note that we have removed monotypic nodes from both trees. 

 * all_tips.tre file: a synthetic tree with tips from phylogeny and taxonomy (newick format, labels are 'ottname ottid')
 * phylo_only_tips.tre: a synthetic tree that only includes the tips from input phylognies (no taxonomy-only tips)
 * annotations.json: details of the synthesis run, including support and conflict for the edges
 * support.csv: a csv version of the support statements in annotations.json

These files were created using the [propinquity workflow](https://github.com/OpenTreeOfLife/propinquity). The README for that repository contains instructions on running your own synthesis. It requires python, C++ and libraries for each. 
