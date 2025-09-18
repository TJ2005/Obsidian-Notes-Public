---
Title: Object Oriented Programming Computer Lab 1
Status: 
marker:
  - "[[Programming]]"
  - "[[Java]]"
tags: 
Date: 2025.01.23
Time: 14:59
---
# Object Oriented Programming Computer Lab 1

### **Java Programming Assignments**

**Name:** Tejas Sahoo  
**Roll Number:** K057

---

## **1. Evaluation of Expressions**

### **Given Assumptions**:

`int a = 1;`  
`double d = 1.0;`

### **Results of the Expressions**:

1. `a = 46 / 9;`  
    **Result**: `a = 5`  
    _(Integer division truncates the fractional part.)_
    
2. `a = 46 % 9 + 4 * 4 - 2;`  
    **Result**: `a = 19`  
    Explanation:  
    `46 % 9 = 1`, then `1 + 4 * 4 = 17`, and `17 - 2 = 19`.
    
3. `a = 45 + 43 % 5 * (23 * 3 % 2);`  
    **Result**: `a = 45`  
    Explanation:  
    `43 % 5 = 3`, `23 * 3 = 69`, `69 % 2 = 1`, so `45 + 3 * 1 = 45`.
    
4. `a %= 3 / a + 3;`  
    **Result**: `a = 0`  
    Explanation:  
    `(3 / a)` becomes `3 / 1 = 3`, then `3 + 3 = 6`. `a %= 6` means `a = 5 % 6 = 0`.
    
5. `d = 4 + d * d + 4;`  
    **Result**: `d = 9.0`  
    Explanation:  
    `d * d = 1.0 * 1.0 = 1.0`, `4 + 1.0 + 4 = 9.0`.
    
6. `d += 1.5 * 3 + (++a);`  
    **Result**: `d = 14.5`  
    Explanation:  
    `++a` increments `a` to `1`, `1.5 * 3 = 4.5`, `d += 4.5 + 1 = 9.0 + 5.5 = 14.5`.
    
7. `d -= 1.5 * 3 + a++;`  
    **Result**: `d = 9.0`  
    Explanation:  
    `a++` uses `a = 1` and increments after, `1.5 * 3 = 4.5`, `d -= 4.5 + 1 = 14.5 - 5.5 = 9.0`.
    

---

## **2. Program to Check Whether a Number is Even or Odd**

```java
import java.util.Scanner;

public class EvenOdd {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter an integer: ");
        int number = scanner.nextInt();

        if (number % 2 == 0) {
            System.out.println(number + " is even.");
        } else {
            System.out.println(number + " is odd.");
        }

        scanner.close();
    }
}
```
![[IMG-20250730000528960.png]]
---

## **3. Program to Solve a Quadratic Equation**

```java
import java.util.Scanner;

public class QuadraticEquation {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter coefficient a: ");
        double a = scanner.nextDouble();

        System.out.print("Enter coefficient b: ");
        double b = scanner.nextDouble();

        System.out.print("Enter coefficient c: ");
        double c = scanner.nextDouble();

        double discriminant = b * b - 4 * a * c;

        if (discriminant > 0) {
            double root1 = (-b + Math.sqrt(discriminant)) / (2 * a);
            double root2 = (-b - Math.sqrt(discriminant)) / (2 * a);
            System.out.println("The roots are real and unequal:");
            System.out.println("Root 1 = " + root1);
            System.out.println("Root 2 = " + root2);
        } else if (discriminant == 0) {
            double root = -b / (2 * a);
            System.out.println("The roots are real and equal:");
            System.out.println("Root = " + root);
        } else {
            System.out.println("The roots are imaginary (no real solutions).");
        }

        scanner.close();
    }
}
```
![[IMG-20250730000549209.png]]
---

# References


###### Information
- date: 2025.01.09
- time: 14:59