# Task 1 Solutions

## Question 1: Mega Data Type

The CPU has a maximum addressable width of **2 bytes = 16 bits**.

So the **mega data type = 16 bits**.



## Question 2: C++ Namespaces Program

```cpp
#include <iostream>
using namespace std;

namespace IntMath {
    int sum(int a, int b) {
        return a + b;
    }
}

namespace LongMath {
    long sum(long a, long b) {
        return a + b;
    }
}

int main() {
    int intResult = IntMath::sum(10, 20);
    long longResult = LongMath::sum(1000000L, 2000000L);

    cout << "IntMath::sum(10, 20) = " << intResult << endl;
    cout << "LongMath::sum(1000000, 2000000) = " << longResult << endl;

    return 0;
}


**Output:**

IntMath::sum(10, 20) = 30
LongMath::sum(1000000, 2000000) = 3000000




## Question 3: Unsigned Integer Underflow

### A. Output:

4294967295

### B. Explanation:

`x` is an `unsigned int`, which on most systems is **32 bits** and can only hold values from **0 to 4,294,967,295**.

When you subtract 1 from 0 on an unsigned type, it **wraps around** (integer underflow) due to modular arithmetic. Unsigned integers can never be negative, so instead of going to -1, the value wraps to the maximum value of the type:

> 0 - 1 = 2³² - 1 = **4,294,967,295**

This is defined behavior in C++ for unsigned types (unlike signed overflow, which is undefined).
