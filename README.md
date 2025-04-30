# EXP.NO.6-Simulation-of-Hamming-and-Shannon-Fano-Code
6. Simulation of Huffman and Shannon-Fano Code.

# AIM
```
To study and verify the simulation of Huffman and Shannon-Fano Code.
```

# SOFTWARE REQUIRED
```
Colab software
```

# ALGORITHMS
```
Step 1: Initialization
Initialize:

L = 0 (to store average codeword length)

hs = 0 (to store entropy)

p[] = empty list to store probabilities

lk[] = empty list to store codeword lengths

var = 0 (to store variance)

Step 2: Input
Input number of samples n.

For each sample from 1 to n:

Input the probability p[i], append to list p.

For each sample from 1 to n:

Input the codeword length lk[i], append to list lk.

Step 3: Calculate Average Codeword Length (L)
For each symbol i from 0 to n-1:

Multiply p[i] * lk[i] and add to L.

Step 4: Calculate Entropy (hs)
For each symbol i from 0 to n-1:

Compute p[i] * log₂(1 / p[i]) and add to hs.

Round entropy hs to 3 decimal places.

Step 5: Calculate Efficiency (eff)
Compute eff = hs / L.

Round eff to 3 decimal places.

Step 6: Calculate Redundancy (red)
Compute red = 1 - eff.

Round red to 3 decimal places.

Step 7: Calculate Variance (var)
For each symbol i from 0 to n-1:

Compute p[i] * (lk[i] - L)² and add to var.

Round var to 3 decimal places.

Step 8: Output Results
Print:

Average Codeword Length L

Entropy hs

Efficiency eff

Redundancy red

Variance var
```

# PROGRAM
```
#Huffman and Shannon-Fano coding
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)
# Avg length of the code word
for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1
# Entropy
for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
# Efficiency
eff =  hs / L
eff = round(eff,3)
# Redundancy 
red =  round(1 - eff,3) 
# Variance
var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```

# OUTPUT
```
Enter the number of Samples : 4
Enter the probability of sample values 1: 0.2
Enter the probability of sample values 2: 0.1
Enter the probability of sample values 3: 0.3
Enter the probability of sample values 4: 0.4
Enter the length of the sample values 1: 1
Enter the length of the sample values 2: 2
Enter the length of the sample values 3: 3
Enter the length of the sample values 4: 4
Average Codeword Length is : 2.9
Entropy is : 1.846
Efficiency is : 0.637
Redudancy is : 0.363
Variance is : 1.29
``` 
# RESULT
```
Thus the simulation of Huffman and Shannon-Fano code is verified.
```
