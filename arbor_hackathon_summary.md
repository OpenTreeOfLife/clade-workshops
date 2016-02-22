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

1. Method to pull two study trees from opentree and compare them

The new Arbor method [pull and compare opentree studies](https://github.com/OpenTreeOfLife/clade-workshops/blob/master/arbor_analyses/phytophaga/pull%20and%20compare%20opentree%20studies.json) fetches two study trees from open tree of life based on their study id. The workflow then compares the topology of the two trees using the function phylo.diff from the [distory](https://cran.r-project.org/web/packages/distory/index.html) R package.

# Catfishes

# Barnacles
