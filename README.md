**BER vs SNR for BPSK Over AWGN**

**Objective**

Compare analytical and simulated Bit Error Rate (BER) performance of Binary Phase Shift Keying (BPSK) over an Additive White Gaussian Noise (AWGN) channel using Monte Carlo simulation.

**BPSK Basics**

Binary Phase Shift Keying (BPSK) is the simplest digital modulation scheme where

* Bit 0 → Symbol \+1  
* Bit 1 → Symbol \-1

The transmission over an AWGN channel is modelled as

y = x + n

Where:

    x ∈ {−1, +1}  → Transmitted BPSK symbol  
    n ∼ N(0, σ²)   → Real-valued Gaussian noise


**Theoretical BER for BPSK**

The probability of bit error (BER) for BPSK in AWGN is given by:

 BER_BPSK = Q(√(2 * Eb / N0))

The Q-function represents the tail probability of the standard normal distribution:

Q(x) = 1/2 * erfc(x / √2)

The BER can also be expressed as:

BER_BPSK = 1/2 * erfc(√(Eb / N0))

**Simulation Method**

1. Generate random binary bits  
2. Map bits to BPSK symbols (0 → \+1, 1 → \-1)  
3. Add real-valued Gaussian noise based on given SNR  
4. Demodulate symbols using threshold detection  
5. Count bit errors to estimate BER  
6. Repeat for a range of SNR values

This is a **Monte Carlo simulation**, meaning large numbers of trials are used to approximate real-world error performance.

**Results:**

**![][image7]**

**Tools Used :**

* **Language**: Python  
* **Libraries**:  
  * NumPy — for signal and noise generation  
  * Matplotlib — for plotting BER curves  
  * SciPy — for computing the complementary error function (erfc)  
* **Platform**: Google Colab

**Author :**

**Mahendar Gajula**

**References**

* Proakis, *Digital Communications*, 5th Edition  
* Simon & Alouini, *Digital Communication over Fading Channels*
