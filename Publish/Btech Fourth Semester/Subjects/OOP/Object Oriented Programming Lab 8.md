---
Title: "Object Oriented Programming Lab 5"
Status: 
marker: 
tags: 
Date: "2025.02.27"
Time: "14:33"
---
d# Object Oriented Programming Lab 5

# Questions
## Question 1
 Write a program (with series of functions) that reads student scores, gets the best score, and then assigns grades based on the following scheme:
- Grade is B if score is >= best - 20;
- Grade is C if score is >= best - 30;
- Grade is D if score is >= best - 40;
- Grade is F otherwise.
The program prompts the user to enter the total number of students, then prompts
the user to enter all of the scores, and concludes by displaying the grades. Here is
a sample run:

```java
import java.util.Scanner;

  

public class StudentScore {

  

    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);

  

        // Prompt the user to enter the number of students

        System.out.print("Enter the number of students: ");

        int numberOfStudents = input.nextInt();

  

        // Create an array to hold the scores

        int[] scores = new int[numberOfStudents];

  

        // Prompt the user to enter each score

        System.out.println("Enter the scores:");

        for (int i = 0; i < numberOfStudents; i++) {

            scores[i] = input.nextInt();

        }

  

        // Get the best score

        int bestScore = getBestScore(scores);

  

        // Display the grades

        for (int i = 0; i < numberOfStudents; i++) {

            char grade = getGrade(scores[i], bestScore);

            System.out.println("Student " + i + " score is " + scores[i] + " and grade is " + grade);

        }

  

        input.close();

    }

  

    // Function to get the best score

    public static int getBestScore(int[] scores) {

        int best = scores[0];

        for (int score : scores) {

            if (score > best) {

                best = score;

            }

        }

        return best;

    }

  

    // Function to get the grade based on the score and best score

    public static char getGrade(int score, int best) {

        if (score >= best - 10) {

            return 'A';

        } else if (score >= best - 20) {

            return 'B';

        } else if (score >= best - 30) {

            return 'C';

        } else if (score >= best - 40) {

            return 'D';

        } else {

            return 'F';

        }

    }

}
```

```bash

C:\Users\TJ\prog\temp\oop\lab5>java StudentScore.java
Enter the number of students: 4
Enter the scores:
90
100
50
60
Student 0 score is 90 and grade is A
Student 1 score is 100 and grade is A
Student 2 score is 50 and grade is F
Student 3 score is 60 and grade is D
```

## Question 2
Write a program (with series of functions) that reads in ten numbers and displays distinct numbers (i.e., if a number appears multiple times, it is displayed only once). _Hint_: Read a number and store it to an array if it is new. If the number is already in the array, ignore it. After the input, the array contains the distinct numbers. Here is the sample run of the program:

```java
import java.util.Scanner;
  
public class Distinct {
  
    public static void main(String[] args) {
        int a[] = new int[10];
        Scanner scanner = new Scanner(System.in);
        for (int i = 0; i < a.length; i++) {
            System.out.print("Enter a number: ");
            a[i] = scanner.nextInt();
        }
        scanner.close();
  
        int new_array[] = new int[10];
        int new_array_index = 0;
        for (int i = 0; i < a.length; i++) {
            boolean isDistinct = true;
            for (int j = 0; j < new_array_index; j++) {
            if (a[i] == new_array[j]) {
                isDistinct = false;
                break;
            }
            }
            if (isDistinct) {
            new_array[new_array_index++] = a[i];
            }
        }
  
        System.out.print("Distinct elements: ");
        for (int i = 0; i < new_array_index; i++) {
            System.out.print(new_array[i] + " ");
        }
    }
}
```

```bash
C:\Users\TJ\prog\temp\oop\lab5>java Distinct.java
Enter a number: 4
Enter a number: 5
Enter a number: 6
Enter a number: 2
Enter a number: 3 
Enter a number: 4
Enter a number: 5
Enter a number: 6
Enter a number: 7
Enter a number: 9
Distinct elements: 4 5 6 2 3 7 9
```

## Question 3
Write a program to create a Vector that holds the following values.
2, 6, Hello, 7, everyone
Use appropriate methods of Vector class to perform the following task.
- Iterate through the vector
- Add element at a specified index
- Check whether a given element exist in the Vector, if so remove it
- Replace an item with a new value given
- Retrieve the first and the last element of the Vector

```java
import java.util.Vector;
import java.util.Enumeration;
  
public class VectorExample {
    public static void main(String[] args) {
        // Create a Vector and add initial values
        Vector<Object> vector = new Vector<>();
        vector.add(2);
        vector.add(6);
        vector.add("Hello");
        vector.add(7);
        vector.add("everyone");
  
        // a. Iterate through the vector
        System.out.println("Iterating through the vector:");
        Enumeration<Object> enumeration = vector.elements();
        while (enumeration.hasMoreElements()) {
            System.out.println(enumeration.nextElement());
        }

        // b. Add element at a specified index
        vector.add(2, "newElement");
        System.out.println("\nVector after adding element at index 2:");
        System.out.println(vector);
  
        // c. Check whether a given element exists in the Vector, if so remove it
        Object elementToRemove = "Hello";
        if (vector.contains(elementToRemove)) {
            vector.remove(elementToRemove);
            System.out.println("\nVector after removing element 'Hello':");
            System.out.println(vector);
        }
  
       // d. Replace an item with a new value given
        int indexToReplace = 3;
        Object newValue = "newValue";
        vector.set(indexToReplace, newValue);
        System.out.println("\nVector after replacing element at index 3 with 'newValue':");
        System.out.println(vector);
  
        // e. Retrieve the first and the last element of the Vector
        Object firstElement = vector.firstElement();
        Object lastElement = vector.lastElement();
        System.out.println("\nFirst element: " + firstElement);
        System.out.println("Last element: " + lastElement);
    }
}
```
# References


###### Information
- date: 2025.02.27
- time: 14:33