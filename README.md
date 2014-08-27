# phylesystem-1

If you are not an open tree developer working on the
api or tools that read from the "raw" git repo), you can probably
ignore this repository.

This is a repository of phylogenetic studies used by the
[Open Tree of Life](http://opentreeoflife.org) project.
The files are in the [HoneyBadgerFish 1.2](https://github.com/OpenTreeOfLife/api.opentreeoflife.org/wiki/HoneyBadgerFish) 
NexSON syntax.

This repository is the backend datastore of the Open Tree 
[api](https://github.com/OpenTreeOfLife/api.opentreeoflife.org)
web services.

Currently we do not support pull requests to this repo (though
we hope to soon).

We have not decided on the final naming scheme for shards in the 
phylesystem repository (if we use a sharding strategy). Additional
phylesystem-*suffix* repositories may be added.

The top-level [phylesystem](https://github.com/OpenTreeOfLife/phylesystem)
repository will hold git submodule links to each of the 
shards. 


# History

The initial state of the repository was created by downloading
studies from phylografter to update the
[old-phylesystem repository](https://github.com/mtholder/old-phylesystem).

Then (assuming the directory structure):

    somepath/old-phylesystem
    somepath/peyotl

then you can create the content of this directory by:

    cd somepath/old-phylesystem
    python bin/refresh_nexsons_from_phylografter.py -v
    cd ../peyotl
    mkdir -p ../phylesystem/phylesystem-0/study
    mkdir ../migration2phylesystem-1
    python dev/migrate_testing_phylesystem.py ../old-phylesystem ../phylesystem/phylesystem-1 ../migration2phylesystem-1 >migration-out.txt 2>migration-err.txt 



## License

Some of the *data* in this repository is released under the [Create Commons Zero 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/) waiver; the rest is released
to the public without any particular license or waiver.

When using any of this data please cite the original source using a bibliographic reference and DOI for the study's publication, as given in each file, and Treebase or other data deposit identifier if available.
