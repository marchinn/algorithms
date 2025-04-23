# Fast exponentiation algorithm

The fast exponentiation algorithm helps to quickly compute large powers of numbers without overloading memory. That's how it looks in python:
```python
def mod_pow(base, exponent, modulus):
    result = 1
    base %= modulus
    while exponent > 0:
        if exponent % 2 == 1:
           result = (result * base) % modulus 
        base = (base * base) % modulus
    return result 
```
Firstly, start with smallest power: *result = 1*

Lower the degree so it can't grow too fast: *base %= modulus*

Then go to the loop that will continue computing *while the exponent is greater than 0*:
1. Check if exponent is odd
2. If it is, assign result value to *result raised to the power of base mod modulus*
3. Then assign the base to *base raised to the power of itself*. The loop will repeat if the exponent is still greater than 0; if it is not, the function will return the result
