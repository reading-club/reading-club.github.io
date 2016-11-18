---
layout: clubs-event
title:  "Flexible frequency control of cortical oscillations enables computations required for working memory"
subtitle: ""
speaker: "coldlikeabrain"
schedule: 2016-11-20 22:30:00, GMT+8
ref: 
  - http://www.pnas.org/content/110/31/12828.short
---


1. symbolism vs. connectionism Connectionism and Cognitive Architecture: A Critical Analysis1 
		
   Jerry A. Fodor and Zenon W. Pylyshyn 
   
2. working memory — like RAM in computer, act as a memory buffer, can write in/erase information, but also can block irrelevant information.
   1. magic number 7 — seems to be better described by symbolism
3. But this paper shows a recurrent network model that can function as working memory
4. Brain oscillation 
   1. ·From “Regulating Cortical Oscillations in an Inhibition-Stabilized Network” by Jadi and Sejnowski  
   
      ….During slow wave sleep, oscillations in delta (2–4 Hz) range are prominent [8]. In rodents, oscillations in the 4–7-Hz or theta range accompany exploration and the formation as well as retrieval of a spatial map of its environment [9]. Oscillations in the 30–80-Hz or gamma frequency range are associated with arousal, working memory [10], and attention [11]. During cognitive tasks in humans, sustained oscillations in the gamma range [12] are induced in the prefrontal cortex [13], and their power increases in proportion to the task load [14]. During sensory processing, gamma range power in LFPs recorded in the related sensory area of the cerebral cortex is significantly enhanced following stimulus onset [Fig. 1(a)] [15], [16]. Abnormal gamma oscillations are a hallmark of cognitive disorders such as schizophrenia [17], autism [18], and language-learning impairments [19]; in the frontal cortices of infants, reduced gamma range power predicts language and cognition deficits at five years of age [20]. 
5.  The model
    1. 100 quadratic I&F, 20% recurrently connected
    2. three parts of input: recurrent connection, sensory input, background oscillation, all in terms of delta pulse
    3. shows gamma - sustain activity/theta - block distractor/alpha - output activity
