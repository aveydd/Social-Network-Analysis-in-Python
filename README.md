# Social-Network-Analysis-in-Python
Networks today are part of our everyday life. Let's see how to visualize and understand a social network in Python using Networks. If you want to learn about Network Analysis,  Networks are everywhere, networks of roads, a network of friends and followers on social media, and a network of office colleagues. They are playing a significant role in our day to day lives from spreading useful information to influencing national elections. The ability to analyze these networks and make informed decisions based on them is a skill that is important for any data analyst.  The focus of this tutorial is to teach social network analysis (SNA) using Python and NetworkX, a Python library for the study of the structure, dynamics, and functions of complex networks. This tutorial assumes that the reader is familiar with the basic syntax of Python, no previous knowledge of SNA is expected.

# Introduction
Let us first start with what do we mean by Social Networks. Below you see a network of Bollywood actors as nodes. They are connected with solid lines if they have worked together in at least one movie.

So, we can see that both Amitabh Bachchan and Abhishek Bachchan have acted with all the actors in the network, while Akshay Kumar has worked with only two Bachchans. 

This too is a social network. Any network with connections between individuals, where the connections capture the relationship between them is a social network. Analyzing these networks can give us great insight about the people in the network like who are real influencers, who are most connected, etc.

Each network consists of: Nodes: The individuals whose network we are building. Actors in the above example.
Edges: The connection between the nodes. It represents a relationship between the nodes of the network. In our example, the relationship was that the actors have worked together.

# Creating a network using NetworkX
There are many types of networks. We will use NetworkX to develop and analyze these different networks. To start, you will need to install networkX: You can use either:

pip install networkx
or if working in Anaconda

conda install -c anaconda networkx
This will install the latest version of networkx. The codes in this tutorial are done on Python=3.5, NetworkX = 2.0 version.

# Symmetric Networks
The first network of actors that we created above is a symmetric network because the relationship "working together in a movie" is a symmetric relationship. If A is related to B, B is also related to A. Let us create the network we saw above in NetworkX.

We will be using the Graph() method to create a new network and add_edge() to add an edge between two nodes.

# Asymmetric Networks
What if the relationship between nodes is 'child of', then the relationship is no longer symmetric. If A is the child of B, then B is not a child of A. Such a network where the relationship is asymmetric (A is related to B, does not necessarily means that B is associated with A) is called an Asymmetric network. We can build the asymmetric network in NetworkX using DiGraph method, which is short of Directional Graph. Let us make an asymmetric graph.

# Weighted Networks
Till now we had networks without weights, but it is possible that networks are made with weights, for example, if in our initial network we consider the number of movies done together as a weight, we will get a Weighted Network. Let us make one again of the actors, but this time we add weight to the network, each edge has a weight signifying the number of movies they have done together.

# Multigraph
We can give different attributes to the edges. For example, we can define a relation of neighbor between two nodes 'A' and 'B' using relation attribute. If within a network two nodes are connected with two different edges (relations) we have a multigraph. We can make a multigraph utilizing the MultiGraph class.

# Network Connectivity
Now the network is made, can we know more about a particular node in the network? Well yes, let us explore some of them.

Degree
Degree of a node defines the number of connections a node has. NetworkX has the function degree which we can use to determine the degree of a node in the network.

# Clustering Coefficient
It is observed that people who share connections in a social network tend to form associations. In other words, there is a tendency in a social network to form clusters. We can determine the clusters of a node, Local Clustering Coefficient, which is the fraction of pairs of the node's friends (that is connections) that are connected with each other. To determine the local clustering coefficient, we make use of nx.clustering(Graph, Node) function.

# Network Influencers
Above we learned some of the network distance measures, they are useful in knowing how the information will spread through the network. In this section, we will learn how to find the most important nodes (individuals) in the network. These parameters are called as centrality measures.

Remember that popular girl from your high school or the schools top baseball player. These were the people who had the power to make your high school experience hell or heaven. What gave them this power? Centrality Measures can help us in identifying popularity, most liked, and biggest influencers within the network.

# Degree Centrality
The people most popular or more liked usually are the ones who have more friends. Degree centrality is a measure of the number of connections a particular node has in the network. It is based on the fact that important nodes have many connections. NetworkX has the function degree_centrality() to calculate the degree centrality of all the nodes of a network.

# Eigenvector Centrality
It is not just how many individuals one is connected too, but the type of people one is connected with that can decide the importance of a node. In Delhi Roads whenever the traffic police capture a person for breaking the traffic rule, the first sentence that traffic police hears is "Do you know whom I am related to?".

Eigenvector centrality is a measure of exactly this. It decides that a node is important if it is connected to other important nodes. We can use the eigenvector_centrality() function of NetworkX to calculate eigenvector centrality of all the nodes in a network.

The Google's Pagerank algorithm is a variant of Eigenvector centrality algorithm.

# Betweenness Centrality
The Betweenness Centrality is the centrality of control. It represents the frequency at which a point occurs on the geodesic (shortest paths) that connected pair of points. It quantifies how many times a particular node comes in the shortest chosen path between two other nodes. The nodes with high betweenness centrality play a significant role in the communication/information flow within the network. The nodes with high betweenness centrality can have a strategic control and influence on others. An individual at such a strategic position can influence the whole group, by either withholding or coloring the information in transmission.

Networkx has the function betweenness_centrality() to measure it for the network. It has options to select if we want betweenness values to be normalized or not, weights to be included in centrality calculation or not, and to include the endpoints in the shortest path counts or not.

# Combining it all.
Let us start with the Facebook data, for our analysis here we will use Facebook combined ego networks dataset, it contains the aggregated network of ten individuals’ Facebook friends list. You can download the required facebook_combined.txt file from the Stanford University site.

You can get your own Facebook/Twitter data using the Facebook/Twitter APIs. Look forward to the next forthcoming tutorial where we will learn how to use Facebook and Twitter APIs to get data and use the information acquired here to analyze it.
