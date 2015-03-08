# Topography scripts


## Clustering ##

### embedding.py ###

To create cluster results based on individual connectivity matrices:

	embedding.py -s <subject> -f <output filebasename>

	where input is a connectivity matrix saved as a .mat file.


## Paths through cluster results: ##

### DoFindPaths.m ###

	[clus, randpath] = DoFindPaths(n);

	where `n` is the number of permutations,
	and a config file is loaded in the script.

Then set config file for path order as in: 

	config/config_my18_path.m

And finally, to run permutation test on path order:

	randPath = pathsPermute(clus, n);

### find_similar_paths.py ###

To find most common paths through a cluster map.


## Distance maps ##

### Calculating distance from DMN on the group-level ###
	
	[distDMN] = loadDistDMN_group(hemi);

New peaks can also be derived from `clus.peaks(find(clus.networks == XX))`

where `XX = DMN network from cluster results` 

### Comparing to myelin maps ###

	DoMyelin();

### Calculating distance from DMN on the individual-level ###

	[distances, zones, surfi_164] = loadDistDMN_individual(sub, hemi);

