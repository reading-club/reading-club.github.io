---
layout: clubs-event
title:  "Is cortical connectivity optimized for storing information? "
subtitle: "Is brain optimal for information storage?"
speaker: "ErbB4"
date:   2016-10-30
schedule: 2016-10-30 22:00:00, GMT+8
ref: 
  - http://www.nature.com/neuro/journal/v19/n5/full/nn.4286.html
---



* ToC
{:toc}



Here is the [Original and Updated Notes](http://hanlu.io/blog/is-brain-optimal-for-information-storage/).

# Topic of interest

Intuition: brain should be **fully** connected, for its highly condensed property and interaction of collaterals.

Empirical evidence: brain is **sparsely** connected, with a connection probability of $10\%$ in neocortex.

Question concerned: is the sparse connection an optimal setting (for information storage)?

# Two hypotheses of information storage in the brain

### attractor state in a recurrent network

A small group of neurons have higher firing rates compared to background activity.

This is also a widely-accepted mechanism in feedback network (recurrent network).

<figure markdown="1">
![]({{ site.baseurl }}/assets/posts/is-brain-optimal-for-information-storage/memory-engram.png)
<figcaption>An illustration of memory engram. The memory of this context is stored by the blue colored neurons.</figcaption>
</figure>

### firing sequences in a feedforward network
It is also confirmed that the signal could be stored in the network in the form of firing sequences of a few neurons in a feedforward network.

<figure markdown="1">
![]({{ site.baseurl }}/assets/posts/is-brain-optimal-for-information-storage/feedforward.png)
<figcaption>In a feedforward network, the neurons never project back.</figcaption>
</figure>

The feedforward network could present (or save) information, because the neuron (or unit network) at different stage has different response time constant.

<figure markdown="1">
![]({{ site.baseurl }}/assets/posts/is-brain-optimal-for-information-storage/feed.png)
<figcaption>When receiving an input, the neurons at different stage have different time delay (and response amplitude). To maintain the same response level, the synaptic weight should increase with stage increases. </figcaption>
</figure>

# Motivation from models to connection style

Current numerical research usually starts from a specific connection pattern, It is unclear whether cortical connectivity obeys the rules postulated by these models.

### learning algorism
So current study started from a possibly fully connection state, using **perceptron learning algorism** to classify total inputs (determine outputs). Patterns to be learned determined the synaptic weights space.

<figure markdown="1">
![]({{ site.baseurl }}/assets/posts/is-brain-optimal-for-information-storage/perceptron.png)
<figcaption>In this illustration, the threshold ($T$) plus a robustness parameter $K$ determined the constrains to the newtrok.</figcaption>
</figure>

### network setting

simplified neuron model: binary ($S_j = 1$  is active, $S_j = 0$ is inactive)

neuron type: excitatory neurons and inhibitory neurons.

connections: Inhibitory neurons are fully connected and not touched during the learning process. Excitatory neurons are possibly fully connected.

### learned patterns and synaptic weights

In the current study, different firing patterns are randomly generated and presented to the network, and the network has to learn (or store) the pattern with sets of synaptic weights.

<figure markdown="1">
![]({{ site.baseurl }}/assets/posts/is-brain-optimal-for-information-storage/pattern.png)
<figcaption>In this example, a network of four neurons has to learn the pattern '1010'. So the connections between neuron $1$ and neuron $3$ is higher, with larger diameter of the circle.</figcaption>
</figure>

### synaptic integration and perceptron classification

Neurons are connected with different strength, $w_{ij}$ is the synaptic weight from neuron $j$ to neuron $i$.

The synaptic inputs to each neuron is summed and compared to a threshold $T$.

$$
\sum_\mathrm{1,...,N}w_{ij}S_j(t),
$$

where $S_j$ is the activity of input neuron and $w_{ij}$ is the corresponding weight.



If $\sum_\mathrm{1,...,N}w_{ij}S_j(t)>T+K$, fire;

if $\sum_\mathrm{1,...,N}w_{ij}S_j(t)<T-K$, silence.

# What are the network connections when the number of learned patterns reaches maximum?

### dominant weak synapses

In the synaptic weight distribution, there are more weak synapses and less strong synapses, which also fits the experimental evidence. (Simulation results absed on attractor state hypothesis.)

<figure markdown="1">
![]({{ site.baseurl }}/assets/posts/is-brain-optimal-for-information-storage/weight-distribution.png)
<figcaption>In $c$, EPSP amplitude is an representation of synaptic weight.</figcaption>
</figure>

### reciprocal connections are stronger

The stronger connections are reciprocal connections. The probability of reciprocal connections are above the square of connection probability. (Simulation results absed on attractor state hypothesis.)

<figure markdown="1">
![]({{ site.baseurl }}/assets/posts/is-brain-optimal-for-information-storage/reciprocal-connections.png)
<figcaption>In $d$, EPSP amplitude is an representation of synaptic weight.</figcaption>
</figure>

### reciprocal connections in sequence hypothesis
The same phenomenon of higher reciprocal connection probability was also observed when simulating the sequence hypothesis of information storage. But the probability equals to the squared probability of connection probability.

<figure markdown="1">
![]({{ site.baseurl }}/assets/posts/is-brain-optimal-for-information-storage/sequence-bi.png)
<figcaption>All black lines: results of attractor state simulation. Orange line: results of sequence simulation.</figcaption>
</figure>

# Take-home-message and discussion

**Conclusion**  The sparely connected network with stronger reciprocal connections make the brain efficient for information storage.

**Discussion**

How to realize the function of memory in ANN?

Use tempotron learning algorism?
<figure markdown="1">
![]({{ site.baseurl }}/assets/posts/is-brain-optimal-for-information-storage/tempotron.png)
</figure>

The function of "potential" (zero) synapses.


# References
[picture of memory engram is modified from this one](http://images.google.de/imgres?imgurl=https%3A%2F%2Fmopapersmoproblems.files.wordpress.com%2F2013%2F08%2Fthingaboutredplace.png&imgrefurl=https%3A%2F%2Fmopapersmoproblems.wordpress.com%2Fcategory%2Fspecial-blog-post%2F&h=899&w=1446&tbnid=Pvf3VgLxOqfw9M%3A&docid=8xz2O0-5qrXhKM&ei=pwkVWKraBYLxUoPhh8gJ&tbm=isch&iact=rc&uact=3&dur=331&page=1&start=18&ndsp=27&ved=0ahUKEwjqyaeU8IDQAhWCuBQKHYPwAZkQMwg-KBowGg&bih=654&biw=1517)

[Goldman MS. Memory without feedback in a neural network. Neuron. 2009 Feb 26;61(4):621-34.](http://www.sciencedirect.com/science/article/pii/S0896627308010830)

[Gütig R, Sompolinsky H. The tempotron: a neuron that learns spike timing–based decisions. Nature neuroscience. 2006 Mar 1;9(3):420-8.](http://www.nature.com/neuro/journal/v9/n3/full/nn1643.html)

[Brunel N. Is cortical connectivity optimized for storing information [quest]. Nature neuroscience. 2016 Apr 11.](http://utmemoryclub.com/wp-content/uploads/2013/07/brunel2016.pdf)
