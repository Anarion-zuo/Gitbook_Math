# Information Theory

##  Entropy

$$
S=k\ln W=k\ln2\log_2W
$$

$W$ is the number of microscopic states/configuration, complexions according to Plank’s words. $\log_2W​$ is the amount of information. Information is change in entropy. Entropy is the information we do not have. When we find something out about a system, the entropy gets less. For people having different amount or kinds of information towards a certain system, entropy of the system is different for them.

In thermal dynamics, temperature is defined by the change in entropy relative to the change in inner energy.
$$
\frac{1}{T}=\frac{\partial S}{\partial E}
$$
where change in energy is defined by heat and heat is derived from the heat capacity.
$$
C=\frac{\partial T}{\partial E}=-T^2\frac{\partial^2S}{\partial E^2}
$$
There are systems holding negative heat capacity, gravitational systems, for example. In a gravitational system, as in all other kinds of classic physics systems, there is a certain relation between the kinetic energy and potential energy.
$$
\bar{E_k}=-\frac{1}{2}\bar{E_U},E=-E_k\propto NT
$$
Thereby gives negative heat capacity. In a galaxy, when taking away some planets, the other planets get closer to the center and move faster than before, thus increases the total kinetic energy.

Code is a systematic way of representing information.

## Compression

## Introduction

### Fundamental Problem

Shannon: Reliable Communication over unreliable channel. Received signal is not identical to the transmitted signal. We would like communication system to have received message is exactly same as the transmitted one.

- Physical solutions. Create a low noise environment for the transmission.
- System solutions. Accept the existence of potential noises and build encode and decode rules to eliminate them, thus transform unreliable channel to a reliable channel.

### Binary Symmetric Channel

Input signals can be 0 or 1, as also for output signals.
$$
P(y=0|x=0)=1-f,P(y=1|x=0)=f
$$
where $f$ is the probability of mistakes.
$$
Ey=nf,Dy=nf(1-f)
$$

### Repetition Encoding

For a file of binary content, as for all files in computers, we apply the repetition encoding method, which is simply replicate the binary bits for 3 times. 0 becomes 000 and 1 becomes 111. The number of repetition can be otherwise. Some of the bits of the received codes may differ from the encoded version, due to the existence of noise. The decoder follows the idea of voting. Namely, for each 3 bits in the received code, take the figure having maximum frequency of appearance as decoded result for the 3 bits.

Suppose the source binary code is represented as vector $s$, encoded code is $t$, noise is $n$, received code is $r$, decoded code is $\hat s$.
$$
r=t\oplus n\mod2
$$
​                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    Apply the Bayes formula upon the repetition encoding system:
$$
P(r|s=0)=f\times f\times(1-f),P(r|s=1)=f\times(1-f)\times(1-f)
$$
For all of the bits:
$$
P(\hat s\ne s)=f^3+3f^2(1-f)=3f^2-2f^3<f
$$
According to the probability theory, any single mistake can be detected and corrected, while more than one mistake is impossible to detect. Therefore, for repetition encoding model, we have a clear boundary of the tolerable number of mistakes and the number is achievable, for terminology.

Generally, according to Shannon, the curve describing the boundary of achievability ex