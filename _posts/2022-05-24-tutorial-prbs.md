---
title: 'Tutorial: Physics-informed pseudo-random binary signal generation with python'
date: 2022-05-24
permalink: /posts/2022/05/prbs-tutorial/
tags:
  - PRBS
  - python
  - scipy
---

This script was used to automatically generate 24- and 48-hour binary signals for our paper *Design of a short perturbation method for on-site estimation of a building envelope thermal performance* (2022).

From timestep, char_time and duration, this code builds a custom binary signal. The advantage with these 3 variables is to deal with physcially relatable values.

```python
from scipy.signal import max_len_seq

# binary signal time-step
timestep = 5  #min

# characteristic times of the signal
char_time = [14,6,5]  #hours

# wanted duration of the signal
duration = 48  #hours

taps = [int(i * 60 / timestep) for i in char_time]
# on fixe nbits au amx des temps caractéristiques
nbits = max(taps)

# Nota : the second element returned by max_len_seq is not useful for our purpose
signal, _ = max_len_seq(nbits=nbits,
                        taps=taps,
                        length=duration)
```
   
Do you know a more elegant method to generate physics-informed binary signals ? Let me know !

