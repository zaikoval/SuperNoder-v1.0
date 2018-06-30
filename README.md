# SuperNoder1.0
This repository contains the SuperNoder sources, the main outcome of the work: SuperNoder: a tool to discover over-represented modular structures in networks.

Authors: They have been anonymized for the review process. 

SuperNoder is a python developed tool that enables the simplification of networks by means of collapsing of frequent motifs. It can be used on a own pc or by its web interface available at: inserire link

To execute SuperNoder on your pc, Docker (download: https://www.docker.com/what-docker#/container-platform) must be previously installed.

To run SuperNoder the user must perform in the supernoder/ directory:
* docker-compose build
* docker-compose up

SuperNoder will be accessible at http://localhost:8080.

If you use SuperNoder in your work, please cite the paper: [1] [authors], SuperNoder: a tool to discover over-represented modular structures in networks. [journal-info][year]

For more info please contact: It will be available after publication.

# Input 
The tool requires two series of data: nodes and edges. 

Input nodes must be provided one for each row. Each node is composed by its id and label separated by a blank space.

Input edges must be provided one for each row. Each edge is composed by two node ids separated by a blank space. Edges that have nodes that are not present in the node series will be automatically discarded by SuperNoder.

Example of nodes series:&emsp;&emsp;&emsp;Example of edges series:

1 Label-A&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;1 2

2 Label-B&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;1 3

3 Label-C&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;1 6

4 Label-A&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;3 5

5 Label-A&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;4 6

6 Label-C&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;5 3

The series can be provided through the web interface or loading two separated files. Into files the same format must be used.

# How use SuperNoder 
The interface of Supernoder allows to directly add nodes and edges or load them from files.
The user can:
* Select the size of motifs that will be looked for in the network.
* Select the heuristic to find disjoint motifs. See the paper for heuristics details.
* Select the type of the network.
* Select a threshold to indicate how many times a motif must appear to be considered over-represented.
* Select the number of iterations SuperNoder must perform building a hierarchy of networks.
* Select how many times the heuristic h1 should be performed.
* Select the size of samples used by heuristics h4 and h5.

# How to read the Output
SuperNoder returns series of nodes and edges using the same format of input. If the selected number of iterations is greater than 1 more series will be returned.

In the series of output nodes, each supernode has as label the concatenation of labels of its source nodes, and the list of nodes that compose it. Supernodes are indicated by #supernode.

An output example

Network after 1 iteration(s)

NODES

4 A

5 A

6 A

7 A-B-C &emsp;[1 - 2 - 3] &emsp;#supernode

EDGES

5 7

6 7 

# Data
The folder networks contains the nodes and their labels of our mappings on taxonomies and the edges of experimented networks. The original networks are available in:
* food-web Florida bay: https://snap.stanford.edu/data/Florida-bay.html
* PPI yeast: http://vlado.fmf.uni-lj.si/pub/networks/data/bio/yeast/yeast.htm
* PPI arabidopsis: http://interactome.dfci.harvard.edu/A_thaliana/index.php?page=download

# Acknowledgements
They will be available after publication.