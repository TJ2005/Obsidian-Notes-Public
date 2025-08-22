---
Title: Object Oriented Programming Lab 2
Status: 
marker: 
tags: 
Date: 2025.01.16
Time: 14:09
---
# Java Programming Assignments Submission
**Name:** Tejas Sahoo  
**Roll Number:** K057  

## 1. Program to reverse a number and check if it’s a palindrome
```java
import java.util.Scanner;

public class Question1 {
    public static boolean checkPalindrome(int number) {
        int originalNumber = number;
        int reversedNumber = 0;
        while (number != 0) {
            int digit = number % 10;
            reversedNumber = reversedNumber * 10 + digit;
            number /= 10;
        }
        System.out.println(reversedNumber);

        return reversedNumber == originalNumber;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int number = scanner.nextInt();
        System.out.println("Your input was " + number);

        if (checkPalindrome(number)) {
            System.err.println("The number is a palindrome");
        } else {
            System.err.println("The number is not a palindrome");
        }

        scanner.close();
    }
}
```
![[IMG-20250730000528969.png]]

## 2. Program to display ‘n’ odd numbers and their sum
```java
public class Question2 {
    public static int summation(int number) {
        int sum = 0;
        for (int i = 0; i < number; i++) {
            if (i % 2 != 0) {
                sum += i;
            }
        }
        return sum;
    }

    public static void main(String[] args) {
        System.out.println(summation(10));
    }
}
```
![[IMG-20250730000549970.png]]

## 3. Program to count the number of vowels and consonants in a given line of text
```java
public class Question3 {
    public static class CountResult {
        public int vowelCount;
        public int consonantCount;

        public CountResult(int vowelCount, int consonantCount) {
            this.vowelCount = vowelCount;
            this.consonantCount = consonantCount;
        }
    }

    public static CountResult alphaCounter(String input) {
        char[] vowels = {'a', 'e', 'i', 'o', 'u'};
        char[] consonants = {'b', 'c', 'd', 'f', 'g', 'h', 'j', 'k', 'l', 'm', 'n', 'p', 'q', 'r', 's', 't', 'v', 'w', 'x', 'y', 'z'};
        int vowelCount = 0;
        int consonantCount = 0;

        for (int i = 0; i < input.length(); i++) {
            char c = Character.toLowerCase(input.charAt(i));
            for (char vowel : vowels) {
                if (c == vowel) {
                    vowelCount++;
                }
            }
            for (char consonant : consonants) {
                if (c == consonant) {
                    consonantCount++;
                }
            }
        }

        return new CountResult(vowelCount, consonantCount);
    }

    public static void main(String[] args) {
        CountResult result = alphaCounter("Tejas Sahoo");
        System.out.println("Vowels: " + result.vowelCount);
        System.out.println("Consonants: " + result.consonantCount);
    }
}
```
![[IMG-20250730000604890.png]]
## 4. Program to accept two numbers and determine their order
```java
import java.util.Scanner;

public class Question4 {
    public static boolean isAscending(int a, int b) {
        return a < b;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter first number: ");
        int number1 = scanner.nextInt();
        System.out.print("Enter second number: ");
        int number2 = scanner.nextInt();

        if (isAscending(number1, number2)) {
            System.out.println("The numbers are in ascending order");
        } else {
            System.out.println("The numbers are not in ascending order");
        }

        scanner.close();
    }
}
```

## 5. Program to find the power of a number given its base and exponent value
```java
public class Question5 {
    public static int pow(int base, int power) {
        int result = 1;
        for (int i = 0; i < power; i++) {
            result *= base;
        }
        return result;
    }

    public static void main(String[] args) {
        System.out.println(pow(2, 3));
    }
}
```
![[IMG-20250730000611036.png]]
## 6. Program to check whether two strings are equal using string functions
```java
public class Question6 {
    public static boolean compareStr(String a, String b) {
        return a.equals(b);
    }

    public static void main(String[] args) {
        String a = "Hello";
        String b = "Hello";

        if (compareStr(a, b)) {
            System.out.println("The strings are equal");
        } else {
            System.out.println("The strings are not equal");
        }
    }
}```
![[Pasted image 20250116154840.png]]