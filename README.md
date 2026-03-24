# Digital-Signature
# Aim: 
To write a C program to implement the signature scheme named digital signature standard (Euclidean Algorithm).

# Algorithm:
STEP-1: Alice and Bob are investigating a forgery case of x and y.

STEP-2: X had document signed by him but he says he did not sign that document digitally.

STEP-3: Alice reads the two prime numbers p and a.

STEP-4: He chooses a random co-primes alpha and beta and the x’s original signature x.

STEP-5: With these values, he applies it to the elliptic curve cryptographic equation to obtain y.

STEP-6: Comparing this ‘y’ with actual y’s document, Alice concludes that y is a forgery.
# Program:
```
#include <stdio.h>

// Euclidean Algorithm for GCD
int gcd(int a, int b) {
    while (b != 0) {
        int t = b;
        b = a % b;
        a = t;
    }
    return a;
}

// Check if two numbers are co-prime
int isCoprime(int a, int b) {
    return gcd(a, b) == 1;
}

int main() {
    int p, a;
    printf("Enter two prime numbers p and a: ");
    scanf("%d %d", &p, &a);

    int alpha, beta;
    printf("Enter two numbers alpha and beta (should be co-prime to p): ");
    scanf("%d %d", &alpha, &beta);

    // Check if alpha and beta are co-prime with p
    if (!isCoprime(alpha, p) || !isCoprime(beta, p)) {
        printf("Error: alpha and beta must be co-prime to p.\n");
        return 1;
    }

    int x, y_document;
    printf("Enter x's original signature (x): ");
    scanf("%d", &x);
    
    // Simulate signature generation using a mock ECC-style equation
    int y_computed = (alpha * x + beta) % p;
    printf("Computed y from signature: %d\n", y_computed);

    printf("Enter the y value from the document: ");
    scanf("%d", &y_document);

    if (y_computed == y_document) {
        printf("Signature is valid. No forgery detected.\n");
    } else {
        printf("Forgery detected! Signature does not match.\n");
    }

    return 0;
}
```
# Output:
![Screenshot 2025-05-26 184905](https://github.com/user-attachments/assets/70a0042e-86e5-4575-9ff3-10438a8ae7cf)


# Result: 
Thus,the implement the signature scheme named digital signature standard is executed successfully.
