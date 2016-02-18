# Finding OpenTree data

Here are some instructions on how to find opentree data for the workshop

##Clades in the synthesis tree

* barnacles: [Thecostraca](https://tree.opentreeoflife.org/opentree/ottol@1040184)
* beetles: [Chrysomeloidea](https://tree.opentreeoflife.org/opentree/argus/ottol@765489/Chrysomeloidea) and [Curculionoidea](https://tree.opentreeoflife.org/opentree/argus/ottol@765492/Curculionoidea)
* catfish: [Siluriformes](https://tree.opentreeoflife.org/opentree/argus/ottol@701516/Siluriformes)

##Taxonomy info

Here are links to the taxonomy browser for the three clades:
* barnacles: [Thecostraca](https://tree.opentreeoflife.org/taxonomy/browse?name=Thecostraca)
* beetles: [Chrysomeloidea](https://tree.opentreeoflife.org/taxonomy/browse?id=765489) and [Curculionoidea](https://tree.opentreeoflife.org/taxonomy/browse?id=765492)
* catfish: [Siluriformes](https://tree.opentreeoflife.org/taxonomy/browse?name=Siluriformes)

##Published phylogenies
We don't have a way to search for taxa in the online interface for the curator tool. But, we do have [web services](https://github.com/OpenTreeOfLife/opentree/wiki/Open-Tree-of-Life-APIs) for this that you can call using `curl`. By default, these only return the identifiers for the studies and trees. You can use the `verbose` option to get all of the info, or use the `study` methods to retrieve single studies or trees - see the [documentation](https://github.com/OpenTreeOfLife/opentree/wiki/Open-Tree-of-Life-APIs#studies-containing-source-trees). 

Barnacles:

    https://api.opentreeoflife.org/v2/studies/find_trees \
    -H "content-type:application/json" \
    -d '{"property":"ot:ottTaxonName","value":"Thecostraca"}'

Catfish: 

    https://api.opentreeoflife.org/v2/studies/find_trees \
    -H "content-type:application/json" \
    -d '{"property":"ot:ottTaxonName","value":"Siluriformes"}'

Chrysomeloidea:

    https://api.opentreeoflife.org/v2/studies/find_trees \
    -H "content-type:application/json" \
    -d '{"property":"ot:ottTaxonName","value":"Chrysomeloidea"}'

Curculionoidea:

    https://api.opentreeoflife.org/v2/studies/find_trees \
    -H "content-type:application/json" \
    -d '{"property":"ot:ottTaxonName","value":"Curculionoidea"}'
