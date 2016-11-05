---
layout: clubs-event
title:  "Popularity versus similarity in growing networks"
subtitle: ""
speaker: "OctoMiao"
schedule: 2016-11-06 22:00:00, GMT+8
ref:
  - http://www.nature.com/nature/journal/v489/n7417/abs/nature11459.html
---


## Background


Why are we interested in networks? Because a enormous categories of phenomena can be models using networks. Internet, society, physics, biology, ecology, economy, even the evolution of the universe.


### Concepts

* Degrees

<figure markdown="1">
![]({{ site.baseurl }}/assets/posts/popularity-similarity-in-networks/directed-degrees.svg.png)
<figcaption markdown="1">
Degrees. Source [wikipedia](https://en.wikipedia.org/wiki/File:DirectedDegrees.svg).
</figcaption>
</figure>


### Scaling in Networks

People have found a lot of scaling phenomena in networks.

* Internet links (directed links):

[arXiv:cond-mat/0008465](https://arxiv.org/abs/cond-mat/0008465) for the scaling in internet links. What they find is that the distribution of degrees is power-law, i.e., $P\propto k^{-\gamma}$ with $\gamma\sim 2$. [arXiv:cond-mat/0009090](https://arxiv.org/abs/cond-mat/0009090v1) provides a better explanation. The explanation is simply popular is more attractive.

* Barabasi et al found that in random networks, scaling appears also [^2].

<figure markdown="1">
![]({{ site.baseurl }}/assets/posts/popularity-similarity-in-networks/barabasi-scaling-random-networks.png)
<figcaption markdown="1">
Scaling of connectivities. Barabasi (1999).
</figcaption>
</figure>

* And some theories like [^3], etc.



### Popularity


In the example of internet links, popular is attractive can be models by a dynamic generation of network following some rules.

1. At each step we have $m$ links distributed.
2. The probability of attaching to some node with degree $k_i$ is

   $$P_i \sim  k_i + A$$

   where $A$ serves as a initial attractiveness since it tells us the probability of attachment when the degree $k_i=0$.

Dorogovtsev et al  proved that this model gives us the final distribution of degrees

$$
P \propto k^{-\gamma},
$$

where $\gamma=2 + A/m$ [^1].


### Similarity

The problem about popularity is that we are all aware that popularity is not the only factor.

Consider the following examples.

1. You write a blog about neuroscience. In the past people usually put links on the blog, which is called blogroll or something. In the links, what you would include is something like facebook, google, maybe nature/science, and most likely some blogs or resources about neuroscience eventhough these websites may not be very popular. However, these links have similar contents as yours.
2. We could also check the link you used in your articles and they are very likely to point to some websites that is also neuroscience.

In some cases similar is also important.



## Popularity and Similarity Together

What we would expect is that larger popularity and small similarity (more similar) are the preferable connections. Thus competitions between the two determines the overall connection probability.

To combine the two factors, we use the metric $\mathrm{Popularity}\times \mathrm{Similarity}$. Even though there is a competition between popularity and similarity, small values of $\mathrm{Popularity}\times \mathrm{Similarity}$ are more preferable connections, which takes similarity more seriously.

A simple model to demonstrate this is to build a space of disc. The radius is time $t$, while angles are the measure of similarity. A smaller angler distance indicates a smaller similarity. Using this mapping, we are able to show the dynamics of networks, since we can tell the history of the nodes.

Mathematically speaking, the similarity is measured as

$$
\begin{equation}
\theta_{ij} = \lvert \theta_i - \theta_j \rvert.
\end{equation}
$$

while time is the radius with $t=0$ at the center of the disc.


<figure markdown="1">
![]({{ site.baseurl }}/assets/posts/popularity-similarity-in-networks/disc-of-similarity.png)
<figcaption markdown="1">
Disc of similarity. This figures shows the measure of similarity. 2 & 3 are more similar, given the fact that their angular distance $\lvert\theta_2-\theta_3\rvert$ is smaller that either $\theta_2-\theta_1$ or $\lvert\theta_3-\theta_1\rvert$. Papadopoulos et al (2012).
</figcaption>
</figure>


Now we are going to dynamically generate a network. The updating rules are listed bellow.

1. We create a node at each time step and label them with numbers. For example, node 3 means it was created at time step 3. We denote the time of the $i$th node as $t_i$ and its angle on the disc as $\theta_i$.
2. As the node $i$ is created at time $t_i$, it is connected to $m$ previous nodes.
3. The node $i$ is connected to node $j$'s if $t_j\theta_{ij}$ are the smallest. In this measure $t_j$ is the popularity of node $j$ and $\theta_{ij}$ is the similarity of the two nodes.

<figure markdown="1">
![]({{ site.baseurl }}/assets/posts/popularity-similarity-in-networks/disc-popularity-similarity.png)
<figcaption markdown="1">
Illustration of the disc model. The radial coordinate measure the creation time of the node, while the angular distance measures the similarity.
</figcaption>
</figure>


**The key transformation of this problem** is to define a new radial coordinate system $r =\ln t$, so that the distance becomes log scale. Then we define the disc to be on a hyperbolic space so that the distance between any two points is calculated as

$$
x_{ij} = r_i + r_j + \ln (\theta_{ij}/2) = \ln(t_i t_j \theta_{ij}/2).
$$

Minimizing $x_{ij}$ becomes equivalent to minimizing $t_j \theta_{ij}/2$ when dealing with the connectivity from a new born node $i$. **The competition between popularity and similarity is simply the minimization of distance between two nodes on a hyperbolic plane.**


Why is this definition of distance superior than the previous measure of $\mathrm{Popularity}\times \mathrm{Similarity}$? Because the universe/nature itself measures distance on hyperbolic space, i.e., Minkowski space.



## References and Notes

[^1]: [arXiv:cond-mat/0009090](https://arxiv.org/abs/cond-mat/0009090v1).
[^2]: Barabási, A.-L., & Albert, R. (1999). [Emergence of Scaling in Random Networks. Science, 286(5439), 509–512.](http://doi.org/10.1126/science.286.5439.509)
[^3]: Krapivsky, P. L., Redner, S., & Leyvraz, F. (2000). [Connectivity of growing random networks. Physical Review Letters, 85(21), 4629–4632.](http://doi.org/10.1103/PhysRevLett.85.4629)
