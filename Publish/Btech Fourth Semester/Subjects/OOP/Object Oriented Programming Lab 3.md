---
Title: Object Oriented Programming Lab 3
Status: 
marker:
  - "[[Inheritance]]"
  - "[[Java]]"
tags: 
Date: 2025.02.13
Time: 15:36
---
K057
# Java OOP Lab Exercises

## Question 1: Printing Square of Numbers

### Code: `First.java`

```java
class First {
    public static void main(String[] args) {
        SquarePrinter printer = new SquarePrinter();
        printer.printSquares();
    }
}

class SquarePrinter {
    private int start;
    private int end;

    // Default constructor
    public SquarePrinter() {
        this.start = 1;
        this.end = 15;
    }

    // Constructor with custom range
    public SquarePrinter(int start, int end) {
        this.start = start;
        this.end = end;
    }

    // Constructor with single end value
    public SquarePrinter(int end) {
        this.start = 1;
        this.end = end;
    }

    // Method to print squares of numbers from start to end
    public void printSquares() {
        for (int i = start; i <= end; i++) {
            System.out.println("Square of " + i + " is " + (i * i));
        }
    }
}
````

### Output:

```
Square of 1 is 1
Square of 2 is 4
Square of 3 is 9
Square of 4 is 16
Square of 5 is 25
Square of 6 is 36
Square of 7 is 49
Square of 8 is 64
Square of 9 is 81
Square of 10 is 100
Square of 11 is 121
Square of 12 is 144
Square of 13 is 169
Square of 14 is 196
Square of 15 is 225
```

---

## Question 2: Calculating Area of Shapes

### Code: `Second.java`

```java
public class Second {
    public static void main(String[] args) {
        Shape shape = new Shape();
        shape.calculateArea();
    }
}

class Shape {
    public void calculateArea() {
        int squareSide = 5;
        int rectangleLength = 6, rectangleWidth = 4;

        System.out.println("Area of the square: " + (squareSide * squareSide));
        System.out.println("Area of the rectangle: " + (rectangleLength * rectangleWidth));
    }
}
```

### Output:

```
Area of the square: 25
Area of the rectangle: 24
```

---

## Question 3: Multiplying Integers and Doubles

### Code: `Third.java`

```java
public class Third {
    // Constructor
    public Third() {
        // Default constructor
    }

    // Method to multiply two integers
    public int multiply(int a, int b) {
        return a * b;
    }

    // Overloaded method to multiply three integers
    public int multiply(int a, int b, int c) {
        return a * b * c;
    }

    // Overloaded method to multiply two doubles
    public double multiply(double a, double b) {
        return a * b;
    }

    // Overloaded method to multiply an integer and a double
    public double multiply(int a, double b) {
        return a * b;
    }

    // Overloaded method to multiply a double and an integer
    public double multiply(double a, int b) {
        return a * b;
    }

    public static void main(String[] args) {
        Third obj = new Third();

        // Testing the multiply methods
        System.out.println("Multiplying two integers: " + obj.multiply(2, 3));
        System.out.println("Multiplying three integers: " + obj.multiply(2, 3, 4));
        System.out.println("Multiplying two doubles: " + obj.multiply(2.5, 3.5));
        System.out.println("Multiplying an integer and a double: " + obj.multiply(2, 3.5));
        System.out.println("Multiplying a double and an integer: " + obj.multiply(2.5, 3));
    }
}
```

### Output:

```
Multiplying two integers: 6
Multiplying three integers: 24
Multiplying two doubles: 8.75
Multiplying an integer and a double: 7.0
Multiplying a double and an integer: 7.5
```

---

## Question 4: Printing First 100 Emirp Numbers

### Code: `Fourth.java`

```java
public class Fourth {

    public static void main(String[] args) {
        EmirpNumber emirpNumber = new EmirpNumber();
        emirpNumber.printFirst100Emirps();
    }
}

class EmirpNumber {

    public EmirpNumber() {
        // Constructor
    }

    public void printFirst100Emirps() {
        int count = 0;
        int number = 13; // Starting from the first known emirp number
        
        while (count < 100) {
            if (isEmirp(number)) {
                System.out.print(number + " ");
                count++;
                if (count % 10 == 0) {
                    System.out.println();
                }
            }
            number++;
        }
    }

    private boolean isEmirp(int number) {
        if (!isPrime(number)) {
            return false;
        }
        int reversedNumber = reverse(number);
        return number != reversedNumber && isPrime(reversedNumber);
    }

    private boolean isPrime(int number) {
        if (number <= 1) {
            return false;
        }
        for (int i = 2; i <= Math.sqrt(number); i++) {
            if (number % i == 0) {
                return false;
            }
        }
        return true;
    }

    private int reverse(int number) {
        int reversed = 0;
        while (number != 0) {
            reversed = reversed * 10 + number % 10;
            number /= 10;
        }
        return reversed;
    }
}
```

### Output:

```
13 17 31 37 71 73 79 97 107 113 
149 157 167 179 199 311 337 347 359 389
701 709 733 739 743 751 761 769 907 937
941 953 967 971 983 991 1009 1021 1031 1033
1061 1069 1091 1097 1103 1109 1151 1153 1181 1193
1201 1213 1217 1223 1229 1231 1237 1249 1259 1279
1283 1301 1321 1381 1399 1409 1429 1439 1453 1471
1487 1499 1511 1523 1559 1583 1597 1601 1619 1657
1669 1723 1733 1741 1753 1789 1811 1831 1847 1867
1879 1901 1913 1933 1949 1979 3011 3019 3023 3049
```

---



# References


###### Information
- date: 2025.02.13
- time: 15:36