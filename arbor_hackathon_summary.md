# Arbor summary

This is a summary of the Arbor parts of the hackathon, including links and descriptions of Arbor tools
for analyses that are associated with your group.

# Arbor on Amazon Cloud for the hackathon

We have created three Arbor instances in the cloud for this workshop.

- [Arbor1](arbor1.arborworkflows.com) for beetles
- [Arbor2](arbor2.arborworkflows.com) for catfishes
- [Arbor3](arbor3.arborworkflows.com) for barnacles

All of the functions discussed below are available on these instances and in the [arbor_analyses](https://github.com/OpenTreeOfLife/clade-workshops/tree/master/arbor_analyses/) folder on this github.
Eventually all functions will be included in [Arbor collections]().

# Beetles

1. *Method to pull two study trees from opentree and compare them:* The new Arbor method [pull and compare opentree studies](https://github.com/OpenTreeOfLife/clade-workshops/blob/master/arbor_analyses/phytophaga/pull%20and%20compare%20opentree%20studies.json) fetches two study trees from open tree of life based on their study id. The workflow then compares the topology of the two trees using the function phylo.diff from the [distory](https://cran.r-project.org/web/packages/distory/index.html) R package.

[inputs](images/inputs1.png)
[treecompare](images/treematch.png)

2. *Workflow to mash together beetle tree and data matrix:* The data matrix is at the genus level while the tree is at the species level. The Arbor workflow [beetleDataTreeSmash](https://github.com/OpenTreeOfLife/clade-workshops/blob/master/arbor_analyses/phytophaga/beetleDataTreeSmash.json) matches the two by extracting genus names from the tree tip labels and then dropping all duplicates from the tree. We then make fake branch lengths and reconstruct ancestral character states on the tree. This workflow includes a few new generally useful Arbor functions for data processing.

# Catfishes

1. *Process catfish data matrix and make heatmap view*

2. *Link catfish character data to images*

3. *Display catfish tree and data in phylopen*

# Barnacles

1. *Match tree and tip data, then reconstruct ancestral character states:* The workflow [aceBarnacles](https://github.com/OpenTreeOfLife/clade-workshops/blob/master/arbor_analyses/barnacles/aceBarnacles.json) makes the barnacle tree ultrametric using [PATHd8](http://www2.math.su.se/PATHd8/), then reconstructs ancestral character states on this ultrametric tree.
