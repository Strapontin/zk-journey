# Math Prerequisites Exercises

## GCD and LCM calculations

For Q1 and Q2, I computed $gcd(a, b)$ by running by hand the following algorithm:

```python
def gcd(a: int, b: int) -> int:
    return gcd(b, a % b) if b != 0 else a
```

Then, I computed the lcm by doing the following: $lcm(a, b) = ab / gcd(a, b)$

### Q1 - Compute gcd(48, 180) and lcm(48, 180)

$$gcd(48, 180)$$
$$= gcd(48, 180 \% 48)$$
$$= gcd(36, 48 \% 36)$$
$$= gcd(12, 36 \% 12)$$
$$= gcd(12, 0)$$
$$= 12$$

$$lcm(48, 180)$$
$$= 48 \cdot 180 / gcd(48, 180)$$
$$= 8640 / 12$$
$$= 720$$

### Q2 - Compute gcd(84, 67) and lcm(84,67)

$$gcd(84, 67)$$
$$= gcd(67, 84 \% 67)$$
$$= gcd(17, 67 \% 17)$$
$$= gcd(16, 17 \% 16)$$
$$= gcd(1, 16 \% 1)$$
$$= 1$$

$$lcm(84, 67)$$
$$= 84 \cdot 67 / gcd(84, 67)$$
$$= 5628 / 1$$
$$= 5628$$

### Q3 - Using prime factorization, find gcd(360, 840) and lcm(360, 840). Confirm the result by asserting $ab = gcd(a, b) \cdot lcm(a,b)$

$$2 | 360 \implies 360/2 = 180$$
$$2 | 180 \implies 180/2 = 90$$
$$2 | 90 \implies 90/2 = 45$$
$$3 | 45 \implies 45/3 = 15$$
$$3 | 15 \implies 15/3 = 5$$
$$360 = 2^3 \cdot 3^2 \cdot 5$$

$$2 | 840 \implies 840/2 = 420$$
$$2 | 420 \implies 420/2 = 210$$
$$2 | 210 \implies 210/2 = 105$$
$$3 | 105 \implies 105/3 = 35$$
$$5 | 35 \implies 35/5 = 7$$
$$840 = 2^3 \cdot 3 \cdot 5 \cdot 7$$

Then, calculating $gcd(360, 840)$ is similar to doing an intersection on both prime factorization:

- 360 = 2³ · 3² · 5
- 840 = 2³ · 3¹ · 5 · 7

Common primes are 2, 3 and 5. For each common prime, we keep the smaller exponent from the intersection:

$$2^3 \cdot 3 \cdot 5$$
$$gcd(360, 840)=120$$

Calculating $lcm(360, 840)$ is similar to doing an union on both prime factorization:


- 360 = 2³ · 3² · 5
- 840 = 2³ · 3¹ · 5 · 7

For each prime, we keep the bigger exponent:

$$2³ \cdot 3² \cdot 5 \cdot 7$$
$$lcm(360, 840)=2520$$
