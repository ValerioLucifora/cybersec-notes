# 19 — Binary Math

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-02

---

## Definition of the Binary System

The binary system is a numbering system that uses only two digits: **0** or **1**. In computing, each of these digits is called a **bit**. When **eight bits** are grouped together, they form a **byte**, which is also often referred to as an **octet** in the context of networking.

## The Importance of the Binary System

Knowing how to convert numbers between decimal and binary is a fundamental skill for understanding **IP subnetting**, which will be a central topic in the study of networking.

---

## The Conversion Table

### How to create the table

To perform conversions, you need to create a reference table starting from right to left:

1. Begin by writing the number **1** on the far right.
2. Double the previous number as you move to the left: **2, 4, 8, 16, 32, 64, 128**.
3. Although for an octet you stop at 128, the table can be extended indefinitely (256, 512, etc.) to calculate larger binary numbers.

### Relationship to powers of two

The values in the table correspond to the **powers of two**:

- 20=1
- 21=2
- 22=4
- ...and so on up to 27=128.

---

## Converting from Binary to Decimal

### Calculation procedure

To convert a binary number to decimal, align the binary number under the conversion table:

- For each binary **0**, place a **0** in the calculation row.
- For each binary **1**, place the **corresponding value** from the table.
- Finally, add up all the numbers obtained to get the final decimal value.

### Practical examples

- **00000010:** Only the column for "2" has a 1, so the result is **2**.
- **10000010:** Add the values of the columns with a 1 (128 + 2), resulting in **130**.
- **11111111:** All columns have a 1. Adding 128+64+32+16+8+4+2+1 gives the maximum value of an octet, which is **255**.

---

## Converting from Decimal to Binary

### The comparison method

To convert a decimal number (e.g., **154**) to binary, proceed from left to right by comparing the number with the values in the table:

1. **Comparison:** Is the table value (e.g., 128) less than or equal to the number we are converting?
2. **If yes:** Write **1** in the column and subtract the table value from the total (or keep track of the accumulated sum).
3. **If no:** Write **0** and move to the next column.

Example: Convert 154

- 128 is ≤ 154? Yes → **1** (remainder 26).
- 64 is ≤ 26? No → **0**.
- 32 is ≤ 26? No → **0**.
- 16 is ≤ 26? Yes → **1** (remainder 10).
- 8 is ≤ 10? Yes → **1** (remainder 2).
- 4 is ≤ 2? No → **0**.
- 2 is ≤ 2? Yes → **1** (remainder 0).
- 1 is ≤ 0? No → **0**.
- **Result:** 154 in decimal corresponds to **10011010** in binary.

---

## Bit Capacity and Possible Results

Increasing the number of bits exponentially increases the number of combinations and the maximum decimal value achievable:

- **2 bits:** 4 possible combinations (00, 01, 10, 11), corresponding to decimals 0, 1, 2, and 3.
- **3 bits:** 8 combinations.
- **4 bits:** 16 combinations.
- **8 bits (1 octet):** allows representation of any number between **0 and 255**.
