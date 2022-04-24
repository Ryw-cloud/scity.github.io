## Co-channel cells and Co-channel interference

### Basics

To introduce how to increase communication efficiency in cellular network, some definitions are first to be introduced. 

**Co-channel cells** : Cells having the same number in the adjacent cluster and using the same set of RF channels. The distance between the cells using the same frequency should be sufficient to keep the co-channel interference to an acceptable level, to maintain the quality of the signal.

**RF protection ratio**: The minimum value of wanted vs. unwanted signal ratio, usually expressed in decibels at the receiver input, determined under specified conditions such that a specific reception quality is achieved at the receiver output.

**RF reuse distance**: To avoid the Interference cells that use the same set of channels or frequencies are separated from one another by a larger distance. The distance between any two co-channels cells can be calculated by the following formula:
$$
D=D_I + D_S = D_I +r_0
$$
**RF reuse coefficient**: The ration of RF reuse distance and cell radius.
$$
Q = \frac{D}{r_0} = 1+\frac{D_I}{r_0}
$$

### Calculation

#### **Locating co-channel cells**

$$
N = i^2 + ij + j^2, \text{where } i \ge 0, j \ge 0, i+j \gt 1
$$

![image-20220424185419790](C:\Users\rywsh\AppData\Roaming\Typora\typora-user-images\image-20220424185419790.png)

1. Travel j cells vertically.
2. Rotate 60 degrees counterclockwise, and travel i cells.

#### Calculating distance

$$
D = \sqrt{i^2+ij+j^2}  \cdot  2R', R' = \frac{\sqrt{3}}{2}R\\
Q = \frac{D}{R} = \sqrt{3N}\\
D = \sqrt{3N} \cdot R
$$

From the calculation listed before, it is trivial to see:

- The larger N is, the larger distance is between co-channel cells, the more robust the network is under co-channel inference.
- The larger N is, the fewer frequency reuse the network applies.

Under the premise that enough communication quality is secured (sufficient RF protection ratio), a network should keep N as small as possible to lead to better frequency reuse, which is more efficient.

 #### System capacity

**Expression**:
$$
C_T = \beta L = \frac{N_s}{N}L
$$
From the expression, we can find that co-channel interference is an important limit to system capacity. Larger distance between co-channel cells which decreases co-channel interference will influence negatively to the system capacity.

#### The relationship between co-channel interference and system capacity

We can combine formulas we derived from former discussion, to see the relationship between system capacity and co-channel interference.
$$
\begin{align*}
\begin{split}
\left \{
\begin{array}{ll}
    C_T = \beta L = \frac{N_s}{N}L\\
    Q = \frac{D}{R} = \sqrt{3N}\\
    \frac{S}{I}=\frac{Q^n}{k}\\
\end{array}
\right.
\end{split}
\end{align*}
$$
We can derive the result:
$$
C_T = \frac{3N_s}{(kS/I)^{\frac{2}{n}}} L
$$

## Solution

### Plot fission

The size and capacity of different cells in the network will vary with the increase of urban construction and the increasing users, and the increase of regional users. Within the user's geographical scope, the cell planning is small, or the cell will change the direction of the omnidirectional coverage of the base station in the cell. Coverage increases the number of frequency channels allocated to each cell to meet the large-scale demand. This technology is called cell organization. Keep the size of the whole region unchanged, we decrease the radius of the plot.

![image-20220424203617167](C:\Users\rywsh\AppData\Roaming\Typora\typora-user-images\image-20220424203617167.png)

The method decrease the switching between base stations while increases the capacity.

### Cell sectoring (SDMA)

**SDMA** - Space division multiple access

Cell sectoring is used to increase the cellular system capacity through reducing the co-channel interference. Traditional sectoring is fixed sectoring with 3 or 6 sectors and identical sector size. It is efficient to mitigate the interference in case of uniform traffic in a cell. 

The traditional way to divide sectors is to use **directional antenna**. Co-channel interference can be decreased depending on co-channel plots. When N = 7, co-channel cells' number decreases to 2 from 6.
$$
\text{undirectional: }\frac{3N_s}{(6S/I)^{\frac{2}{n}}} L \\
\text{directional: }\frac{3N_s}{(2S/I)^{\frac{2}{n}}} L
$$

## Increase Capacity in 5G Network 

### Frequency challenge in 5G network

With signal transmitting with larger and larger frequency, the transmitting distance will be more limited. For example, 4G LTE mainly applies 1.8-1.9GHz and 2.3-2.6GHz, while 5G NR mainly uses 3.4-3.6GHz and 4.7-4.9GHz.
