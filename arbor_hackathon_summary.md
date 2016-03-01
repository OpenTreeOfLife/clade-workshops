# Arbor summary

This is a summary of the Arbor parts of the hackathon, including links and descriptions of Arbor tools
for analyses that are associated with your group.

# Arbor on Amazon Cloud for the hackathon

We have created three Arbor instances in the cloud for this workshop.

- [Arbor1](arbor1.arborworkflows.com) for beetles
- [Arbor2](arbor2.arborworkflows.com) for catfishes
- [Arbor3](arbor3.arborworkflows.com) for barnacles

All of the functions discussed below are available on these instances and in the [arbor_analyses](https://github.com/OpenTreeOfLife/clade-workshops/tree/master/arbor_analyses/) folder on this github.
Eventually all functions will be included in [Arbor collections](https://github.com/lukejharmon/arborCollections).

# Beetles

1. *Method to pull two study trees from opentree and compare them:* The new Arbor method [pull and compare opentree studies](https://github.com/OpenTreeOfLife/clade-workshops/blob/master/arbor_analyses/phytophaga/pull%20and%20compare%20opentree%20studies.json) fetches two study trees from open tree of life based on their study id. The workflow then compares the topology of the two trees using the function phylo.diff from the [distory](https://cran.r-project.org/web/packages/distory/index.html) R package.

![inputs](https://github.com/OpenTreeOfLife/clade-workshops/blob/master/images/inputs_1.png)
![treecompare](https://github.com/OpenTreeOfLife/clade-workshops/blob/master/images/treematch.png)

2. *Workflow to mash together beetle tree and data matrix:* The data matrix is at the genus level while the tree is at the species level. The Arbor workflow [beetleDataTreeSmash](https://github.com/OpenTreeOfLife/clade-workshops/blob/master/arbor_analyses/phytophaga/beetleDataTreeSmash.json) matches the two by extracting genus names from the tree tip labels and then dropping all duplicates from the tree. We then make fake branch lengths and reconstruct ancestral character states on the tree. This workflow includes a few new generally useful Arbor functions for data processing.

![inputs](https://github.com/OpenTreeOfLife/clade-workshops/blob/master/images/inputs_2.png)
![inputs](https://github.com/OpenTreeOfLife/clade-workshops/blob/master/images/inputs_3.png)
![acebeetles](https://github.com/OpenTreeOfLife/clade-workshops/blob/master/images/acebeetles.png)

# Catfishes

1. *Process catfish data matrix and make heatmap view*

The Phenoscape team provided Arbor with sample-size data matrices and a matching small sample trees of a catfish family, which were extracted from Phenoscape and morphobank to perform initial integration.  The Arbor team incorporated two new, open-source rendering packages for heatmap (jheatmap) and heatmap&phylogeny (InCHlib) rendering to allow for exploring the large phenotype matrixes exported from Phenoscape. During the workshop, we used prototype visualizations to explore large trait presence/absence matrices (1250+ taxa, 200+ characters) and a second multi-valued character attribute table of equivalent size.   Renderings are provided below that represent interactive browser views (including a demonstration on the iPad).

![heatmap](https://github.com/OpenTreeOfLife/clade-workshops/blob/master/images/catfish-all-values-matrix.png)

**Ipad version**
![heatmap](https://github.com/OpenTreeOfLife/clade-workshops/blob/master/images/ipad-matrix-explorer.jpg)

The catfish tree was rolled up to be viewable at the family level using some traits selected out the full matrix:

![heatmap](https://github.com/OpenTreeOfLife/clade-workshops/blob/master/images/catfish-family-phyloTraits-rendering.png)


2. *Link catfish character data to images*

The catfish trait data is currently curated in Morphobank.  Images are associated with each specimen reported in the trait matrix.  As this data is exported from Morphobank into Arbor, an association table of tip-names to image names is created.  A method was added to Arbor that embeds image URLs into the tree-tips of an “annotated tree”.  Arbor allows additional information to be added at any node, so the trait data is added at the tips.  Additional trait information at the tips is used by visualization algorithms,such as phyloMap and PhyloPen.  

3. *Display catfish tree and data in phylopen*

PhyloPen, an interactive tree, matrix, and image renderer was tested for the first time on the catfish data this weekend.  PhyloPen is a native Java application which is a client of Arbor.  We used Arbor to preprocess the tree and matrix so the user can browse the values of traits on the tree.  This project was curated using Morphobank and we are still in the process of establishing integration between Morphobank and Arbor for attaching images to the correct tree tips.  Other data exports are working.  Below is a screenshot of PhyloPen browsing the catfish tree, matrix, and associated tip image:

# Barnacles

1. *Match tree and tip data, then reconstruct ancestral character states:* The workflow [aceBarnacles](https://github.com/OpenTreeOfLife/clade-workshops/blob/master/arbor_analyses/barnacles/aceBarnacles.json) makes the barnacle tree ultrametric using [PATHd8](http://www2.math.su.se/PATHd8/), then reconstructs ancestral character states on this ultrametric tree.
