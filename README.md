# Social-Network-Analysis-in-Python
Networks today are part of our everyday life. Let's see how to visualize and understand a social network in Python using Networks. If you want to learn about Network Analysis,  Networks are everywhere, networks of roads, a network of friends and followers on social media, and a network of office colleagues. They are playing a significant role in our day to day lives from spreading useful information to influencing national elections. The ability to analyze these networks and make informed decisions based on them is a skill that is important for any data analyst.  The focus of this tutorial is to teach social network analysis (SNA) using Python and NetworkX, a Python library for the study of the structure, dynamics, and functions of complex networks. This tutorial assumes that the reader is familiar with the basic syntax of Python, no previous knowledge of SNA is expected.

Introduction
Let us first start with what do we mean by Social Networks. Below you see a network of Bollywood actors as nodes. They are connected with solid lines if they have worked together in at least one movie.

So, we can see that both Amitabh Bachchan and Abhishek Bachchan have acted with all the actors in the network, while Akshay Kumar has worked with only two Bachchans. Interesting right!

This too is a social network. Any network with connections between individuals, where the connections capture the relationship between them is a social network. Analyzing these networks can give us great insight about the people in the network like who are real influencers, who are most connected, etc.

Each network consists of: Nodes: The individuals whose network we are building. Actors in the above example.
Edges: The connection between the nodes. It represents a relationship between the nodes of the network. In our example, the relationship was that the actors have worked together.

Creating a network using NetworkX
There are many types of networks. We will use NetworkX to develop and analyze these different networks. To start, you will need to install networkX: You can use either:

pip install networkx
or if working in Anaconda

conda install -c anaconda networkx
This will install the latest version of networkx. The codes in this tutorial are done on Python=3.5, NetworkX = 2.0 version.

Symmetric Networks
The first network of actors that we created above is a symmetric network because the relationship "working together in a movie" is a symmetric relationship. If A is related to B, B is also related to A. Let us create the network we saw above in NetworkX.

We will be using the Graph() method to create a new network and add_edge() to add an edge between two nodes.

Asymmetric Networks
What if the relationship between nodes is 'child of', then the relationship is no longer symmetric. If A is the child of B, then B is not a child of A. Such a network where the relationship is asymmetric (A is related to B, does not necessarily means that B is associated with A) is called an Asymmetric network. We can build the asymmetric network in NetworkX using DiGraph method, which is short of Directional Graph. Let us make an asymmetric graph.

Weighted Networks
Till now we had networks without weights, but it is possible that networks are made with weights, for example, if in our initial network we consider the number of movies done together as a weight, we will get a Weighted Network. Let us make one again of the actors, but this time we add weight to the network, each edge has a weight signifying the number of movies they have done together.
